---
layout: post
title: IsBusy support in Syncfusion® BusyIndicator control for Xamarin.iOS
description: This section provides details about how to enable and disable animations in BusyIndicator for Xamarin.iOS
platform: xamarin.ios
control: SfBusyIndicator
documentation: ug
---

# Control Busy Animation State

The SfBusyIndicator control allows you to control whether animations are active or inactive using the `IsBusy` property. This property determines the visibility and animation state of the busy indicator.

## IsBusy Property

The `IsBusy` property is a boolean value that controls the animation state:

- **true**: Shows the busy indicator and starts the animation
- **false**: Hides the busy indicator and stops the animation

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