---
layout: post
title: Sizing support in Syncfusion® BusyIndicator control for Xamarin.iOS
description: This section provides details about how to customize the size of the animation for BusyIndicator in Xamarin.iOS
platform: xamarin.ios
control: SfBusyIndicator
documentation: ug
---

# BusyIndicator ViewBox Sizing

The drawing size of the SfBusyIndicator animation can be customized to fit your application's design requirements. The `ViewBoxHeight` and `ViewBoxWidth` properties allow you to set the height and width of the animation area, giving you precise control over the indicator's appearance.

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
