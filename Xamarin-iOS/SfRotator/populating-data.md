---
layout : post
title : Populating data in Syncfusion Rotator control in Xamarin.iOS
description : Learn how to set the DataSource in Rotator for Xamarin.iOS
platform : Xamarin.iOS
control : Rotator 
documentation : ug
---

# Populating Data

## DataSource

SfRotator items can be populated with a collection of image data. For example, a user may want to create a SfRotator control which will display a sequence of images.

{% highlight C# %}

	NSMutableArray<SFRotatorItem> rotatorItemCollection = new NSMutableArray<SFRotatorItem> ();
	For(int i=1;i<18;i++)
	{
	SFRotatorItem item =new SFRotatorItem ();
	item.ImageName="image"+i;
	rotatorItemCollection.Add(item);
	}
	rotator.DataSource=rotatorItemCollection;
	
{% endhighlight %}