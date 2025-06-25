---
layout: post
title: Appearance Customization in Syncfusion® Rating Control for Xamarin.iOS
description: Learn how to customize the appearance and styling of Rating control for Xamarin.iOS platform
platform: xamarin.ios
control: SfRating
documentation: ug
---

# Appearance Customization

You can customize the color, stroke width, and stroke color of rated and unrated items using the following properties of SfRatingSettings:

* `RatedFill`
* `UnRatedFill`
* `RatedStroke`
* `UnRatedStroke`
* `RatedStrokeWidth`
* `UnRatedStrokeWidth`

## Set Fill Color

The SfRating control has support to set the fill color for the selected and unselected items.

### Selected Items

The `RatedFill` property fills the rated area with the specified solid color in the SfRating control.

{% tabs %}

{% highlight c# %}

	SfRating rating = new SfRating();
	rating.Frame = new CGRect(10, 15, this.View.Frame.Width, this.View.Frame.Height);
	rating.Value = 3;
	SfRatingSettings ratingSettings = new SfRatingSettings();
	ratingSettings.RatedFill = UIColor.Red;
	rating.RatingSettings = ratingSettings;

{% endhighlight %}

{% endtabs %}

![Rated Item Fill Color](images/ratedFill.jpg)

### Unselected Items

The `UnRatedFill` property fills the unrated area with the specified solid color in the SfRating control.

{% tabs %}

{% highlight c# %}

	SfRating rating = new SfRating();
	rating.Frame = new CGRect(10, 15, this.View.Frame.Width, this.View.Frame.Height);
	rating.Value = 3;
	SfRatingSettings ratingSettings = new SfRatingSettings();
	ratingSettings.UnRatedFill = UIColor.Gray;
	rating.RatingSettings = ratingSettings;

{% endhighlight %}

{% endtabs %}

![Unrated Item Fill Color](images/unRatedFill.jpg)

## Set Stroke Color

The SfRating control has support to set the stroke color for the selected and unselected items.

### Selected Items

The `RatedStroke` property sets the stroke color for the rated area with the specified solid color in the SfRating control.

{% tabs %}

{% highlight c# %}

	SfRating rating = new SfRating();
	rating.Frame = new CGRect(10, 15, this.View.Frame.Width, this.View.Frame.Height);
	rating.Value = 2;
	SfRatingSettings ratingSettings = new SfRatingSettings();
	ratingSettings.RatedStroke = UIColor.Green;
	rating.RatingSettings = ratingSettings;

{% endhighlight %}

{% endtabs %}

![Rated Item Stroke Color](images/ratedstroke.png)

### Unselected Items

The `UnRatedStroke` property sets the stroke color for the unrated items with the specified solid color in the SfRating control.

{% tabs %}

{% highlight c# %}

	SfRating rating = new SfRating();
	rating.Frame = new CGRect(10, 15, this.View.Frame.Width, this.View.Frame.Height);
	rating.Value = 2;
	SfRatingSettings ratingSettings = new SfRatingSettings();
	ratingSettings.UnRatedStroke = UIColor.Green;
	rating.RatingSettings = ratingSettings;

{% endhighlight %}

{% endtabs %}

![Unrated Item Stroke Color](images/unratedstroke.png)
 
## Set Stroke Thickness

The SfRating control has support to set the stroke thickness for the selected and unselected items.

### Selected Items

The `RatedStrokeWidth` property sets the stroke thickness for the rated items with the specified value in the SfRating control.

{% tabs %}

{% highlight c# %}

	SfRating rating = new SfRating();
	rating.Frame = new CGRect(10, 15, this.View.Frame.Width, this.View.Frame.Height);
	rating.Value = 3;
	SfRatingSettings ratingSettings = new SfRatingSettings();
	ratingSettings.RatedFill = UIColor.Red;
	ratingSettings.RatedStroke = UIColor.Black;
	ratingSettings.RatedStrokeWidth = 5;
	rating.RatingSettings = ratingSettings;

{% endhighlight %}

{% endtabs %}

![Rated Item Stroke Thickness](images/ratedStrokeThickness.jpg)

### Unselected Items

The `UnRatedStrokeWidth` property sets the stroke thickness for the unrated area with the specified value in the SfRating control.

{% tabs %}

{% highlight c# %}

	SfRating rating = new SfRating();
	rating.Frame = new CGRect(10, 15, this.View.Frame.Width, this.View.Frame.Height);
	rating.Value = 3;
	SfRatingSettings ratingSettings = new SfRatingSettings();
	ratingSettings.UnRatedFill = UIColor.Gray;
	ratingSettings.UnRatedStroke = UIColor.Black;
	ratingSettings.UnRatedStrokeWidth = 3;
	rating.RatingSettings = ratingSettings;

{% endhighlight %}

{% endtabs %}

![Unrated Item Stroke Thickness](images/unRatedStrokeThickness.jpg)
