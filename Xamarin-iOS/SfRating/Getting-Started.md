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

{Syncfusion Installed location}\Essential Studio {version number}\lib

Add the following assembly references to the iOS unified project,

iOS-unified\Syncfusion.SfRating.iOS.dll

### Add and Configure the Rating Control

* Adding reference to Autocomplete.

{% highlight c# %}
	
	using Syncfusion.SFRating.iOS;
	
{% endhighlight %}

* Create an instance of SfRating.

{% highlight c# %}

	SFRating rating = new SFRating ();
	this.AddSubview(rating);
	
{% endhighlight %}

* Configure the properties of Rating

{% highlight c# %}

    rating.ItemCount=5;
	rating.Precision = SFRatingPrecision.Half;
	rating.ToolTipPlacement= SFRatingToolTipPlacement.None;
	rating.ItemSize=10;
	rating.Readonly=true;
	rating.Value=(nfloat)3.5;
	rating.ItemSpacing = 5;

{% endhighlight %}

### Setting Value

* The `Value` property sets the display value of the rating. 

N> By default, property value is 0.

{% highlight c# %}

    rating.Value=3;

{% endhighlight %}

### Precision

* To enable full, half and exact values of rating, set the `Precision` property.

{% highlight c# %}

    rating.Precision = Precision.Standard;

{% endhighlight %}

![](images/standard.jpg)


