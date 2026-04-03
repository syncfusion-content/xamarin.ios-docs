---
layout: post
title: Getting Started with Syncfusion® Carousel control for Xamarin.iOS
description: This section provides details for new users getting started with Syncfusion® carousel control for Xamarin.iOS platform
platform: xamarin.ios
control: Carousel
documentation: ug
---

# Getting Started with Carousel

This section provides a quick overview for working with Essential<sup>®</sup> Carousel for Xamarin.iOS. It guides you through the entire process of creating an SfCarousel in your application.

## Referencing Essential Studio<sup>®</sup> components in your solution

After installing Essential Studio<sup>®</sup> for Xamarin, you can find all the required assemblies in the installation folders, typically:
{Syncfusion Installed location}\Essential Studio {version number}\lib

Add the following assembly reference to the iOS unified project:

iOS-unified\Syncfusion.SfCarousel.iOS.dll

## Add SfCarousel

* Add the namespace for the referenced assemblies:


{% highlight C# %}

using Syncfusion.SfCarousel.iOS; 

{% endhighlight %}

* Now add the SfCarousel control using the included namespace:

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
this.AddSubview(carousel);

{% endhighlight %}

## Add Carousel Items

SfCarousel items can be populated with a collection of image data. The following example shows how to populate an image collection as carousel items:

{% highlight c# %}

NSMutableArray<SfCarouselItem> carouselItemCollection = new NSMutableArray<SfCarouselItem> ();
for(int i=1;i<18;i++)
{
    SfCarouselItem item = new SfCarouselItem();
    item.ImageName = "image"+i+".png";
    carouselItemCollection.Add(item);
}
carousel.DataSource = carouselItemCollection;

{% endhighlight %}

## Set Gap between Items

SfCarousel provides an option to set the distance between items in the panel. This can be done using the `Offset` property in the SfCarousel control.

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
carousel.SelectedIndex = 2;
carousel.Offset = 20;

{% endhighlight %}

## Setting the Height and Width of Carousel Items

The `ItemHeight` and `ItemWidth` properties are used to change the height and width of carousel items in the carousel panel.

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
carousel.ItemWidth = 150;
carousel.ItemHeight = 170;

{% endhighlight %}

## Tilt Non-Selected Items

Items in the SfCarousel control can be rotated at a user-defined angle. The `RotationAngle` property is used to specify the angle at which items should be rotated.

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
carousel.SelectedIndex = 2;
carousel.Offset = 20;
carousel.RotationAngle = 45;

{% endhighlight %}

![Overview Image](images/carousel.png)
You can find the complete getting started sample from this [link.](https://www.syncfusion.com/downloads/support/directtrac/general/ze/CarouselSample-473851751)
