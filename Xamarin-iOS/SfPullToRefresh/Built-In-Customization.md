---
layout: post
title: Built-in customizations | SfPullToRefresh | Xamarin.iOS | Syncfusion
description: Built-in customizations in SfPullToRefresh
platform: Xamarin.iOS
control: SfPullToRefresh
documentation: ug
--- 

# Built-in customizations

This section gives a quick overview of the various built-in customizations supported by SfPullToRefresh.

## Property Settings

The various properties of SfPullToRefresh are listed below:

* [TransitionType](#transitiontype)
* [RefreshContentThreshold](#refreshcontentthreshold)
* [PullingThreshold](#pullingthreshold)
* [RefreshContentRadius](#refreshcontentradius)
* [ProgressStrokeWidth](#progressstrokewidth)
* [ProgressStrokeColor](#progressstrokecolor)
* [ProgressBackgroundColor](#progressbackgroundcolor)
* [ProgressShadowColor](#progressshadowcolor)
* [Progress](#progress)
* [IsRefreshing](#isrefreshing)

### TransitionType

In the `TransitionType.SlideOnTop`, the progress view will render over the pullable content and it will be moved based on the pulling position, whenever the pulling action is performed.

In the `TransitionType.Push`, the progress view will push the pullable content down and simultaneously moves the refresh content and the pullable content based on the pulling position, whenever the pulling action is performed. 

Refer the below code example to switch to the `TransitionType.Push` mode of transition.

{% highlight c# %}

pullToRefresh.TransitionType = TransitionType.Push;

{% endhighlight %}

### RefreshContentThreshold

The [SfPullToRefresh.RefreshContentThreshold](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~RefreshContentThreshold.html) serves different purpose based on the [SfPullToRefresh.TransitionType](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~TransitionType.html) which is explained in the below table: 

<table width = "700">
<tr>
<th width="20%">TransitionType</th>
<th width="80%">Purpose</th>
</tr>
<tr>
<td width="20%">SlideOnTop</td>
<td width="80%">It decides the starting Y-position of the progress view in the application.</td>
</tr>
<tr>
<td width="20%">Push</td>
<td width="80%">It decides the touch-down point for pulling to be recognized.</td>
</tr>
</table>

The default value of [SfPullToRefresh.RefreshContentThreshold](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~RefreshContentThreshold.html) is 17. 

N> For both the transition types, the refresh content progress view will be rendered in the application at [SfPullToRefresh.RefreshContentThreshold](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~RefreshContentThreshold.html) property, when the refreshing animation is in progress.

Refer the below code example to set the [SfPullToRefresh.RefreshContentThreshold](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~RefreshContentThreshold.html) property.

{% highlight c# %}

pullToRefresh.RefreshContentThreshold = 20;

{% endhighlight %}

### PullingThreshold

The [SfPullToRefresh.PullingThreshold](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~PullingThreshold.html) property indicates the maximum pullable position of the refresh content progress view, to reach 100 % of pulling progress. Refreshing will be started in the view only when the pulling progress reaches 100 % and the touch is released. If the touch is released before the refresh content reaches 100 % of pulling progress, pulling will be canceled and hence refreshing will not be started.

Refer the below code example to set the [SfPullToRefresh.PullingThreshold](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~PullingThreshold.html) property.

{% highlight c# %}

pullToRefresh.PullingThreshold = 110;

{% endhighlight %}

The default value of [SfPullToRefresh.PullingThreshold](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~PullingThreshold.html) is 90.

N> [SfPullToRefresh.RefreshContentThreshold](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~RefreshContentThreshold.html) and [SfPullToRefresh.PullingThreshold](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~PullingThreshold.html) should have a difference of at least 80, then only the animations of the pullable content will be visible in `TransitionType.Push` mode of animation.

### RefreshContentRadius

The radius of the refresh content can be customized using [SfPullToRefresh.RefreshContentRadius](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~RefreshContentRadius.html) property. The default value of [SfPullToRefresh.RefreshContentRadius](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~RefreshContentRadius.html) is 20. 

Refer the below code example to set the [SfPullToRefresh.RefreshContentRadius](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~RefreshContentRadius.html) property.

{% highlight c# %}

pullToRefresh.RefreshContentRadius = 25;

{% endhighlight %}

### ProgressStrokeWidth

The width of the inner stroke of the refresh content can be customized using the [SfPullToRefresh.ProgressStrokeWidth](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~ProgressStrokeWidth.html) property. The default width of the inner stroke of the refresh content (circular progress view) is "2".

Refer the below code example to set the [SfPullToRefresh.ProgressStrokeWidth](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~ProgressStrokeWidth.html) property.

{% highlight c# %}

pullToRefresh.ProgressStrokeWidth = 3;

{% endhighlight %}

### ProgressStrokeColor

The color of the inner stroke of the refresh content is customizable. The default color of the inner stroke of the refresh content is "Blue".

Refer the below code example to set the [SfPullToRefresh.ProgressStrokeColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~ProgressStrokeColor.html) property.

{% highlight c# %}

pullToRefresh.ProgressStrokeColor = UIColor.Black;

{% endhighlight %}

### ProgressBackgroundColor

The background color of the refresh content can be changed as per the requirement. The default background color of the refresh content is "White".

Refer the below code example to set the [SfPullToRefresh.ProgressBackgroundColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~ProgressBackgroundColor.html) property.

{% highlight c# %}

pullToRefresh.ProgressBackgroundColor = UIColor.Yellow;

{% endhighlight %}

### ProgressShadowColor

The shadow color of the progress view can be customized using [SfPullToRefresh.ProgressShadowColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~ProgressShadowColor.html) property. The default background color of the refresh content is "UIColor.LightGray". 

In cases, where the background color of the pullable content and the refresh content are same, use the progress shadow color to separate the refresh content view from the pullable content view, which enhances the visual appearance of the application. 

Refer the below code example to set the [SfPullToRefresh.ProgressShadowColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~ProgressShadowColor.html) property.

{% highlight c# %}

pullToRefresh.ProgressShadowColor = UIColor.LightYellow;

{% endhighlight %}

### Progress

The progress of pulling in SfPullToRefresh can be tracked using [SfPullToRefresh.Progress](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~Progress.html) property. The progress of pulling is also provided in the [PullingEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.PullingEventArgs.html) of the [SfPullToRefresh.Pulling](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~Pulling_EV.html) event. Refer the topic [Pulling Event](#pulling-event) for more details regarding it.

### IsRefreshing

The [SfPullToRefresh.IsRefreshing](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~IsRefreshing.html) flag returns a value indicating whether refreshing is being done or not. When the refreshing is started in the SfPullToRefresh, it returns true and once the refreshing is completed, it resets to false.

## Events in SfPullToRefresh

There are three built-in events in SfPullToRefresh, which are listed below:

* [Pulling Event](#pulling-event)
* [Refreshing Event](#refreshing-event)
* [Refreshed Event](#refreshed-event)

### Pulling Event

The pulling event will be fired continuously as long as the pulling action is performed in the SfPullToRefresh. The progress of pulling can be tracked by the [PullingEventArgs.Progress](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.PullingEventArgs~Progress.html) property.

Refer the below code example which illustrates hooking the [SfPullToRefresh.Pulling](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~Pulling_EV.html) event. 

{% highlight c# %}

pullToRefresh.Pulling += PullToRefresh_Pulling;

private void PullToRefresh_Pulling(object sender, PullingEventArgs e)
{
    progressOfPulling = e.Progress;
}

{% endhighlight %}

### Refreshing Event

To refresh the view, the user should hook the [SfPullToRefresh.Refreshing](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~Refreshing_EV.html) event. The [SfPullToRefresh.Refreshing](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~Refreshing_EV.html) event will be fired, once the pulling progress reaches 100% and the touch is released. The user can do the required operations to refresh the view and once the view is refreshed, set the [RefreshingEventArgs.Refreshed](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.RefreshingEventArgs~Refreshed.html) as <b>true</b> to stop the refreshing animation. 

Refer the below code example which illustrates hooking the [SfPullToRefresh.Refreshing](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~Refreshing_EV.html) event and refresh the view. 

{% highlight c# %}

//MyViewController.cs

public MyViewController()
{
    ....
    //Hooking the Refreshing event.
    pullToRefresh.Refreshing += PullToRefresh_Refreshing;
    ....
}

private void PullToRefresh_Refreshing(object sender, RefreshingEventArgs e)
{
    NSTimer.CreateScheduledTimer(TimeSpan.FromSeconds(3), new Action<NSTimer>(delegate {
        baseView.model.Temperature = (NSString)new Random().Next(10, 40).ToString();
        baseView.UpdateBaseView();
        e.Refreshed = true;
    }));
}

{% endhighlight %}

### Refreshed Event

The [SfPullToRefresh.Refreshed](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~Refreshed_EV.html) event will be fired once the refreshing animation is completed, to indicate that the view is refreshed. 

Refer the below code example which illustrates hooking the [SfPullToRefresh.Refreshed](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.RefreshingEventArgs~Refreshed.html) event.

{% highlight c# %}

pullToRefresh.Refreshed += PullToRefresh_Refreshed;

private void PullToRefresh_Refreshed(object sender, EventArgs e)
{
    //Event will be fired once the refreshing is completed, the user can do the needful here.
}

{% endhighlight %}

## Programmatic Refresh

SfPullToRefresh supports refreshing the pullable content programmatically, without interaction. To refresh, the pullable content programmatically call the [SfPullToRefresh.StartRefreshing()](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~StartRefreshing.html) method and to end the programmatic refresh, call the [SfPullToRefresh.EndRefreshing()](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~EndRefreshing.html) method.

Refer the below code example to refresh the pullable content programmatically.

{% highlight c# %}

private async void PerformRefreshing()
{
    //Starts the refreshing.
    pullToRefresh.StartRefreshing();
    NSTimer.CreateScheduledTimer(TimeSpan.FromSeconds(3), new Action<NSTimer>(delegate
    {
        baseView.model.Temperature = (NSString)new Random().Next(10, 40).ToString();
        baseView.UpdateBaseView();
        //Ends the refreshing.
        pullToRefresh.EndRefreshing();
    }));
}

{% endhighlight %}
