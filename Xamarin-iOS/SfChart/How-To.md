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

##  Adding duplicate axis in SFChart

Duplicate axis can be added in the [`SFChart`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChart.html) using the chart [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.ChartBase~Axes.html) collection property. The axis added in the [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.ChartBase~Axes.html) collection will be aligned in the horizontal position by default. The axis position can be changed by using the [`IsVertical`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFAxis~IsVertical.html) bool property of the [`SfAxis`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFAxis.html). When [`IsVertical`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFAxis~IsVertical.html) property is set true axis will be placed vertical and vice versa.

N> The [`SFAxis`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFAxis.html) added in the [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.ChartBase~Axes.html) collection won’t get removed until removing it from the [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.ChartBase~Axes.html) collection. The [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.ChartBase~Axes.html) collection clear method doesn’t support. Same axis can’t be added more than once in [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.ChartBase~Axes.html) only distinct axis get added in [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.ChartBase~Axes.html) collection.