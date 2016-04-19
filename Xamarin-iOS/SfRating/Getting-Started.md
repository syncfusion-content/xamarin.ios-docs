---

layout: post
title: Getting Started with Syncfusion Rating control for Xamarin.iOS
description:  A quick tour to initial users on Syncfusion Rating control for Xamarin.iOS platform
platform: Xamarin.iOS
control: Rating
documentation: ug

---

# Getting Started

This section explains you the steps to configure a rating control in a real-time scenario and also provides a walk-through on some of the customization features available in Rating control.

![](images/gettingstarted.png)

## Creating your First Rating in Xamarin.iOS

### Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly references to the iOS unified project,

iOS-unified\Syncfusion.SfRating.iOS.dll

### Add and Configure the Rating Control

* Create an instance of SfRating.

{% highlight c# %}

	SfRating sfRating = new SfRating ();
	SetContentView(sfRating);
	
{% endhighlight %}

* Configure the properties of Rating

{% highlight c# %}

    sfRating.ItemCount=5;
	sfRating.Precision = SFRatingPrecision.Half;
	sfRating.ToolTipPlacement= SFRatingToolTipPlacement.None;
	sfRating.ItemSize=10;
	sfRating.Readonly=true;
	sfRating.Value=(nfloat)3.5;
	sfRating.ItemSpacing = 5;

{% endhighlight %}

### Setting Value

* The `Value` property sets the display value of the rating. 

N> By default, property value is 0.

{% highlight c# %}

    sfRating.Value=3;

{% endhighlight %}

### Precision

* To enable full, half and exact values of rating, set the `Precision` property.

{% highlight c# %}

    sfRating.Precision = Precision.Standard;

{% endhighlight %}

![](images/standard.jpg)


