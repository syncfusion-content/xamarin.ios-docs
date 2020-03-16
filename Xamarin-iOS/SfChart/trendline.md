---
layout: post
title: Chart trendline | SFChart | Xamarin.iOS | Syncfusion
description: How to configure the chart trendlines and customize the appearance of the trendlines in Xamarin.iOS Chart.
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Trendlines in Xamarin.iOS Chart

The [`Trendline`]() is a line drawn over the chart to display the overall direction of the results. And it built on the assumption based on current and past beliefs. 

The following code examples shows how to add Trendline in SFChart.

{% highlight c# %} 

SFColumnSeries columnSeries = new SFColumnSeries();
columnSeries.Trendlines = new ChartTrendlineCollection();
SFChartTrendline trendline = new SFChartTrendline();
columnSeries.Trendlines.Add(trendline);

{% endhighlight %}

## Types of Trendline

SFChart support following types of [`Trendlines`]().

* [`Linear`]()
* [`Exponential`]()
* [`Logarithmic`]()
* [`Power`]()
* [`Polynomial`]()


### Linear

[`Linear`]() trendline was best-fit straight line for simple linear datasets. A linear trend line usually shows that something is increasing or decreasing at a steady rate. This is the default trendline to be drawn for the SFChart.

The following is the code example of linear trendline.

{% tabs %} 
{% highlight c# %}
[C#]

columnSeries.Trendlines = new ChartTrendlineCollection();
SFChartTrendline trendline = new SFChartTrendline();
trendline.Type = ChartTrendlineType.Linear;
columnSeries.Trendlines.Add(trendline);

{% endhighlight %}

{% endtabs %}

### Logarithmic

A [`Logarithmic`]() trendline is the strongest-fit curved line, that is most effective when the data change rate increases or decreases rapidly. Logarithmic trends may use negative and/or positive values as well. 

The following is the code example of logarithmic trendline.

{% tabs %} 

{% highlight c# %}

SFColumnSeries columnSeries = new SFColumnSeries();
columnSeries.Trendlines = new ChartTrendlineCollection();
SFChartTrendline trendline = new SFChartTrendline();
trendline.Type = ChartTrendlineType.Logarithmic;
columnSeries.Trendlines.Add(trendline);

{% endhighlight %}

{% endtabs %}

### Exponential

The [`Exponential`]() trendline is the curved line most useful for data values rise or fall at increasingly higher rates.

N> SFChart will not generate Exponential trendline when your data contains zero or negative values. 

{% tabs %} 

{% highlight c# %}
[C#]

SFColumnSeries columnSeries = new SFColumnSeries();
columnSeries.Trendlines = new ChartTrendlineCollection();
SFChartTrendline trendline = new SFChartTrendline();
trendline.Type = ChartTrendlineType.Exponential;
columnSeries.Trendlines.Add(trendline);

{% endhighlight %}

{% endtabs %}

### Power

The [`Power`]() trendline is typically used with data sets to compare measurements that grow at a specific rate.

The following is the code example of power trendline.

{% tabs %} 

{% highlight c# %}
[C#]

SFColumnSeries columnSeries = new SFColumnSeries();
columnSeries.Trendlines = new ChartTrendlineCollection();
SFChartTrendline trendline = new SFChartTrendline();
trendline.Type = ChartTrendlineType.Power;
columnSeries.Trendlines.Add(trendline);

{% endhighlight %}

{% endtabs %}

### Polynomial

The [`polynomial`]() trendline is a curved line that is used when there are more data fluctuations. By default, this trendline calculated with order of 2, it will be override by the property [`PolynomialOrder`]().

The following is the code example of polynomial trendline.

{% tabs %} 

{% highlight c# %}
[C#]

columnSeries.Trendlines = new ChartTrendlineCollection();
SFChartTrendline trendline = new SFChartTrendline();
trendline.Type = ChartTrendlineType.Polynomial;
trendline.PolynomialOrder = 3;
columnSeries.Trendlines.Add(trendline);

{% endhighlight %}

{% endtabs %}

## Forecasting

Forecasting is used to display trends about the future and the past beliefs.

The following two types of forecasting are available in SFChart:

* Forward Forecasting
* Backward Forecasting

### Forward Forecasting

For determining the future trends (in forward direction). The 
following code example explains the how to set the value for [`ForwardForecast`]().

{% tabs %} 

{% highlight c# %}
[C#]

columnSeries.Trendlines = new ChartTrendlineCollection();
SFChartTrendline trendline = new SFChartTrendline();
trendline.Type = ChartTrendlineType.Linear;
trendline.ForwardForecast = 2;
columnSeries.Trendlines.Add(trendline);

{% endhighlight %}

{% endtabs %}

### Backward Forecast

For determining the future trends (in backward direction). The following code example explains the how to set the value for [`BackwardForecast`]().

{% tabs %} 

{% highlight c# %}
[C#]

columnSeries.Trendlines = new ChartTrendlineCollection();
SFChartTrendline trendline = new SFChartTrendline();
trendline.Type = ChartTrendlineType.Linear;
trendline.BackwardForecast = 2;
columnSeries.Trendlines.Add(trendline);

{% endhighlight %}

{% endtabs %}

## Customization

We can customize the trendline appearance using [`LineWidth`](), [`LineColor`]() and [`Dashes`]() properties. 

{% tabs %} 

{% highlight c# %}

trendline.LineColor = UIColor.Red;
trendline.LineWidth = 2;
NSObject[] dashes = new NSObject[2];
dashes[0] = (NSNumber)3;
dashes[1] = (NSNumber)3;
trendline.Dashes = NSArray.FromObjects(dashes);

{% endhighlight %}

{% endtabs %}

## Legend Item Visibility

We can able to control the visibility of the trendline legend items using [`VisibilityOnLegend`]() property of the Trendline.

{% tabs %} 

{% highlight c# %}

trendline.VisibilityOnLegend = Visibility.Visible;

{% endhighlight %}

{% endtabs %}

