---
layout: post
title: Transformation in Syncfusion® Carousel control in Xamarin.iOS
description: This section provides details about how to set transformations for Carousel items in Carousel for Xamarin.iOS
platform: xamarin.ios
control: Carousel
documentation: ug
---

# Carousel Transformation

The SfCarousel control provides various transformation options to customize the appearance and positioning of carousel items. You can adjust the offset between selected and unselected items, apply scaling effects, and control rotation angles for enhanced visual presentation.
## Tilt Non-Selected Items

The `RotationAngle` property in the SfCarousel control is used to tilt all unselected items at a specified angle, creating a dynamic visual effect.

> **Note:** If the angle value is positive, the rotation is clockwise. If the angle value is negative, the rotation is counterclockwise.

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
carousel.RotationAngle = 40;

{% endhighlight %}

![The rotationangle](images/rotationangle.png)

## Set Gap Between Unselected Items

The `Offset` property is used to specify the distance between unselected items in the SfCarousel panel, allowing you to control the spacing for optimal visual presentation.

N> The default value is 20.

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
carousel.Offset = 30;

{% endhighlight %}

![The image](images/offset.png)

## Set Gap Between Selected Item and Others

The distance between the selected item and other items can be customized using the `SelectedItemOffset` property of the SfCarousel control. This helps emphasize the selected item by creating additional space around it.

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
carousel.SelectedItemOffset = 6;

{% endhighlight %}

## Set Scaling for Carousel Items

The `ScaleOffset` property in the SfCarousel control is used to scale all items to a specified scale value, creating size variations that enhance the visual hierarchy.

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
carousel.ScaleOffset = (nfloat)0.7;

{% endhighlight %}

![The ScaleOffset](images/scaleoffset.png)

## Spacing of Items in Linear Mode

When using Linear view mode, the spacing between all items can be controlled using the `ItemSpacing` property. This provides precise control over item arrangement in linear layouts.
> **Note:** The default value is 5.

N> The default value is 5. 

{% highlight C# %}

SfCarousel carousel = new SfCarousel();

carousel.ViewMode = SFCarouselViewMode.SFCarouselViewModeLinear;

carousel.ItemSpacing = 10;

{% endhighlight %}
