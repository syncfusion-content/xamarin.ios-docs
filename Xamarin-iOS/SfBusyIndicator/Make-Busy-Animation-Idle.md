---
layout: post
title: IsBusy support in Syncfusion BusyIndicator control for Xamarin.iOS
description: This section provides the details about how to enable and disable animation in BusyIndicator for Xamarin.iOS
platform: Xamarin.iOS
control: SfBusyIndicator
documentation: ug
---

# Make Busy Animation Idle

SfBusyIndicator control provides support to determine whether an animation needs to be executed or not. Setting the `IsBusy` property to false will stop the animation and removes the control from view. 

{% tabs %}

{% highlight c# %}

	SfBusyIndicator busyindicator = new SfBusyIndicator();
	busyindicator.AnimationType = SFBusyIndicatorAnimationType.SFBusyIndicatorAnimationTypeSingleCircle;
	busyindicator.IsBusy = true;

{% endhighlight %}

{% endtabs %}

![The IsBusy_img1](images/IsBusy_img1.png)                 

BusyIndicator
{:.caption}