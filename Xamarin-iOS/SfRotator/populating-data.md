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

	ArrayList temp=new ArrayList();
	For(int i=1;i<18;i++)
	{
	SfRotatorItem item =new SfRotatorItem ();
	item.ImageName="image"+i;
	temp.add(item);
	}
	rotator.DataSource=temp;

{% endhighlight %}