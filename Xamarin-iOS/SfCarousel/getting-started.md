---
layout : post
title : Getting Started with Syncfusion AutoComplete control for Xamarin.iOS
description : A quick tour to initial users on Syncfusion carousel control for Xamarin.iOS platform
platform : Xamarin.iOS
control : Carousel
documentation : ug
---

# Getting Started

This section provides a quick overview for working with Essential Carousel for Xamarin.iOS. It guides you to the entire process of creating a SfCarousel in your Application.

## Referencing Essential Studio components in your solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:
{Syncfusion Installed location}\Essential Studio {version number}\lib

And below assembly reference to the iOS unified project.
iOS-unifed\Syncfusion.SfCarousel.iOS.dll

## Add SfCarousel

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight C# %}

	using Syncfusion.SFCarousel.iOS; 

{% endhighlight %}

{% endtabs %}

* Now add the SfCarousel control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight C# %}

SFCarousel carousel = new SFCarousel();
this.AddSubview(carousel);

{% endhighlight %}

{% endtabs %}

## Add Carousel Items

SfCarousel items can be populated with a collection of image data. This collection includes Arrays, Lists and DataTables. An example to populate image collection as carousel items as follows

{% tabs %}

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

{% endtabs %}

## Set Gap between Items

SfCarousel provides option to set the distance between the items in the panel. This can be done by using the `Offset` property in SfCarousel control. 

{% tabs %}

{% highlight C# %}

SFCarousel carousel = new SFCarousel();
carousel.SelectedIndex=2;
carousel.Offset=20;

{% endhighlight %}

{% endtabs %}

## Tilt Non Selected Items

Items in the SfCarousel control can be rotated in user defined angle. `RotationAngle` property is used to decide the angle in which items should be rotated

{% tabs %}

{% highlight C# %}

SFCarousel carousel = new SFCarousel();
carousel.SelectedIndex=2;
carousel.Offset=20;
carousel.RotationAngle = 45;

{% endhighlight %}

{% endtabs %}

![](images/carousel.png)