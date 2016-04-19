---
layout: post
title: Vertical Chart | SFChart | Xamarin.iOS | Syncfusion
description: How to show cartesian series vertically in SFChart
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Vertical Chart

Vertical chart is used to show the CartesianSeries vertically which helps to view the data in different
perceptive using `IsTransposed` property. 



{% highlight c# %}

SFLineSeries series   = new SFLineSeries ();

series.IsTransposed   = true;

return series; 

{% endhighlight %}

![](ChartSeries_images/VerticalChart.png)