---
layout: post
title: Appearance and Styling in Syncfusion Rating control for Xamarin.iOS
description: Learn how to change the Appearance and Styling of rating control
platform: Xamarin.iOS
control: Rating
documentation: ug
---

# Appearance and Styling

## Item Size

The `ItemSize` property sets the size of the rating items. 

N> By default, property value is 50.

{% highlight c# %}
	   
	rating.ItemSize=20;

{% endhighlight %}

![](images/layoutSize.jpg)
 
## Item Spacing

The `ItemSpacing` property sets the spacing between the rating items. 

N> By default, property value is 5.

{% highlight c# %}

	rating.ItemSpacing=20;

{% endhighlight %}

![](images/layoutSpace.jpg)
 
## Number of Items

The `ItemCount` property sets the number of rating items to be displayed. 

N> The default property value is 5.

{% highlight c# %}

	rating.ItemCount=4;

{% endhighlight %}

![](images/fourstar.jpg)
 
## Read Only

Rating control provides support for changeable or unchangeable values for Rating control. This is achieved by the ReadOnly property. When this property is set to True, the Rating value becomes unchangeable. By default, this property value is set to False.

{% highlight c# %}

	rating.ReadOnly = true;

{% endhighlight %}

![](images/readOnly.jpg)
 
## RatingSettings

{% highlight c# %}

	SFRatingSettings ratingSetting = new SFRatingSettings ();
	ratingSetting.RatedFill = UIColor.FromRGB (251,209,10);
	ratingSetting.RatedStroke = UIColor.FromRGB (251,209,10);
    ratingSetting.RatedStrokeThickness=10;
	ratingSetting.UnRatedFill=UIColor.FromRGB (251,209,10);
	ratingSetting.UnRatedStrokeThickness=10;	
			
{% endhighlight %}

### Rated Fill

The RatedFill property fills the rated area with the specified solid color in the SfRating control.

{% highlight c# %}

	ratingSetting.RatedFill=Color.FromHex("#fbd10a");

{% endhighlight %}

![](images/ratedFill.jpg)

### Rated Stroke

The RatedStroke property sets the stroke for the rated area with the specified solid color in the SfRating control.

{% highlight c# %}

	ratingSetting.RatedStroke=Color.GREEN;

{% endhighlight %}

![](images/ratedStroke.jpg)
 
### Rated Stroke Thickness

The RatedStrokeThickness property sets the stroke thickness for the rated area with the specified value in the SfRating control.

{% highlight c# %}

	ratingSetting.RatedStrokeThickness=3;

{% endhighlight %}

![](images/ratedStrokeThickness.jpg)
 
### UnRated Fill

The UnRatedFill property fills the unrated area with the specified solid color in the SfRating control.

{% highlight c# %}

	ratingSetting.UnRatedFill=Color.GRAY;

{% endhighlight %}

![](images/unRatedFill.jpg)

### UnRated Stroke

The UnRatedStroke property sets the stroke for the unrated area with the specified solid color in the SfRating control.

{% highlight c# %}

	ratingSetting.UnRatedStroke=Color.BLACK;

{% endhighlight %}

![](images/unRatedStroke.jpg)

### UnRated Stroke Thickness

The UnRatedStrokeThickness property sets the stroke thickness for the unrated area with the specified value in the SfRating control.

{% highlight c# %}

	ratingSetting.UnRatedStrokeThickness=3;

{% endhighlight %}

![](images/unRatedStrokeThickness.jpg)
