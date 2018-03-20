---
layout: post
title: Performance Line Chart | SFChart | Xamarin.iOS | Syncfusion
description: Performance
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Performance

Following are the key points that can be used to boost the performance of the chart when there is a need to plot high volume data.

* When there are large number of points to load in line series, you can use [`SFFastLineSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFFastLineSeries.html) series instead of [`SFLineSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFLineSeries.html). To renderer a fast line chart, create an instance of [`SFFastLineSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFFastLineSeries.html) and add to [`SFChart`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChart.html).


{% highlight c# %}

SFFastLineSeries columnSeries = new SFFastLineSeries() { 
    
    ItemsSource = Data, 
    XBindingPath = "Country", 
    YBindingPath = "Value" 

};

{% endhighlight %}


N>If you have minimal set of data points, the recommended approach is to use normal line series to visualize those data using line chart. Because the normal line series has provisions to customize the color and shape of individual line.

* Instead of enabling data markers and labels when there are large number of data points, you can use [**Trackball**](https://help.syncfusion.com/xamarin-ios/sfchart/trackball) to view the point information.

* The default line width of the [`SFFastLineSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFFastLineSeries.html) is 2, reducing this to 1 will improve the performance. Refer the following code snippet to configure the line width of FastLineSeries.

{% highlight c# %}

SFFastLineSeries columnSeries = new SFFastLineSeries() { 
    
    ItemsSource = Data, 
    XBindingPath = "Country", 
    YBindingPath = "Value",
	LineWidth = 1 

};

{% endhighlight %}

* When your underlying data object implements INotifyPropertyChanged, you need to enable the ListenPropertyChange property of the series, to make the chart listen to the property changes of your data object. However enabling this property registers PropertyChanged event of every object in the data source. Due to this, chart’s loading time is affected when there are a large number of points. By default, ListenPropertyChange is set to false in order to avoid the event registration unnecessarily.

* Whenever there is a new data point is added to the [`ItemsSource`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~ItemsSource.html) property of [`SFSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries.html), the chart will be refreshed with new data point if the [`ItemsSource`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~ItemsSource.html) property is type of `ObservableCollection`. In order to avoid the chart rendering for each update in [`ItemsSource`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~ItemsSource.html), you can suspend the chart using [`SuspendSeriesNotification`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~SuspendNotification.html) method of chart and the [`ResumeSeriesNotification`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~ResumeNotification.html) should be called once the required data points are added to the collection and the chart should be refreshed with data points that have been added between these two method calls.

{% highlight c# %}

Chart.SuspendSeriesNotification();

// ...

// Add the data points to ItemsSource property.

// ...

Chart.ResumeSeriesNotification();

{% endhighlight %}

Similarly, you can use [`SuspendNotification`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~SuspendNotification.html) and [`ResumeNotification`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~ResumeNotification.html) methods of [`SFSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries.html) to suspend and resume the update of the respective series.

{% highlight c# %}

series.SuspendNotification();

// ...

// Add the data points to ItemsSource property.	

// ...

series.ResumeNotification();

{% endhighlight %}

