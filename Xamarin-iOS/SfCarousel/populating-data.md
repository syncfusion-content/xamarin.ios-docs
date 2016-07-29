---
layout : post
title : Data source in Syncfusion Carousel control in Xamarin.iOS
description : Learn how to set the Data source in Carousel 
platform : Xamarin.iOS
control : Carousel
documentation : ug
---

# Populating Data

## Data Source

SfCarousel items can be populated with a collection of business objects. For example, a user may wants to create a SfCarousel control which will display a list of images.

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

## SelectedIndex

It gets or sets the Selected Item index value of SfCarousel control to bring the particular item to center of the screen.

N> The `SelectedIndex` property will be 0 by default.

{% highlight c# %}

	carousel.SelectedIndex=2;

{% endhighlight %}

