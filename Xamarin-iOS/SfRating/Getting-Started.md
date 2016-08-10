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

## Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio {version number}\lib

Add the following assembly references to the iOS unified project,

iOS-unified\Syncfusion.SfRating.iOS.dll

## Add SfRating

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight c# %}
	
	using Syncfusion.SFRating.iOS;
	
{% endhighlight %}

{% endtabs %}

* Now add the SfRating control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight c# %}

	SFRating rating = new SFRating ();
	this.AddSubview(rating);
	
{% endhighlight %}

{% endtabs %}

* Configure the properties of Rating

{% tabs %}

{% highlight c# %}

    rating.ItemCount=5;
	rating.Precision = SFRatingPrecision.Half;
	rating.ToolTipPlacement= SFRatingToolTipPlacement.None;
	rating.ItemSize=10;
	rating.Readonly=true;
	rating.Value=(nfloat)3.5;
	rating.ItemSpacing = 5;

{% endhighlight %}

{% endtabs %}

## Set Value

Display value can be set in SfRating control which is selected among the items. The following example shows the display value of 3 with 5 rating items. 

N> By default, property value is 0.

{% tabs %}

{% highlight c# %}

    rating.Value=3;

{% endhighlight %}

{% endtabs %}

## Precision

SfRating control provides option to rate the items in full, half and exact value. This can be set through `Precision` property.

{% tabs %}

{% highlight c# %}

    rating.Precision =  SFRatingPrecision.Standard;

{% endhighlight %}

{% endtabs %}


![](images/gettingstarted.png)
