---
layout: post
title: Set title to the Syncfusion® BusyIndicator control for Xamarin.iOS
description: This section provides details about how to set title and font properties for BusyIndicator control in Xamarin.iOS
platform: xamarin.ios
control: SfBusyIndicator
documentation: ug
---

# Set BusyIndicator Header

The SfBusyIndicator provides an option to set descriptive text that provides information about the current loading operation. This can be accomplished using the `Title` property, which displays text beneath the animation.


{% tabs %}

{% highlight c# %}

	SfBusyIndicator busyindicator = new SfBusyIndicator();
	busyindicator.AnimationType = SFBusyIndicatorAnimationType.SFBusyIndicatorAnimationTypeBattery;
	busyindicator.Title = (NSString)"Loading...";
	
{% endhighlight %} 

{% endtabs %}

![The Title_img1](images/Title_img1.png)                  

BusyIndicator with title
{:.caption}


## FontFace

`FontFace` can be used to define the font style and font size of the title that is displayed beneath the animation.

{% tabs %}

{% highlight c# %}

	SfBusyIndicator busyindicator = new SfBusyIndicator();
	busyindicator.AnimationType = SFBusyIndicatorAnimationType.SFBusyIndicatorAnimationTypeBattery;
	busyindicator.Title = "Loading...";
	busyindicator.FontFace = Typeface.create("Arial",Typeface.NONE);

{% endhighlight %}

{% endtabs %}

![The Title_img2](images/Title_img2.png)                         

BusyIndicator with font face
{:.caption}

