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

	using Com.Syncfusion.Carousel; 

{% endhighlight %}

* Create an instance for SfCarousel.

{% highlight C# %}

	SfCarousel sfCarousel = new SfCarousel(this);
	SetContentView(sfCarousel);

{% endhighlight %}

## Setting Offset

Set the Offset property to specify the distance between the items in Carousel panel.

{% highlight C# %}

	SfCarousel sfCarousel = new SfCarousel();
	sfCarousel.SelectedIndex=2;
	sfCarousel.Offset=20;

{% endhighlight %}


## Setting Rotation Angle

Set the RotationAngle property to decide the angle in which items should be rotated.

{% highlight C# %}

	SfCarousel sfCarousel = new SfCarousel();
	sfCarousel.SelectedIndex=2;
	sfCarousel.Offset=20;
	SfCarousel.RotationAngle = 45;

{% endhighlight %}

## Setting DataSource

SfCarousel items can be populated with a collection of image datas. For example, a user may want to create a SfCarousel control which will display a list of images.

{% highlight c# %}

	ArrayList temp=new ArrayList();
	For(int i=1;i<18;i++)
	{
	SfCarouselItem item =new SfCarouselItem();
	item.ImageName="image"+i;
	temp.add(item);
	}
	carousel.DataSource=temp;

{% endhighlight %}
