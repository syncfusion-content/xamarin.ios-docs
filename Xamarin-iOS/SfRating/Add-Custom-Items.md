---
layout: post
title: Adding Custom items in Syncfusion Rating Itmes control for Xamarin.iOS
description: Learn how to add the Custom Items in rating control
platform: Xamarin.iOS
control: Rating
documentation: ug
---

# Custom Views

SfRating Items control provides support to add custom views.

## Add SfRating Items

Add the SfRating Items control with a required optimal name by using the included namespace.

{% highlight C# %}

SfRating rating= new SfRating(); 

SfRatingItem item = new SfRatingItem(rating);

{% endhighlight %}

## Set Selected View
 
The `SelectedView` property is used to apply the given SelectedView to selected rating item.

{% highlight C# %}

	var imageView = new UIImageView(View.Frame);
	imageView.Image = UIImage.FromBundle("Angry_selected");
	item.SelectedView = imageView;

{% endhighlight %}

## Set UnSelected View
 
The `UnSelectedView` property is used to apply the given UnSelectedView to unselected rating items.

{% highlight C# %}

	var imageView2 = new UIImageView(View.Frame);
	imageView2.Image = UIImage.FromBundle("Angry_Unselected");
	item.UnSelectedView = imageView2;

{% endhighlight %}

## Add Items

The `Items` property is used to hold the collection of SfRatingItem. 

N> SfRatingItem keeps both selected and unselected view respectively.

{% highlight C# %}

	NSMutableArray collection = new NSMutableArray();
	collection.Add(item);
	rating.Items = collection;

{% endhighlight %}

## Enable Custom Items

When `EnableCustomItems` property is enabled, it will display the custom items added in the rating item. 

{% highlight C# %}
	
	SfRating rating= new SfRating();
	SfRatingItem item = new SfRatingItem(rating);
		var imageView = new UIImageView(View.Frame);
		imageView.Image = UIImage.FromBundle("Angry_selected");
		item.SelectedView = imageView;
		var imageView2 = new UIImageView(View.Frame);
		imageView2.Image = UIImage.FromBundle("Angry_Unselected");
		item.UnSelectedView = imageView2;

	SfRatingItem item2 = new SfRatingItem(rating);
		var imageView3 = new UIImageView(View.Frame);
		imageView3.Image = UIImage.FromBundle("UnHappy_selected");			item2.SelectedView = imageView3;
		var imageView4 = new UIImageView(View.Frame);
		imageView4.Image = UIImage.FromBundle("UnHappy_Unselected");	
		item2.UnSelectedView = imageView4;

	SfRatingItem item3 = new SfRatingItem(rating);
		var imageView5 = new UIImageView(View.Frame);
		imageView5.Image = UIImage.FromBundle("Neutral_selected");
		item3.SelectedView = imageView5;
		var imageView6 = new UIImageView(View.Frame);
		imageView6.Image = UIImage.FromBundle("Neutral_Unselected");
		item3.UnSelectedView = imageView6;

	SfRatingItem item4 = new SfRatingItem(rating);
		var imageView7 = new UIImageView(View.Frame);	imageView7.Image = UIImage.FromBundle("Happy_selected");
		item4.SelectedView = imageView7;
		var imageView8 = new UIImageView(View.Frame);
		imageView8.Image = UIImage.FromBundle("Happy_Unselected");
		item4.UnSelectedView = imageView8;

	SfRatingItem item5 = new SfRatingItem(rating);
		var imageView9 = new UIImageView(View.Frame);
		imageView9.Image = UIImage.FromBundle("Excited_selected");
		item5.SelectedView = imageView9;
		var imageView10 = new UIImageView(View.Frame);
		imageView10.Image = UIImage.FromBundle("Excited_Unselected");
		item5.UnSelectedView = imageView10;
	
	NSMutableArray collection = new NSMutableArray();
            collection.Add(item);
            collection.Add(item2);
        	collection.Add(item3);
		collection.Add(item4);
		collection.Add(item5);
	rating.EnableCustomView = true;
	rating.Items = collection;

{% endhighlight %}

![](images/CustomviewItems.png)
 




 
