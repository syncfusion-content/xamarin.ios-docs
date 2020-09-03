---
layout: post
title: Populating data | SFChart | Xamarin.iOS | Syncfusion
description: What are all the different types for add data point to series in Essential Xamarin.forms.
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Populating Data

[`SFChart`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChart.html) control can be configured with data points using ItemsSource property of [`SFSeries`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFSeries.html). You can create data points for chart.

## Custom Object

You can assign a collection of custom objects to the [`ItemsSource`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFSeries.html#Syncfusion_SfChart_iOS_SFSeries_ItemsSource) property. In this case, you need to set the [`XBindingPath`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFSeries.html#Syncfusion_SfChart_iOS_SFSeries_XBindingPath) and [`YBindingPath`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFXyDataSeries.html#Syncfusion_SfChart_iOS_SFXyDataSeries_YBindingPath) properties of chart series with the property names of the custom object which contains the x-value/category and y-value respectively.

N> While using custom objects, XBindingPath property is required for all types of chart series. You need to set YBindingPath property only for the XYDataSeries types which needs single y-value for a data point. For example, Line, Spline, Column, Bar, Pie etc. For BubbleSeries type, you need to set both YBindingPath and Size properties since it requires two y-values to plot a single bubble data point. In the case of financial series types like Candle and HiLoOpenClose, which requires four y-values for a single data point, you need to set High, Low, Open and Close properties with the property names of a custom object which contains respective values.

{% highlight c# %}
public class ChartData
{
    public ChartData(string demand, double year2010, double year2011)
    {
        Demand = demand;

        Year2010 = year2010;

        Year2011 = year2011;

    }

    public string Demand { get; set; }

    public double Year2010 { get; set; }

    public double Year2011 { get; set; }

}
{% endhighlight %}

{% highlight c# %}

    ObservableCollection<ChartData> Demands = new ObservableCollection<ChartData>(); 
    Demands.Add(new ChartData("Jan", 42, 27));
    Demands.Add(new ChartData("Feb", 44, 28));
    Demands.Add(new ChartData("Mar", 53, 35));
    Demands.Add(new ChartData("Apr", 64, 44));
    Demands.Add(new ChartData("May", 75, 54));

    chart.Series.Add (new SFColumnSeries () {
    
    ItemsSource = Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010"

});
{% endhighlight %}
