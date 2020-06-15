---
layout: post
title: Sizing support in Syncfusion BusyIndicator control for Xamarin.iOS
description: This section provides the details about how to customize the size of the animation type for Xamarin.iOS
platform: Xamarin.iOS
control: SfBusyIndicator
documentation: ug
---

# BusyIndicator ViewBox Size

Drawing size can be customized in SfBusyIndicator. `ViewBoxHeight` and `ViewBoxWidth` properties can be used to set height and width of the Indicator.

{% tabs %}

{% highlight c# %}

SfBusyIndicator busyindicator = new SfBusyIndicator();
busyindicator.AnimationType = SFBusyIndicatorAnimationType.SFBusyIndicatorAnimationTypeSlicedCircle;
busyindicator.ViewBoxWidth = 200;
busyindicator.ViewBoxHeight = 200;
	
{% endhighlight %}

{% endtabs %}

![The Sizing_img1](images/Sizing_img1.png)                       

ViewBox height and width
{:.caption}
