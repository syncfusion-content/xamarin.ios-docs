---
layout : post
title : Interaction in Syncfusion Carousel Control in Xamarin.iOS.
description : Learn how to perform an operation while changing the carouselItem or Collection in Carousel for Xamarin.Android.
platform : Xamarin.iOS
control : Carousel
documentation : ug
---

# How to perform an operation while changing the carouselItem?

We can perform operation while changing the carouselItem using `DidSelectItem` event. DidSelectItem event returns the index changed SfCarouselItem.

### Delegate Definition:

For getting carousel event, need to inherits SfCarouselDelegate class as like below. All events definitions are mentioned only DelegateClass.

{% highlight C# %}

public class DelegateClass : SfCarouselDelegate
{
    public override void DidSelectItem(SfCarousel carousel, SfCarouselItem item)
    {
        base.DidSelectItem(carousel, item);
    }
}

{% endhighlight %}

### Delegate initialization

By initializing the CarouselDelegate with inherited class of SfCarouselDelegate, we can access the events on SfCarousel control.

{% highlight C# %}

carousel.CarouselDelegate = new DelegateClass();

{% endhighlight %}
