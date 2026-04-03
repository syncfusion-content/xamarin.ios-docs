---
layout: post
title: Animation duration in Syncfusion® Carousel control for Xamarin.iOS
description: Learn how to configure animation duration for smooth transitions in Carousel control for Xamarin.iOS applications.
platform: xamarin.ios
control: Carousel
documentation: ug
---

# Animation Duration

The `Duration` property of the SfCarousel control specifies the time required for an item to animate to the selected position during carousel transitions. This property controls the speed of the animation when users navigate between carousel items.

## Configuring Animation Duration

The duration value is specified in milliseconds, with a default value of 300 milliseconds. You can customize this value to create faster or slower transitions based on your application's requirements.
{% highlight C# %}

SfCarousel carousel = new SfCarousel();

carousel.Duration = 1000;

{% endhighlight %}

