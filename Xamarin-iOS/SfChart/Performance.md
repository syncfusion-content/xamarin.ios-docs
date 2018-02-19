---
layout: post
title: Performance Line Chart | SFChart | Xamarin.iOS | Syncfusion
description: Performance
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Performance

When there are large number of points to load in line series, you can use [`SFFastLineSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFFastLineSeries.html) series instead of [`SFLineSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFLineSeries.html). To renderer a fast line chart, create an instance of [`SFFastLineSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFFastLineSeries.html) and add to [`SFChart`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChart.html).



{% highlight c# %}

SFFastLineSeries columnSeries = new SFFastLineSeries() { 
    
    ItemsSource = Data, 
    XBindingPath = "Country", 
    YBindingPath = "Value" 

};

{% endhighlight %}


N> Instead of enabling data markers and labels when there are large number of data points, you can use [**Trackball**](http://help.syncfusion.com/ios/sfchart/trackball) to view the point information.