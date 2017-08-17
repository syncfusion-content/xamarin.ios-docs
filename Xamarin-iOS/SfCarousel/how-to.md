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

For getting carousel event, need to inherits SFCarouselDelegate class as like below. All events definitions are mentioned only DelegateClass.

{% highlight C# %}

public class DelegateClass : SFCarouselDelegate
{
    public override void DidSelectItem(SFCarousel carousel, SFCarouselItem item)
    {
        base.DidSelectItem(carousel, item);
    }
}

{% endhighlight %}

### Delegate initialization

By initializing the CarouselDelegate with inherited class of SFCarouselDelegate, we can access the events on SFCarousel control.

{% highlight C# %}

carousel.CarouselDelegate = new DelegateClass();

{% endhighlight %}
