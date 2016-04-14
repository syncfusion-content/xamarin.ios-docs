---
layout: post
title: Performance Line Chart | SFChart | Xamarin.iOS | Syncfusion
description: Performance
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Performance

When there are large number of points to load in line series, you can use `SFFastLineSeries` series instead of `SFLineSeries`. To renderer a fast line chart, create an instance of `SFFastLineSeries` and add to `SFChart`.



{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFFastLineSeries series = new SFFastLineSeries ();

    return series;
}
{% endhighlight %}


N> Instead of enabling data markers and labels when there are large number of data points, you can use [**Trackball**](http://help.syncfusion.com/ios/sfchart/trackball) to view the point information.