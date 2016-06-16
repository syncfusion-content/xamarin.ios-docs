---
layout: post
title: Getting Started with syncfusion Rotator control for Xamarin.iOS 
description:  A quick tour to initial users on Syncfusion Rotator control for Xamarin.iOS platform
platform: Xamarin.iOS 
control: Rotator 
documentation: ug
---

# Getting Started

This section explains you the steps to configure a Rotator control in a real-time scenario and also provides a walk-through on some of the customization features available in Rotator control.

![](images/rotator.png)

## Creating your first Rotator in Xamarin.iOS

## Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:

You have to add the following assembly reference to the iOS unified project

iOS-unifed\Syncfusion.SfRotator.iOS.dll

## Add and Configure the Rotator 

* Adding reference to Rotator.

{% highlight c# %}

	using Com.Syncfusion.Rotator; 

{% endhighlight %}


* Create an instance of SfRotator.


{% highlight c# %}		

	SfRotator  rotator  = new SfRotator();
	SetContentView(rotator);

{% endhighlight %}

## Setting Navigation Mode

The NavigationMode property decides the navigation mode for navigating items. The items can be navigated using Thumbnail or Dots.

{% highlight C# %}	

	rotator.NavigationMode = NavigationMode.Dots;

{% endhighlight %}

## Customizing Position

The TabStripPosition property decides the position in which navigation strip items such as Thumbnail or Dots should be rendered. 

{% highlight C# %}	

	rotator.NavigationMode = NavigationMode.Dots;
	rotator.TabStripPosition = TabStripPosition.Bottom;
	
{% endhighlight %}