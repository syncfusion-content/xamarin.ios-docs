---
layout: post
title: Get the data point collection based on region in Syncfusion SFChart
description: Get the data point collection based on region in SFChart
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Get the data point collection based on region

[`CartesianSeries`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFCartesianSeries.html) provides the following methods to get the visible range data points.

* [`GetDataPoints(RectangleF rect)`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFCartesianSeries.html#Syncfusion_SfChart_iOS_SFCartesianSeries_GetDataPoints_System_Drawing_RectangleF_) - Gets the collection of data that fall inside the given rectangle region.
* [`GetDataPoints(double startX, double endX, double startY, double endY)`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFCartesianSeries.html#Syncfusion_SfChart_iOS_SFCartesianSeries_GetDataPoints_System_Double_System_Double_System_Double_System_Double_) - Gets the collection of data from the given ChartAxis visible range.

{% highlight c# %}

List<object> dataPoints = Series.GetDataPoints(rectangle);

or

List<object> dataPoints = Series.GetDataPoints(startX, endX, startY, endY);

{% endhighlight  %}

N> You can get the visible plotting region of the series in the chart using [`SeriesClipRect`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChart.html#Syncfusion_SfChart_iOS_SFChart_SeriesClipRect) or [`SeriesBounds`]() property in run time.
