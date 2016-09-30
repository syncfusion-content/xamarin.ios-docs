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

## Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio {version number}\lib

You have to add the following assembly reference to the iOS unified project

iOS-unifed\Syncfusion.SfRotator.iOS.dll

## Add SfRotator 

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight c# %}

	using Syncfusion.SFRotator.iOS;

{% endhighlight %}

{% endtabs %}

* Now add the SfRotator control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight c# %}		

	SFRotator  rotator  = new SFRotator();
	this.AddSubview(rotator);

{% endhighlight %}

{% endtabs %}

## Setting Navigation Mode

SfRotator provides option to display the navigating items either in Thumbnail or Dots mode. The navigation mode for navigating items can be decided using `NavigationMode` property.

{% tabs %}

{% highlight C# %}	

	rotator.NavigationStripMode = SFRotatorNavigationStripMode.Dots;

{% endhighlight %}

{% endtabs %}

## Customizing Position

The placement position of navigation strip items such as Thumbnail or Dots can be customized in SfRotator. This can be specified using `NavigationStripPosition` property.  

{% tabs %}

{% highlight C# %}	

	rotator.NavigationStripMode = SFRotatorNavigationStripMode.Dots;
	rotator.NavigationStripPosition = SFRotatorNavigationStripPosition.Bottom;
	
{% endhighlight %}

{% endtabs %}

![](images/rotator.png)