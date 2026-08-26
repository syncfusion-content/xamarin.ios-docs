---
layout: post
title: Getting Started with Syncfusion® RangeSlider control for Xamarin.iOS
description: This section provides details for initial users on Syncfusion® RangeSlider control for Xamarin.iOS platform
platform: xamarin.ios
control: RangeSlider
documentation: ug
---

# Getting Started with RangeSlider

This section explains the steps to configure a RangeSlider control in a real-time scenario and also provides a walk-through on some of the customization features available in the RangeSlider control.

## Referencing Essential Studio<sup>®</sup> Components in Your Solution

After installing Essential Studio<sup>®</sup> for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio {version number}\lib

You have to add the following assembly reference to the iOS unified project:

iOS-unified\Syncfusion.SfRangeSlider.iOS.dll

## Add and Configure the RangeSlider

### Adding Reference to RangeSlider

{% tabs %}

{% highlight C# %}

	using Syncfusion.SfRangeSlider.iOS; 

{% endhighlight %}

{% endtabs %}

### Create an Instance of SfRangeSlider

{% tabs %}

{% highlight C# %}

	SfRangeSlider rangeSlider = new SfRangeSlider();
	this.AddSubview(rangeSlider);	

{% endhighlight %}

{% endtabs %}

## Add Values and Scale

You can set the minimum and maximum values for the slider by using the `Minimum` and `Maximum` properties in the RangeSlider. These can be numerical values.

{% tabs %}

{% highlight c# %}

	rangeSlider.Minimum = 0; 
	rangeSlider.Maximum = 24; 
	rangeSlider.DirectionReversed = false; 
	rangeSlider.RangeEnd = 20; 
	rangeSlider.RangeStart = 4;
	rangeSlider.ShowRange = true; 
	rangeSlider.Orientation = SFOrientation.SFOrientationHorizontal;

{% endhighlight %}

{% endtabs %}

> **Note:** The `RangeStart` and `RangeEnd` properties denote the start range and end range values when dual thumb is used. The `ShowRange` property is used to switch between a single thumb and double thumb. The `Orientation` property sets the type of orientation.

## Add Ticks and Labels for RangeSlider

The ticks can be set by configuring the `TickFrequency` and `TickPlacement` properties. Likewise, value labels can be displayed by setting the `ShowValueLabel` property to `true`. The position of the label can be varied using the `ValuePlacement` property.

{% tabs %}

{% highlight c# %}

	rangeSlider.TickFrequency = 4; 
	rangeSlider.ShowValueLabel = true; 
	rangeSlider.ValuePlacement = SFValuePlacement.SFValuePlacementTopLeft; 
	rangeSlider.TickPlacement = SFTickPlacement.SFTickPlacementBottomRight;

{% endhighlight %}

{% endtabs %}

> **Note:** The `TickFrequency` property determines the interval between the ticks.

## Add Snapping Type for RangeSlider

The movement of the thumb can be configured in different ways. This is achieved by setting the `SnapsTo` property.

{% tabs %}

{% highlight c# %}

	rangeSlider.SnapsTo = SFSnapsTo.SFSnapsToTicks; 
	rangeSlider.StepFrequency = 6;

{% endhighlight %}

{% endtabs %}

## Configure the Properties for RangeSlider

{% tabs %} 

{% highlight C# %}
	
	rangeSlider.Minimum = 0;
	rangeSlider.Maximum = 24;
	rangeSlider.RangeStart = 4;
	rangeSlider.RangeEnd = 20;
	rangeSlider.TickFrequency = 4;
	rangeSlider.TickPlacement = SFTickPlacement.SFTickPlacementBottomRight;
	rangeSlider.SnapsTo = SFSnapsTo.SFSnapsToTicks;

{% endhighlight %}

{% endtabs %}

![The RangeSlider](images/RangeSlider-iOS.png) 

