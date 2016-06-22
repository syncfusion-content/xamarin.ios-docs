---
layout: post
title: Set title to the Syncfusion BusyIndicator control for Xamarin.iOS
description: Learn how to set title and fontface to BusyIndicator control
platform: Xamarin.iOS
control: SfBusyIndicator
documentation: ug
---

# Title

The `Title` property can be used to get or set the content that indicates the information related to loading. The Title is displayed beneath the animation.A user customized string is displayed while showing animation. 

{% highlight c# %}

	SFBusyIndicator busyindicator = new SFBusyIndicator();
	busyindicator.AnimationType=SFBusyIndicatorAnimationType.SFBusyIndicatorAnimationTypeBattery;
	busyindicator.Title="Loading...";
	
{% endhighlight %} 

![](images/Title_img1.png)                  

BusyIndicator with title
{:.caption}


## FontFace

`FontFace` can be used to define the font style and font size that can be set to the title that is displayed beneath the animation.

{% highlight c# %}

	SFBusyIndicator busyindicator = new SFBusyIndicator();
	busyindicator.AnimationType=SFBusyIndicatorAnimationType.SFBusyIndicatorAnimationTypeBattery;
	busyindicator.Title="Loading...";
	busyindicator.Fontface=Typeface.create("Arial",Typeface.NONE);

{% endhighlight %}

![](images/Title_img2.png)                         

BusyIndicator with font face
{:.caption}
