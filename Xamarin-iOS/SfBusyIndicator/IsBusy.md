---
layout: post
title: IsBusy support in Syncfusion BusyIndicator control for Xamarin.iOS
description: Learn how to enable and disable animation in BusyIndicator
platform: Xamarin.iOS
control: SfBusyIndicator
documentation: ug
---

# IsBusy

The `IsBusy` property in the SFBusyIndicator control is used to determine whether an animation needs to be executed or not. 

{% highlight c# %}

	SFBusyIndicator busyindicator = new SFBusyIndicator();
	busyindicator.AnimationType=SFBusyIndicatorAnimationType.SFBusyIndicatorAnimationTypeSingleCircle;
	busyindicator.IsBusy=true;

{% endhighlight %}

![](images/IsBusy_img1.png)                 

BusyIndicator
{:.caption}