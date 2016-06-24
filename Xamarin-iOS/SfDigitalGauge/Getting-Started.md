---
layout: post
title: Getting Started with Syncfusion DigitalGauge control for Xamarin.iOS
description: A quick tour to initial users on Syncfusion digitalGauge control for Xamarin.iOS platform
platform: Xamarin.iOS
control: DigitalGauge
documentation: ug
---

# Getting Started

This section explains you the steps to configure a DigitalGauge control in a real-time scenario and also provides a walk-through on some of the customization features available in DigitalGauge control.

![](images/Objective.png)

## Creating Your First DigitalGauge in Xamarin.iOS

### Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio {version number}\lib

And below assembly reference to the iOS unified project.

iOS-unifed\Syncfusion.SfGauge.iOS.dll 

### Add and Configure the DigitalGauge

* Adding reference to DigitalGauge.

{% highlight C# %}

	using Syncfusion.SfDigitalGauge.iOS; 

{% endhighlight %}

* Create an instance of SfDigitalGauge.

{% highlight c# %}

	SFDigitalGauge  digitalGauge = new SFDigitalGauge ();
	this.AddSubview(digitalGauge);

{% endhighlight %}

### Configure the properties of DigitalGauge

{% highlight c# %}

	digitalGauge.CharacterHeight = 36;
	digitalGauge.CharacterWidth = 18;
	digitalGauge.CharacterType = SFDigitalGaugeCharacterType.SFDigitalGaugeCharacterTypeSegmentSeven;
	digitalGauge.Value = (NSString)“Syncfusion”;

{% endhighlight %}
