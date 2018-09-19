---
layout: post
title: How to | SFChart | Xamarin.iOS | Syncfusion
description: getting started 
platform: xamarin.ios
control: SFChart
documentation: ug
---

# How to

##  Get the data point collection based on region

[`CartesianSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFCartesianSeries.html) provides the following methods to get the visible range data points.

* [`GetDataPoints(RectangleF rect)`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFCartesianSeries~GetDataPoints(RectangleF).html) - Gets the collection of data that fall inside the given rectangle region.
* [`GetDataPoints(double startX, double endX, double startY, double endY)`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFCartesianSeries~GetDataPoints(Double,Double,Double,Double).html) - Gets the collection of data from the given ChartAxis visible range.

{% highlight c# %}

List<object> dataPoints = Series.GetDataPoints(rectangle);

or

List<object> dataPoints = Series.GetDataPoints(startX, endX, startY, endY);

{% endhighlight  %}