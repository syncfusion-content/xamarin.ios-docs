---
layout: post
title: Appearance and Styling in Syncfusion Rating control for Xamarin.iOS
description: Learn how to change the Appearance and Styling of rating control
platform: Xamarin.iOS
control: Rating
documentation: ug
---

# Appearance and Styling

SfRating control provides support to customize the Size, Item count and space between rating items.

## Set Size

The `ItemSize` property sets the size of the rating items. 

N> By default, property value is 50.

{% tabs %}

{% highlight c# %}
	   
	rating.ItemSize=20;

{% endhighlight %}

{% endtabs %}

![](images/layoutSize.jpg)
 
## Set Number of Items

The `ItemCount` property sets the number of rating items to be displayed. 

N> The default property value is 5.

{% tabs %}

{% highlight c# %}

	rating.ItemCount=4;

{% endhighlight %}

{% endtabs %}

![](images/fourstar.jpg) 

## Set Space between Items

The `ItemSpacing` property sets the spacing between the rating items. 

N> By default, property value is 5.

{% tabs %}

{% highlight c# %}

	rating.ItemSpacing=20;

{% endhighlight %}

{% endtabs %}

![](images/layoutSpace.jpg) 

## Rating Settings

For styling customization, set the RatingSettings property value with SfRatingSettings object instance.

{% tabs %}

{% highlight c# %}

	SFRatingSettings settings = new SFRatingSettings ();
	settings.RatedFill = UIColor.FromRGB (251,209,10);
	settings.RatedStroke = UIColor.FromRGB (251,209,10);
    settings.RatedStrokeThickness=10;
	settings.UnRatedFill=UIColor.FromRGB (251,209,10);
	settings.UnRatedStrokeThickness=10;
	rating.RatingSettings=settings;	
			
{% endhighlight %}

{% endtabs %}

