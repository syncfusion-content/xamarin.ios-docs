---
layout: post
title: Appearance and Styling in Syncfusion Rating control for Xamarin.iOS
description: Learn how to change the Appearance and Styling of rating control
platform: Xamarin.iOS
control: Rating
documentation: ug
---

# Appearance and Styling

Different colors can be applied for rated and unrated items and its border in SfRating control.

## Set Fill Color

SfRating control has support to set the fill color for the selected and unselected items.

### Selected Items

The `RatedFill` property fills the rated area with the specified solid color in the SfRating control.

{% tabs %}

{% highlight c# %}

	ratingSetting.RatedFill=UIColor.FromRGB (251,209,10);

{% endhighlight %}

{% endtabs %}

![](images/ratedFill.jpg)

### Unselected Items

The `UnRatedFill` property fills the unrated area with the specified solid color in the SfRating control.

{% tabs %}

{% highlight c# %}

	ratingSetting.UnRatedFill=UIColor.Gray;

{% endhighlight %}

{% endtabs %}

![](images/unRatedFill.jpg)

## Set Stroke Color

SfRating control has support to set the stroke color for the selected and unselected items.

### Selected Items

The `RatedStroke` property sets the stroke for the rated area with the specified solid color in the SfRating control.

{% tabs %}

{% highlight c# %}

	ratingSetting.RatedStroke=UIColor.Green;

{% endhighlight %}

{% endtabs %}

![](images/ratedStroke.jpg)

### Unselected Items

The `UnRatedStroke` property sets the stroke for the unrated area with the specified solid color in the SfRating control.

{% tabs %}

{% highlight c# %}

	ratingSetting.UnRatedStroke=UIColor.Black;

{% endhighlight %}

{% endtabs %}

![](images/unRatedStroke.jpg)
 
## Set Stroke Thickness

SfRating control has support to set the stroke thickness for the selected and unselected items.

### Selected Items

The `RatedStrokeThickness` property sets the stroke thickness for the rated area with the specified value in the SfRating control.

{% tabs %}

{% highlight c# %}

	ratingSetting.RatedStrokeThickness=3;

{% endhighlight %}

{% endtabs %}

![](images/ratedStrokeThickness.jpg)

### Unselected Items

The `UnRatedStrokeThickness` property sets the stroke thickness for the unrated area with the specified value in the SfRating control.

{% tabs %}

{% highlight c# %}

	ratingSetting.UnRatedStrokeThickness=3;

{% endhighlight %}

{% endtabs %}

![](images/unRatedStrokeThickness.jpg)
