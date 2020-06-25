---
layout: post
title: Getting Started with Syncfusion DigitalGauge control for Xamarin.iOS
description: A quick tour to initial users on Syncfusion digitalGauge control for Xamarin.iOS platform and also describes how to customize the characters.
platform: Xamarin.iOS
control: DigitalGauge
documentation: ug
---

# Getting Started with SfDigitalGauge

This section explains you the steps to configure a SfDigitalGauge control in a real-time scenario and some of the customization features available in it.

## Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio {version number}\lib

And below assembly reference to the iOS unified project.

iOS-unified\Syncfusion.SfGauge.iOS.dll 

## Initialize digital gauge from designer

[`SFDigitalGauge`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFDigitalGauge.html) allows users to drag the control from toolbox to designer window. The properties window will be displayed where you change the necessary functionalities to customize the digital gauge in designer.

![Xamarin.iOS DigitalGauge Designer](images/designer.gif)

### Add SfDigitalGauge

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight C# %}

	using Syncfusion.SfGauge.iOS; 

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

![Xamarin.iOS DigitalGauge Getting Started](images/Objective.png)

You can find the complete getting started sample from this [`link`](https://github.com/SyncfusionExamples/SfDigitalGauge_GettingStarted_Xamarin.iOS).