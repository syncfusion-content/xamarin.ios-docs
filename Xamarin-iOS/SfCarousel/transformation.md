---
layout: post
title: Transformation in Syncfusion Carousel control in Xamarin.iOS
description: This section provides the details about how to set the Transformation in Carousel for Xamarin.iOS
platform: Xamarin.iOS
control: Carousel
documentation: ug
---

# Carousel Transformation

The Offset between selected and unselected item can be customized in SfCarousel control. And also the items can be scaled to the specified value.

## Tilt Non Selected Items

The `RotationAngle` property in the SfCarousel control is used to tilt all the unselected items in a specified angle. 

N> If the angle value is positive, then the rotation is in the clockwise direction. If the angle value is negative, the rotation is in the counterclockwise direction. 

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
carousel.RotationAngle = 40;

{% endhighlight %}

![The rotationangle](images/rotationangle.png)

## Set Gap between Unselected Items

The `Offset` property is used to specify the accurate distance between unselected items in SfCarousel panel.  

N> The default value is 20.

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
carousel.Offset = 30;

{% endhighlight %}

![The image](images/offset.png)

## Set Gap between Selected Item

Distance between the selected item and other items can be customized by using `SelectedItemOffset` property of the SfCarousel control.

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
carousel.SelectedItemOffset = 6;

{% endhighlight %}

## Set Scaling for Carousel Items

The `ScaleOffset` property in the SfCarousel control is used to scale all the items to the specified scale value.

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
carousel.ScaleOffset = (nfloat)0.7;

{% endhighlight %}

![The ScaleOffset](images/scaleoffset.png)

## Spacing of Items in Linear mode

Spacing of all the items in Linear mode can be determined by using `ItemSpacing` property.

N> The default value is 5. 

{% highlight C# %}

SfCarousel carousel = new SfCarousel();

carousel.ViewMode = SFCarouselViewMode.SFCarouselViewModeLinear;

carousel.ItemSpacing = 10;

{% endhighlight %}
