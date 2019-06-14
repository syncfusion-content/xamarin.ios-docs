---
layout: post
title: Appearance and Styling in Syncfusion Rating control for Xamarin.iOS
description: Learn how to change the Appearance and Styling of rating control
platform: Xamarin.iOS
control: Rating
documentation: ug
---

# Appearance and Styling

You can customize the color, stroke width, and stroke color of rated and unrated items using the following properties of SfRatingSettings:

* `RatedFill`
* `UnRatedFill`
* `RatedStroke`
* `UnRatedStroke`
* `RatedStrokeWidth`
* `UnRatedStrokeWidth`

## Set Fill Color

SfRating control has support to set the fill color for the selected and unselected items.

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

![Rated item fill color](images/ratedFill.jpg)

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

![Unrated item fill color](images/unRatedFill.jpg)

## Set Stroke Color

SfRating control has support to set the stroke color for the selected and unselected items.

### Selected Items

The `RatedStroke` property sets the stroke for the rated area with the specified solid color in the SfRating control.

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

![Rated item stroke color](images/ratedstroke.png)

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

![Unrated item stroke color](images/unratedstroke.png)
 
## Set Stroke Thickness

SfRating control has support to set the stroke thickness for the selected and unselected items.

### Selected Items

The `RatedStrokeWidth` property sets stroke thickness to the rated items with the specified value in the SfRating control.

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

![Rated item stroke thickness](images/ratedStrokeThickness.jpg)

### Unselected Items

The `UnRatedStrokeWidth` property sets stroke thickness to the unrated area with the specified value in the SfRating control.

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

![Unrated item stroke thickness](images/unRatedStrokeThickness.jpg)
