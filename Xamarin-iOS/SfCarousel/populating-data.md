---
layout: post
title: Data source in Syncfusion® Carousel control in Xamarin.iOS
description: This section provides details about populating the data source with Carousel control for Xamarin.iOS
platform: xamarin.ios
control: Carousel
documentation: ug
---

# Populating Data Source

The SfCarousel control supports multiple ways to populate data, allowing you to display collections of images or custom views based on your application requirements.
## Data Source with Collection of Images

SfCarousel items can be populated with a collection of business objects. For example, you may want to create an SfCarousel control that displays a list of images.

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

## Data Source with Collection of Custom Views

SfCarousel items can also be populated with custom views for more complex layouts. This can be achieved by passing a custom view to the `View` property in `SfCarouselItem`.

{% highlight c# %}


SfCarousel carousel = new SfCarousel();

NSMutableArray<SfCarouselItem> listOfArray = new NSMutableArray<SfCarouselItem>();

for (int i = 1; i < 4; i++)
{
	SfCarouselItem items = new SfCarouselItem();
	UIImageView uiImageView = new UIImageView();
	uiImageView.Frame = new CGRect(0, 0, carousel.ItemWidth, carousel.ItemHeight);
	uiImageView.Image = new UIImage("Images/image"+i.ToString()+".png");
	items.View = uiImageView;
	listOfArray.Add(items);

}

carousel.DataSource = listOfArray;

View.AddSubview(carousel);


{% endhighlight %}

## Carousel SelectedIndex

It gets or sets the Selected Item index value of SfCarousel control to bring the particular item to center of the screen.

N> The `SelectedIndex` property will be 0 by default.

{% tabs %}

{% highlight c# %}

	carousel.SelectedIndex = 2;

{% endhighlight %}

{% endtabs %}

