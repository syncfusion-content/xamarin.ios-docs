---
layout: post
title: Set title to the Syncfusion BusyIndicator control for Xamarin.iOS
description: Learn how to set title and fontface to BusyIndicator control
platform: Xamarin.iOS
control: SfBusyIndicator
documentation: ug
---

# Set Header

SfBusyIndicator provides option to set the text that indicates the information related to loading. This can be done using `Title` property.

{% tabs %}

{% highlight c# %}

	SFBusyIndicator busyindicator = new SFBusyIndicator();
	busyindicator.AnimationType=SFBusyIndicatorAnimationType.SFBusyIndicatorAnimationTypeBattery;
	busyindicator.Title=(NSString)"Loading...";
	
{% endhighlight %} 

{% endtabs %}

![](images/Title_img1.png)                  

BusyIndicator with title
{:.caption}


## FontFace

`FontFace` can be used to define the font style and font size of the title that is displayed beneath the animation.

{% tabs %}

{% highlight c# %}

	SFBusyIndicator busyindicator = new SFBusyIndicator();
	busyindicator.AnimationType=SFBusyIndicatorAnimationType.SFBusyIndicatorAnimationTypeBattery;
	busyindicator.Title="Loading...";
	busyindicator.Fontface=Typeface.create("Arial",Typeface.NONE);

{% endhighlight %}

{% endtabs %}

![](images/Title_img2.png)                         

BusyIndicator with font face
{:.caption}
