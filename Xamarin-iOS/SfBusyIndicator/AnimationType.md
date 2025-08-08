---
layout: post
title: Animation Types in Syncfusion® BusyIndicator control for Xamarin.iOS
description: This section provides details about the various animation types available in Syncfusion® BusyIndicator for Xamarin.iOS
platform: xamarin.ios
control: SfBusyIndicator
documentation: ug
---

# BusyIndicator Animation Types

The `AnimationType` property for the SfBusyIndicator allows you to set one of the built-in animations available in the control. Each animation type provides a different visual style to indicate busy or loading states in your application.

## Setting Animation Type

You can set the animation type using the `AnimationType` property as shown below:

{% tabs %}

{% highlight c# %}

	SfBusyIndicator busyindicator = new SfBusyIndicator();
	busyindicator.AnimationType = SFBusyIndicatorAnimationType.SFBusyIndicatorAnimationTypeBall;
	
{% endhighlight %} 

{% endtabs %}

![The Ball Animation](images/Ball.png)                 

