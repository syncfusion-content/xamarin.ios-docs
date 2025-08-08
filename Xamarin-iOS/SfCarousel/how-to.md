---
layout: post
title: Interaction in Syncfusion® Carousel Control in Xamarin.iOS
description: Learn how to perform operations while changing the carouselItem or Collection in Carousel for Xamarin.iOS.
platform: xamarin.ios
control: Carousel
documentation: ug
---

# How to perform operations while changing the carouselItem?

You can perform operations while changing the carouselItem using the `DidSelectItem` event. The `DidSelectItem` event returns the SfCarouselItem with the changed index.

## Delegate Definition

To receive carousel events, you need to inherit from the `SfCarouselDelegate` class as shown below. All event definitions are mentioned in the delegate class.

{% highlight C# %}

public class DelegateClass : SfCarouselDelegate
{
    public override void DidSelectItem(SfCarousel carousel, SfCarouselItem item)
    {
        base.DidSelectItem(carousel, item);
    }
}

{% endhighlight %}

## Delegate Initialization

By initializing the `CarouselDelegate` with an inherited class of `SfCarouselDelegate`, you can access the events on the SfCarousel control.

{% highlight C# %}

carousel.CarouselDelegate = new DelegateClass();

{% endhighlight %}
