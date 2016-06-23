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

{Syncfusion Installed location}\Essential Studio {version number}\lib

You have to add the following assembly reference to the iOS unified project

iOS-unifed\Syncfusion.SfRotator.iOS.dll

## Add and Configure the Rotator 

* Adding reference to Rotator.

{% highlight c# %}

	using Syncfusion.SFRotator.iOS;

{% endhighlight %}


* Create an instance of SfRotator.


{% highlight c# %}		

	SFRotator  rotator  = new SFRotator();
	this.AddSubview(rotator);

{% endhighlight %}

## Setting Navigation Mode

The NavigationMode property decides the navigation mode for navigating items. The items can be navigated using Thumbnail or Dots.

{% highlight C# %}	

	rotator.NavigationStripMode = SFRotatorNavigationStripMode.Dots;

{% endhighlight %}

## Customizing Position

The TabStripPosition property decides the position in which navigation strip items such as Thumbnail or Dots should be rendered. 

{% highlight C# %}	

	rotator.NavigationStripMode = SFRotatorNavigationStripMode.Dots;
	rotator.NavigationStripPosition = SFRotatorNavigationStripPosition.Bottom;
	
{% endhighlight %}