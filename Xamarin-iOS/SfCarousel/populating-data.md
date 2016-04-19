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

SfCarousel items can be populated with a collection of business objects. For example, a user may want to create a SfCarousel control which will display a list of images.

{% highlight c# %}

	ArrayList temp=new ArrayList();
	For(int i=1;i<18;i++)
	{
	varitem: SFCarousel = SFCarousel (); 
	item.ImageName="image";
	temp.Add(item);
	}
	carousel.DataSource=temp;
	
{% endhighlight %}

## SelectedIndex

It gets or sets the Selected Item index value of carousel control to bring the particular item to center of the screen.

N> The selectedIndex property will be 0 by default

{% highlight c# %}

	carousel.SelectedIndex=2;

{% endhighlight %}

