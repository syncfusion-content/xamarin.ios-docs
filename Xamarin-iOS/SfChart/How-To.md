---
layout: post
title: How to | SFChart | Xamarin.iOS | Syncfusion
description: getting started 
platform: xamarin.ios
control: SFChart
documentation: ug
---

# How to

## Get the visible range data points

CartesianSeries provides the following methods to get the visible range data points.

* [`GetDataPoints(RectangleF rect)`]() - Used to get the actual data points that are fall inside the given rectangle.
* [`GetDataPoints(double startX, double endX, double startY, double endY)`]() - Used to get the actual data points from the given range.

{% highlight c# %}

List<object> dataPoints = Series.GetDataPoints(rectangle);

List<object> ActualDataPoints = Series.GetDataPoints(startX, endX, startY, endY);

{% endhighlight  %}

N> You can also get the dataPoints based on x-range if rectangle height is given as Zero and also get the dataPoints based on y-range if rectangle width is given as Zero.
