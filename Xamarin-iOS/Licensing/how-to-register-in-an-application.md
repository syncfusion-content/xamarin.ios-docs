---
layout: post
title: Overview of Syncfusion® license registration - Syncfusion®
description: Learn here about how to register Syncfusion® Xamarin.iOS license key for xamarin.iOS application for license validation.
platform: xamarin.ios
control: Essential Studio<sup>®</sup>
documentation: ug
---


# Register Syncfusion<sup>®</sup> License key in Xamarin.iOS application

The generated license key is just a string that needs to be registered before any Syncfusion<sup>®</sup> control is initiated. The following code is used to register the license.

{% tabs %}
{% highlight c# %}
Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
{% endhighlight %}
{% endtabs %}

N> * Place the license key between double quotes.  Also, ensure that Syncfusion.Licensing.dll is referenced in your project where the license key is being registered.
* Syncfusion<sup>®</sup> license validation is done offline during application execution and does not require internet access.  Apps registered with a Syncfusion<sup>®</sup> license key can be deployed on any system that does not have an internet connection.

### Xamarin.iOS

You can register the license key in **FinishedLaunching** override method of **AppDelegate.cs**

{% tabs %}
{% highlight c# %}
public override bool FinishedLaunching(UIApplication application, NSDictionary launchOptions)
{
	//Register Syncfusion<sup>®</sup> license
	Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");

	// create a new window instance based on the screen size
	Window = new UIWindow(UIScreen.MainScreen.Bounds);

	// If you have defined a root view controller, set it here:
	// Window.RootViewController = myViewController;

	// make the window visible
	Window.MakeKeyAndVisible();

	return true;
} 
{% endhighlight %}
{% endtabs %}