---
layout: post
title: Appearance and Styling in Syncfusion® Rating Control for Xamarin.iOS
description: Learn how to change the appearance and styling properties of Rating control for Xamarin.iOS platform with customization options
platform: xamarin.ios
control: SfRating
documentation: ug
---

# Appearance and Styling

When the default view is not needed, you can customize the view of the Xamarin.iOS SfRating control. The SfRating control provides support to customize the size, item count, and space between rating items.

## Set Size

The `ItemSize` property sets the size of the rating items. 

> **Note:** By default, the property value is 50.

{% tabs %}

{% highlight c# %}
	   
	rating.ItemSize = 20;

{% endhighlight %}

{% endtabs %}

![SfRating Layout Customization](images/layoutSize.jpg)
 
## Set Number of Items

The `ItemCount` property sets the number of rating items to be displayed. 

> **Note:** The default property value is 5.

{% tabs %}

{% highlight c# %}

	rating.ItemCount = 4;

{% endhighlight %}

{% endtabs %}

![Set Number of Rating Items](images/fourstar.jpg)

## Set Space Between Items

The `ItemSpacing` property sets the spacing between the rating items. 

> **Note:** By default, the property value is 5.

{% tabs %}

{% highlight c# %}

	rating.ItemSpacing = 20;

{% endhighlight %}

{% endtabs %}

![Space Between Rating Items](images/layoutSpace.jpg)

## Rating Settings

For styling customization, set the `RatingSettings` property value with an SfRatingSettings object instance.

{% tabs %}

{% highlight c# %}

SfRating rating;
SfRatingSettings ratingSetings;

public override void ViewDidLoad()
{
	base.ViewDidLoad();
	rating = new SfRating();
	ratingSettings = new SfRatingSettings();
	ratingSettings.RatedFill = UIColor.Red;
	ratingSettings.UnRatedFill = UIColor.Blue;
	ratingSettings.RatedStrokeWidth = 5;
	ratingSettings.UnRatedStrokeWidth = 3;
	rating.RatingSettings = ratingSettings;
}
			
{% endhighlight %}

{% endtabs %}