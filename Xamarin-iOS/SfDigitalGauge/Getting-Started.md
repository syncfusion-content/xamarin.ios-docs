---
layout: post
title: Getting Started with Syncfusion DigitalGauge control for Xamarin.iOS
description: A quick tour to initial users on Syncfusion digitalGauge control for Xamarin.iOS platform
platform: Xamarin.iOS
control: DigitalGauge
documentation: ug
---

# Getting Started

This section explains you the steps to configure a SfDigitalGauge control in a real-time scenario and some of the customization features available in it.

## Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio {version number}\lib

And below assembly reference to the iOS unified project.

iOS-unifed\Syncfusion.SfGauge.iOS.dll 

### Add SfDigitalGauge

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight C# %}

	using Syncfusion.SfDigitalGauge.iOS; 

{% endhighlight %}

{% endtabs %}

* Now add the SfDigitalGauge control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight c# %}

SFDigitalGauge  digitalGauge = new SFDigitalGauge ();
this.AddSubview(digitalGauge);

{% endhighlight %}

{% endtabs %}

## Configuring properties

Character Height, Width and segment  which is used to display the Characters can be customized as in the below code snippets.

{% tabs %}

{% highlight c# %}

digitalGauge.CharacterHeight = 36;
digitalGauge.CharacterWidth = 18;
digitalGauge.CharacterType = SFDigitalGaugeCharacterType.SFDigitalGaugeCharacterTypeSegmentSeven;
digitalGauge.Value = (NSString)“Syncfusion”;

{% endhighlight %}

{% endtabs %}

![](images/Objective.png)