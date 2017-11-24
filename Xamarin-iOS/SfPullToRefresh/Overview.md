---
layout: post
title: Overview | SfPullToRefresh |Xamarin.iOS | Syncfusion
description: overview
platform: Xamarin.iOS
control: SfPullToRefresh
documentation: ug
---

# SfPullToRefresh

SfPullToRefresh is a refresh control that allows to interact and refresh the loaded view as pullable content. It supports loading complex and custom layouts that can be refreshed programmatically or through interaction.

# Key features:

* The view can be refereshed programmatically. Use [SfPullToRefresh.StartRefreshing()](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~StartRefreshing.html) to start the refreshing programmatically and [SfPullToRefresh.EndRefreshing()](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~EndRefreshing.html) to end the refershing programmatically.

* There are two types of transition for refreshing. You can toggle between the transition using the  [SfPullToRefresh.TransitionType](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~TransitionType.html) property. 

* The progress view can be customized. Size, background color, stroke color, and width of the stroke can be customized using the following properties: 
  * [SfPullToRefresh.RefreshContentRadius](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~RefreshContentRadius.html)
  * [SfPullToRefresh.ProgressBackgroundColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~ProgressBackgroundColor.html)
  * [SfPullToRefresh.ProgressStrokeColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~ProgressStrokeColor.html)
  * [SfPullToRefresh.ProgressStrokeWidth](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~ProgressStrokeWidth.html)

<div style="text-align:center" markdown="1">
![](overview_images/WeatherData_Refresh_iOS.gif)
</div>
