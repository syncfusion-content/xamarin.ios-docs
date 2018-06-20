---
layout: post
title: Populating data | SFChart | Xamarin.iOS | Syncfusion
description: What are all the different types for add data point to series in Essential Xamarin.forms.
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Populating Data

[`SFChart`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChart.html) control can be configured with data points using ItemsSource property of [`SFSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries.html). You can create data points for chart.

## Custom Object

You can assign a collection of custom objects to the [`ItemsSource`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~ItemsSource.html) property. In this case, you need to set the [`XBindingPath`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~XBindingPath.html) and [`YBindingPath`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFXyDataSeries~YBindingPath.html) properties of chart series with the property names of the custom object which contains the x-value/category and y-value respectively.

N> While using custom objects, XBindingPath property is required for all types of chart series. You need to set YBindingPath property only for the XYDataSeries types which needs single y-value for a data point. For example, Line, Spline, Column, Bar, Pie etc. For BubbleSeries type, you need to set both YBindingPath and Size properties since it requires two y-values to plot a single bubble data point. In the case of financial series types like Candle and HiLoOpenClose, which requires four y-values for a single data point, you need to set High, Low, Open and Close properties with the property names of a custom object which contains respective values.

{% highlight c# %}
public class MonthDemand

{

    public MonthDemand(string demand, double year2010, double year2011)
    {

        Demand = demand;

        Year2010 = year2010;

        Year2011 = year2011;

    }

    public string Demand { get; set; }

    public double Year2010 { get; set; }

    public double Year2011 { get; set; }

}

public class DataModel
{
    
    public ObservableCollection<MonthDemand>  Demands{ get; set; }

    public DataModel ()
    {

        Demands = new ObservableCollection<MonthDemand>();

        Demands.Add(new MonthDemand("Jan", 42, 27));
        Demands.Add(new MonthDemand("Feb", 44, 28));
        Demands.Add(new MonthDemand("Mar", 53, 35));
        Demands.Add(new MonthDemand("Apr", 64, 44));
        Demands.Add(new MonthDemand("May", 75, 54));
        Demands.Add(new MonthDemand("Jun", 83, 63));
        Demands.Add(new MonthDemand("Jul", 87, 68));
        Demands.Add(new MonthDemand("Aug", 84, 66));
        Demands.Add(new MonthDemand("Sep", 78, 59));
        Demands.Add(new MonthDemand("Oct", 67, 48));
        Demands.Add(new MonthDemand("Nov", 55, 38));
        Demands.Add(new MonthDemand("Dec", 45, 29));

    }

}
{% endhighlight %}

{% highlight c# %}
chart.Series.Add (new SFColumnSeries () {
    
    ItemsSource = dataModel.Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010"

});
{% endhighlight %}
