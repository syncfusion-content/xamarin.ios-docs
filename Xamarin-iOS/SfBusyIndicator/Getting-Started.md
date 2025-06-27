---
layout: post
title: Getting Started with Syncfusion® BusyIndicator control for Xamarin.iOS
description: This section provides details for new users getting started with Syncfusion® BusyIndicator control for Xamarin.iOS platform
platform: xamarin.ios
control: SfBusyIndicator
documentation: ug
---

# Getting Started with BusyIndicator

This section explains the steps to configure an SfBusyIndicator control in a real-time scenario and provides a walkthrough of the customization features available in the SfBusyIndicator control.

## Referencing Essential Studio<sup>®</sup> Components in Your Solution

After installing Essential Studio<sup>®</sup> for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio {version number}\lib

Add the following assembly reference to the iOS unified project:

iOS-unified\Syncfusion.SfBusyIndicator.iOS.dll

## Add BusyIndicator

### Adding Namespace
Add the namespace for the referenced assemblies:

{% tabs %}

{% highlight c# %}

	using Syncfusion.SfBusyIndicator.iOS;

{% endhighlight %}

{% endtabs %}

* Now add the SfBusyIndicator control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight c# %}
	
	SfBusyIndicator busyindicator = new SfBusyIndicator();
	this.AddSubview(busyindicator);
	
{% endhighlight %}

{% endtabs %}

## Set Animation Type

SfBusyIndicator provides 10+ predefined animation types such as Ball, Battery, Globe, and more. You can select one of the animation types using the `AnimationType` property.

The following example shows how to set the battery animation type for SfBusyIndicator:

{% tabs %}

{% highlight c# %}

	 busyindicator.AnimationType = SFBusyIndicatorAnimationType.SFBusyIndicatorAnimationTypeBattery;

{% endhighlight %}

{% endtabs %}
	
## Configure Properties for SFBusyIndicator

Size and color can be customized in SfBusyIndicator as follows.

{% tabs %}
      
{% highlight c# %}
	 
	busyindicator.AnimationType = SFBusyIndicatorAnimationType.SFBusyIndicatorAnimationTypeBall;
	busyindicator.Foreground = UIColor.Red;
	busyindicator.ViewBoxHeight = 20;
	busyindicator.ViewBoxWidth = 20;
	busyindicator.IsBusy = True;
	
{% endhighlight %}

{% endtabs %}

![the BusyIndicator](images/BusyIndicator-iOS.png)                 

BusyIndicator
{:.caption}