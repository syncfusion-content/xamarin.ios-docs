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


* Instead of enabling data markers and labels when there are large number of data points, you can use [**Trackball**](http://help.syncfusion.com/ios/sfchart/trackball) to view the point information.

* When your underlying data object implements INotifyPropertyChanged, you need to enable the ListenPropertyChange property of the series, to make the chart listen to the property changes of your data object. However enabling this property registers PropertyChanged event of every object in the data source. Due to this, chart’s loading time is affected when there are a large number of points. By default, ListenPropertyChange is set to false in order to avoid the event registration unnecessarily.

N>If you have minimal set of data points, the recommended approach is to use normal line series to visualize those data using line chart. Because the normal line series has provisions to customize the color and shape of individual line.
