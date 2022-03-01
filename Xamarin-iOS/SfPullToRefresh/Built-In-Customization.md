---
layout: post
title: Built-in customizations | SfPullToRefresh | Xamarin.iOS | Syncfusion
description: Built-in customizations in SfPullToRefresh
platform: Xamarin.iOS
control: SfPullToRefresh
documentation: ug
--- 

# Built-in Customizations

This section gives a quick overview of the various built-in customizations supported by SfPullToRefresh.

## Property settings

The various properties of SfPullToRefresh are listed as follows:

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

In the `TransitionType.SlideOnTop`, the progress view will render over the pullable content. It will be moved based on the pulling position whenever the pulling action is performed.

In the `TransitionType.Push`, the progress view will push the pullable content down thereby simultaneously moving the progress view and the pullable content based on the pulling position whenever the pulling action is performed.

Refer to the following code example to switch to the `TransitionType.Push` mode of transition:

{% highlight c# %}

pullToRefresh.TransitionType = TransitionType.Push;

{% endhighlight %}

### RefreshContentThreshold

The [SfPullToRefresh.RefreshContentThreshold](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_RefreshContentThreshold) serves different purpose based on the [SfPullToRefresh.TransitionType](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_TransitionType) is explained in the following table: 

<table width = "550">
<tr>
<th width="25%">TransitionType</th>
<th width="75%">Purpose</th>
</tr>
<tr>
<td width="25%">SlideOnTop</td>
<td width="75%">It denotes the starting Y-position of the progress view in the application.</td>
</tr>
<tr>
<td width="25%">Push</td>
<td width="75%">It denotes the Y-point after which pulling will be recognized.</td>
</tr>
</table>


The default value of the [SfPullToRefresh.RefreshContentThreshold](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_RefreshContentThreshold) is 17. 

N> For both the transition types, the progress view will be rendered in the application at the [SfPullToRefresh.RefreshContentThreshold](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_RefreshContentThreshold) property, when the refreshing animation is in progress.

Refer to the following code example to set the [SfPullToRefresh.RefreshContentThreshold](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_RefreshContentThreshold) property:

{% highlight c# %}

pullToRefresh.RefreshContentThreshold = 20;

{% endhighlight %}

### PullingThreshold

The [SfPullToRefresh.PullingThreshold](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_PullingThreshold) property indicates the maximum pullable position of the  progress view to reach 100 % of pulling progress. Refreshing will be started in the view only when the pulling progress reaches 100 % and touch is released. If the touch is released before the progress view reaches 100 % of pulling progress, pulling will be canceled and refreshing will not occur.

Refer to the following code example to set the [SfPullToRefresh.PullingThreshold](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_PullingThreshold) property:

{% highlight c# %}

pullToRefresh.PullingThreshold = 110;

{% endhighlight %}

The default value of the [SfPullToRefresh.PullingThreshold](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_PullingThreshold) is 90.

N> The [SfPullToRefresh.RefreshContentThreshold](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_RefreshContentThreshold) and the [SfPullToRefresh.PullingThreshold](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_PullingThreshold) should have a difference of at least 80. Only then the animations of the pullable content will be visible in the `TransitionType.Push` mode of animation.

### RefreshContentRadius

The radius of the progress view can be customized using the [SfPullToRefresh.RefreshContentRadius](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_RefreshContentRadius) property. The default value of the[SfPullToRefresh.RefreshContentRadius](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_RefreshContentRadius) is 20. 

Refer to the following code example to set the [SfPullToRefresh.RefreshContentRadius](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_RefreshContentRadius) property:

{% highlight c# %}

pullToRefresh.RefreshContentRadius = 25;

{% endhighlight %}

### ProgressStrokeWidth

The width of the inner stroke of the progress view can be customized using the [SfPullToRefresh.ProgressStrokeWidth](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_ProgressStrokeWidth) property. The default width of the inner stroke of the progress view is "2".

Refer to the following code example to set the [SfPullToRefresh.ProgressStrokeWidth](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_ProgressStrokeWidth) property:

{% highlight c# %}

pullToRefresh.ProgressStrokeWidth = 3;

{% endhighlight %}

### ProgressStrokeColor

The color of the inner stroke of the progress view is customizable. The default color of the inner stroke of the progress view is "Blue".

Refer to the following code example to set the [SfPullToRefresh.ProgressStrokeColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_ProgressStrokeColor) property:

{% highlight c# %}

pullToRefresh.ProgressStrokeColor = UIColor.Black;

{% endhighlight %}

### ProgressBackgroundColor

The background color of the progress view can be changed as per the requirement. The default background color of the progress view is "White".

Refer to the following code example to set the [SfPullToRefresh.ProgressBackgroundColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_ProgressBackgroundColor) property:

{% highlight c# %}

pullToRefresh.ProgressBackgroundColor = UIColor.Yellow;

{% endhighlight %}

### ProgressShadowColor

The shadow color of the progress view can be customized using the [SfPullToRefresh.ProgressShadowColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_ProgressShadowColor) property. The default background color of the progress view is "UIColor.LightGray". 

In cases, where the background color of the pullable content and the progress view are same, use the [SfPullToRefresh.ProgressShadowColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_ProgressShadowColor) to separate the progress view from the pullable content view to enhance the visual appearance of the application. 

Refer to the following code example to set the [SfPullToRefresh.ProgressShadowColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_ProgressShadowColor) property:

{% highlight c# %}

pullToRefresh.ProgressShadowColor = UIColor.LightYellow;

{% endhighlight %}

### Progress

The progress of pulling in SfPullToRefresh can be tracked using the [SfPullToRefresh.Progress](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_Progress) property. The progress of pulling is also provided in the [PullingEventArgs](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.PullingEventArgs.html) of the [SfPullToRefresh.Pulling](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html) event. Refer to the [Pulling Event](#pulling-event) topic for more details.

### IsRefreshing

The [SfPullToRefresh.IsRefreshing](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_IsRefreshing) flag returns a value indicating whether refreshing is being done or not. When the refreshing is started in the SfPullToRefresh, it returns true and once the refreshing is completed, it resets to false.

## Events in SfPullToRefresh

The three built-in events in SfPullToRefresh are as follows:

* [Pulling Event](#pulling-event)
* [Refreshing Event](#refreshing-event)
* [Refreshed Event](#refreshed-event)

### Pulling event

The pulling event will be fired continuously as long as the pulling action is performed in SfPullToRefresh. The progress of pulling can be tracked by the [PullingEventArgs.Progress](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.PullingEventArgs.html#Syncfusion_SfPullToRefresh_PullingEventArgs_Progress) property.

Refer to the following code example illustrating hooking of the [SfPullToRefresh.Pulling](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html) event:

{% highlight c# %}

pullToRefresh.Pulling += PullToRefresh_Pulling;

private void PullToRefresh_Pulling(object sender, PullingEventArgs e)
{
    progressOfPulling = e.Progress;
}

{% endhighlight %}

### Refreshing event

To refresh the view, hook the [SfPullToRefresh.Refreshing](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html) event. The [SfPullToRefresh.Refreshing](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html) event will be fired once the pulling progress reaches 100% and touch is released. You can do the required operations to refresh the view. Once the view is refreshed, set the [RefreshingEventArgs.Refreshed](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.RefreshingEventArgs.html#Syncfusion_SfPullToRefresh_RefreshingEventArgs_Refreshed) as <b>true</b> to stop the refreshing animation. 

Refer to the following code example illustrating hooking of the [SfPullToRefresh.Refreshing](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html) event and refreshing the view: 

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

### Refreshed event

The [SfPullToRefresh.Refreshed](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html) event will be fired once the refreshing animation is completed to indicate that the view is refreshed. 

Refer to the following code example illustrating hooking of the [SfPullToRefresh.Refreshed](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.RefreshingEventArgs.html#Syncfusion_SfPullToRefresh_RefreshingEventArgs_Refreshed) event:

{% highlight c# %}

pullToRefresh.Refreshed += PullToRefresh_Refreshed;

private void PullToRefresh_Refreshed(object sender, EventArgs e)
{
    //Event will be fired once the refreshing is completed, the user can do the needful here.
}

{% endhighlight %}

## Programmatic refresh

SfPullToRefresh supports refreshing the pullable content programmatically without interaction. To refresh the pullable content programmatically, call the [SfPullToRefresh.StartRefreshing()](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_StartRefreshing) method. To end programmatic refreshing, call the [SfPullToRefresh.EndRefreshing()](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_EndRefreshing) method.

Refer to the following code example to refresh the pullable content programmatically:

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

The following GIF demonstrates the programmatic refresh:

<div style="text-align:center" markdown="1">
![](built_in_customization_images\ProgrammaticRefresh_iOS.gif)
</div>
