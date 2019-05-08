---
layout : post
title : Populating data in Syncfusion Rotator control in Xamarin.iOS
description : Learn how to set the DataSource in Rotator for Xamarin.iOS
platform : Xamarin.iOS
control : Rotator 
documentation : ug
---

# Populating Data

SfRotator control supports binding to different data sources such as IList Data Source, Observable Collection Data Source.

## DataSource

SfRotator items can be populated with a collection of image data. For example, a user may want to create a SfRotator control which will display a sequence of images.

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

RotatorItems consisting of two properties View and ItemText using this user can set content for SFRotator.
