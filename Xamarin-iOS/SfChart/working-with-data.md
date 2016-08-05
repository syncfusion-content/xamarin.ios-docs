---
layout: post
title: Populating data | SFChart | Xamarin.iOS | Syncfusion
description: What are all the different types for add data point to series in Essential Xamarin.forms.
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Populating Data

SFChart needs to be provided with the datasource, which adopts the SFChartDataSource protocol to visualize the data.


## Chart Data Point	

To visualize the data values in the chart, we need to provide the collection of datapoints as the instance of `SFChartDataPoint`.

N> SFChartDataPoint class has few overloaded constructors depending on the number of y values required to plot a data point for particular series type. For example, you can use a constructor with two parameters to instantiate a data point for XY Data Series like Line, Spline, Pie etc,

Following code snippet illustrates this,

{% highlight c# %}
public class ChartDataModel : SFChartDataSource
{
    NSMutableArray HighTemperature;

    public ChartDataModel ()
    {
        HighTemperature= new NSMutableArray();

        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Jan"),NSObject.FromObject(42)));

        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Feb"),NSObject.FromObject(44)));

        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Mar"),NSObject.FromObject(53)));

        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Apr"),NSObject.FromObject(64)));

        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("May"),NSObject.FromObject(75)));

        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Jun"),NSObject.FromObject(83)));

        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Jul"),NSObject.FromObject(87)));

        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Aug"),NSObject.FromObject(84)));

        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Sep"),NSObject.FromObject(78)));

        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Oct"),NSObject.FromObject(67)));

        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Nov"),NSObject.FromObject(55)));

        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Dec"),NSObject.FromObject(45))); 

    } 
}

{% endhighlight %}

## Adopting chart data source protocol

In order to add data source to SFChart, you need to adopt the `SFChartDataSource` protocol through the class extension as shown below.

{% highlight c# %}

// Need to create seperate class for SFChartDataSource
public class SFChartDataSource : SFChartDataSource
{
}

{% endhighlight %}

The `SFChartDataSource` protocol contains four required methods and an optional method.

**Required Methods**

* `NumberOfSeriesInChart` - returns an integer that represents the number of series to be added to SFChart.
* `GetSeries` - returns a series object, like SFSeries, for the Chart at a particular index.
* `GetNumberOfDataPoints` - returns the number of data points required.
* `GetDataPoint` - returns each data point to be plotted in the series.

**Optional Method**

* `GetDataPoints` - Returns an array of data points to be plotted in the series based on series index.

The following code example shows how to implement the SFChartDataSource and setting DataSource to chart.

{% highlight c# %}
public override void ViewDidLoad ()
{
    base.ViewDidLoad ();

    SFChart chart               	= new SFChart ();
    chart.Frame                 	= this.View.Frame;
	chart.Title.Text   				= new NSString( "Weather Analysis");
	SFCategoryAxis primaryAxis 		= new SFCategoryAxis ();
	primaryAxis.Title.Text     		= new NSString("Month");
	chart.PrimaryAxis   			= primaryAxis;
	SFNumericalAxis secondaryAxis 	= new SFNumericalAxis ();
	secondaryAxis.Title.Text      	= new NSString("Temperature");
	chart.SecondaryAxis           	= secondaryAxis;
	
	//Defining the data source for the Chart.
    ChartDataModel dataModel    	= new ChartDataModel ();
    chart.DataSource            	= dataModel as SFChartDataSource;

    this.View.AddSubview (chart);
}

public class ChartDataModel : SFChartDataSource
{

	NSMutableArray HighTemperature;

    public ChartDataModel ()
    {
        HighTemperature = new NSMutableArray();

        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Jan"),NSObject.FromObject(42)));
        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Feb"),NSObject.FromObject(44)));
        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Mar"),NSObject.FromObject(53)));
        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Apr"),NSObject.FromObject(64)));
        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("May"),NSObject.FromObject(75)));
        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Jun"),NSObject.FromObject(83)));
        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Jul"),NSObject.FromObject(87)));
        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Aug"),NSObject.FromObject(84)));
        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Sep"),NSObject.FromObject(78)));
        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Oct"),NSObject.FromObject(67)));
        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Nov"),NSObject.FromObject(55)));
        HighTemperature.Add (new SFChartDataPoint(NSObject.FromObject ("Dec"),NSObject.FromObject(45))); 

    } 
	
    public override nint NumberOfSeriesInChart (SFChart chart)
    {
        return 1; 
    }

    public override SFSeries GetSeries (SFChart chart, nint index)
    {
        SFSplineSeries series  = new SFSplineSeries ();
        series.Label           = new NSString("High");
        return series;
    }

    public override SFChartDataPoint GetDataPoint (SFChart chart, nint index, nint seriesIndex)
    {
        return HighTemperature.GetItem<SFChartDataPoint> ((nuint)index);
    }

    public override nint GetNumberOfDataPoints (SFChart chart, nint index)
    {
        return 12;
    }
}

{% endhighlight %}
