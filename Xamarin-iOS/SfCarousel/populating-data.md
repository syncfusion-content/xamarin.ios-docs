---
layout : post
title : Data source in Syncfusion Carousel control in Xamarin.iOS
description : Learn how to set the Data source in Carousel 
platform : Xamarin.iOS
control : Carousel
documentation : ug
---

# Populating Data

## DataSource with Collection of Images

SfCarousel items can be populated with a collection of business objects. For example, a user may wants to create a SfCarousel control which will display a list of images.

{% highlight c# %}

NSMutableArray<SFCarouselItem> carouselItemCollection = new NSMutableArray<SFCarouselItem> ();
for(int i=1;i<18;i++)
{
SFCarouselItem item =new SFCarouselItem();
item.ImageName="image"+i+".png";
carouselItemCollection.Add(item);
}
carousel.DataSource=carouselItemCollection;
	
{% endhighlight %}

## DataSource with Collection of custom view

SFCarousel items can be populated with a collection of business objects. It can be achieved by passing the custom view into View property in SFCarouselItem

{% highlight c# %}


SFCarousel carousel = new SFCarousel();

NSMutableArray<SFCarouselItem> listOfArray = new NSMutableArray<SFCarouselItem>();

for (int i = 1; i < 4; i++)
{
	SFCarouselItem items = new SFCarouselItem();
	UIImageView uiImageView = new UIImageView();
	uiImageView.Frame = new CGRect(0, 0, carousel.ItemWidth, carousel.ItemHeight);
	uiImageView.Image = new UIImage("Images/image"+i.ToString()+".png");
	items.View = uiImageView;
	listOfArray.Add(items);

}

carousel.DataSource = listOfArray;

View.AddSubview(carousel);


{% endhighlight %}

# SelectedIndex

It gets or sets the Selected Item index value of SfCarousel control to bring the particular item to center of the screen.

N> The `SelectedIndex` property will be 0 by default.

{% tabs %}

{% highlight c# %}

	carousel.SelectedIndex=2;

{% endhighlight %}

{% endtabs %}

