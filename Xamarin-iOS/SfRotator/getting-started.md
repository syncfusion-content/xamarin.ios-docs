---
layout: post
title: Getting Started with Syncfusion® Rotator Control for Xamarin.iOS
description: A quick tour to initial users on Syncfusion® Rotator control for Xamarin.iOS platform
platform: xamarin.ios 
control: SfRotator
documentation: ug
---

# Getting Started

This section explains the steps to configure a Rotator control in a real-time scenario and also provides a walk-through on some of the customization features available in the Rotator control.

## Referencing Essential Studio<sup>®</sup> Components in Your Solution

After installing Essential Studio<sup>®</sup> for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio {version number}\lib

You have to add the following assembly reference to the iOS unified project:

iOS-unified\Syncfusion.SfRotator.iOS.dll

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

SfRotator provides an option to display the navigating items either in Thumbnail or Dots mode. The navigation mode for navigating items can be decided using the `NavigationStripMode` property.

{% tabs %}

{% highlight C# %}	

	rotator.NavigationStripMode = SFRotatorNavigationStripMode.Dots;

{% endhighlight %}

{% endtabs %}

## Customizing Position

The placement position of navigation strip items such as Thumbnail or Dots can be customized in SfRotator. This can be specified using the `NavigationStripPosition` property.

{% tabs %}

{% highlight C# %}	

	rotator.NavigationStripMode = SFRotatorNavigationStripMode.Dots;
	rotator.NavigationStripPosition = SFRotatorNavigationStripPosition.Bottom;
	
{% endhighlight %}

{% endtabs %}

![Rotator Control](images/rotator.png)
