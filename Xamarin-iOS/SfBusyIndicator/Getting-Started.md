---
layout: post
title: Getting Started with Syncfusion BusyIndicator control for Xamarin.iOS
description: A quick tour to initial users on Syncfusion busyIndicator control for Xamarin.iOS platform
platform: Xamarin.iOS
control: SfBusyIndicator
documentation: ug
---

# Getting Started

This section explains you the steps to configure a BusyIndicator control in a real-time scenario and also provides a walk-through on some of the customization features available in BusyIndicator control.

![](images/BusyIndicator-iOS.png)                 

BusyIndicator
{:.caption}

## Creating your first BusyIndicator in Xamarin.iOS.

### Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio {version number}\lib

And below assembly reference to the iOS unified project.

ios-unifed\Syncfusion.SfBusyIndicator.iOS.dll

### Add and Configure the BusyIndicator

* Adding reference to busyindicator.

{% highlight c# %}

	using Com.Syncfusion.BusyIndicator; 

{% endhighlight %}

* Create an instance of BusyIndicator.

{% highlight c# %}
	
	SfBusyIndicator sfBusyIndicator = new SfBusyIndicator(this);
	SetContentView(sfBusyIndicator);
	
{% endhighlight %}

### Set the AnimationType to BusyIndicator

To set AnimationType for the BusyIndicator, use AnimationType property and choose anyone of the 13 predefined animation types. 

{% highlight c# %}

	SfBusyIndicator busyIndicator = new SfBusyIndicator (this); 
	busyIndicator.AnimationType=AnimationTypes.Battery;

{% endhighlight %}
	
### Configure the properties for BusyIndicator. 
      
{% highlight c# %}
	 
	sfBusyIndicator.AnimationType=AnimationTypes.Ball;
	sfBusyIndicator.TextColor=Color.RED;
	sfBusyIndicator.ViewBoxHeight=20;
	sfBusyIndicator.ViewBoxWidth=20;
	sfBusyIndicator.IsBusy=True;
	
{% endhighlight %}

