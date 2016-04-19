---
layout: post
title: Multiple series and combination of series | SFChart | Xamarin.iOS | Syncfusion
description: How to add multiple series and combination series in SFChart
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Chart Series

In order to add data source to SFChart, you need to implement the SFChartDataSource protocol which contains four methods and an optional method. This has been explained briefly in the `Populating Data` document.

## Multiple Series

You can add multiple series to `Series` property of `SFChart` class.

{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    if (index == 0) 
    {
        SFColumnSeries series1 = new SFColumnSeries ();

        series1.Label          = new NSString ("Gold");

        return series1;
    } 
    else if (index == 1) 
    {
        SFColumnSeries series2 = new SFColumnSeries ();

        series2.Label          = new NSString ("Silver");

        return series2;
    } 
    else
    {
        SFColumnSeries series3 = new SFColumnSeries ();

        series3.Label          = new NSString ("Bronze");

        return series3;
    } 
}
{% endhighlight %}


![](ChartSeries_images/MultipleSeries.png)

## Combination Series

`SFChart` allows you to render the combination of different types of series.

{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    if (index == 0)
    {
        SFColumnSeries series1 = new SFColumnSeries ();

        series1.Label          = new NSString ("Unit Sold");

        return series1;
    } 
    else 
    {
        SFLineSeries series2 = new SFLineSeries ();

        series2.Label        = new NSString ("Total Transaction");

        return series2;
    } 
}
{% endhighlight %}


![](ChartSeries_images/CombinationSeries.png)

**Limitation of Combination Chart**

* Bar, StackingBar, and StackingBar100 cannot be combined with the other Cartesian type series
* Cartesian type series cannot be combined with accumulation series (pie, doughnut, funnel, and pyramid) and radar & polar series

When the combination of Cartesian and accumulation series types are added to the `Series` property, the series which are similar to the first series will be rendered and other series will be ignored. Following code snippet illustrates this.

{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    if (index == 0)
    {
        SFLineSeries series1    = new SFLineSeries ();

        series1.Label           = new NSString ("Unit Sold");

        return series1;
    } 
    else 
    {
        SFPieSeries series2     = new SFPieSeries ();

        series2.Label           = new NSString ("Total Transaction");

        return series2;
    } 
}
{% endhighlight %}

![](ChartSeries_images/Limitation.png)