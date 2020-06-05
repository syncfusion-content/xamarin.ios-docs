---
layout: post
title: AnimationDuration in Syncfusion Carousel control in Xamarin.iOS
description: Learn how to set the Duration in Carousel for Xamarin.iOS
platform: Xamarin.iOS
control: Carousel
documentation: ug
---

# The Carousel Animation

The `Duration` property of the SfCarousel control is used to specify the time taken to move an item to the selected item position. The duration is specified in seconds.  The default value is 300 ms.

{% highlight C# %}

SfCarousel carousel = new SfCarousel();

carousel.Duration = 1000;

{% endhighlight %}

