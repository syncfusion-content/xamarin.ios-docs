---
layout : post
title : Getting Started with Syncfusion AutoComplete control for Xamarin.iOS
description : A quick tour to initial users on Syncfusion carousel control for Xamarin.iOS platform
platform : Xamarin.iOS
control : Carousel
documentation : ug
---

# Getting Started

This section provides a quick overview for working with Essential Carousel for Xamarin.iOS. It guides you to the entire process of creating a Carousel in your Application

![](images/carousel.png)


## Creating your first Carousel in Xamarin.iOS

## Referencing Essential Studio components in your solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:
{Syncfusion Installed location}\Essential Studio {version number}\lib
And below assembly reference to the iOS unified project.
iOS-unifed\Syncfusion.SfCarousel.iOS.dll

## Add and Configure the Carousel

* Adding reference to carousel.

{% highlight C# %}

	using Syncfusion.SFCarousel.iOS; 

{% endhighlight %}

* Create an instance for SfCarousel.

{% highlight C# %}

	SFCarousel carousel = new SFCarousel();
	this.AddSubview(carousel);

{% endhighlight %}

## Setting Offset

Set the Offset property to specify the distance between the items in Carousel panel.

{% highlight C# %}

	SFCarousel carousel = new SFCarousel();
	carousel.SelectedIndex=2;
	carousel.Offset=20;

{% endhighlight %}


## Setting Rotation Angle

Set the RotationAngle property to decide the angle in which items should be rotated.

{% highlight C# %}

	SFCarousel carousel = new SFCarousel();
	carousel.SelectedIndex=2;
	carousel.Offset=20;
	carousel.RotationAngle = 45;

{% endhighlight %}

## Setting DataSource

SfCarousel items can be populated with a collection of image data. For example, a user may want to create a SfCarousel control which will display a list of images.

{% highlight c# %}

	NSMutableArray<SFCarouselItem> carouselItemCollection = new NSMutableArray<SFCarouselItem> ();
	For(int i=1;i<18;i++)
	{
	SFCarouselItem item =new SFCarouselItem();
	item.ImageName="image"+i;
	carouselItemCollection.Add(item);
	}
	carousel.DataSource=carouselItemCollection;

{% endhighlight %}
