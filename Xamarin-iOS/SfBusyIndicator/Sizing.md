---
layout: post
title: Sizing support in Syncfusion BusyIndicator control for Xamarin.iOS
description: Learn how to customize the size of the animation type
platform: Xamarin.iOS
control: SfBusyIndicator
documentation: ug
---



# Sizing

ViewBox is used for sizing an animation.It is achieved by,

* ViewBoxHeight
* ViewBoxWidth

`ViewBoxHeight` allows you to set the height of the animation and `ViewBoxWidth` allows to set the width of the animation.

{% highlight c# %}

	SfBusyIndicator busyindicator = new SfBusyIndicator(this);
	busyindicator.AnimationType=AnimationTypes.SlicedCircle;
	busyindicator.ViewBoxWidth=200;
	busyindicator.ViewBoxHeight=200;
	
{% endhighlight %}

![](images/Sizing_img1.png)                       

ViewBox height and width
{:.caption}
