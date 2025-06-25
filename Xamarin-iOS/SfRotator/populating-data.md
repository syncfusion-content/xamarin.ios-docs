---
layout: post
title: Populating Data in Syncfusion® Rotator Control in Xamarin.iOS
description: Learn how to set the DataSource in Rotator for Xamarin.iOS
platform: xamarin.ios
control: SfRotator
documentation: ug
---

# Populating Data

The SfRotator control supports binding to different data sources such as IList data source and Observable Collection data source.

## DataSource

SfRotator items can be populated with a collection of image data. For example, a user may want to create an SfRotator control that will display a sequence of images.

{% tabs %}

{% highlight C# %}

	NSMutableArray<SFRotatorItem> rotatorItems = new NSMutableArray<SFRotatorItem>();

    for (int i = 1; i < 5; i++)
    {
        SFRotatorItem item = new SFRotatorItem();

        UIView customView = new UIView();
        UIImageView image = new UIImageView();
        image.Image = UIImage.FromFile("movie" + i.ToString() + ".png");
        item.View = image;
        customView.AddSubview(image);
        rotatorItems.Add(item);
    }
    rotator.DataSource = rotatorItems;
	
{% endhighlight %}

{% endtabs %}

## RotatorItem

RotatorItems consist of two properties: `View` and `ItemText`. Using these properties, users can set content for SfRotator.

