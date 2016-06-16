---
layout: post
title: Getting Started with Syncfusion LinearGauge control for Xamarin.iOS
description: A quick tour to initial users on Syncfusion linearGauge control for Xamarin.iOS platform 
platform: Xamarin.iOS
control: LinearGauge
documentation: ug
---

# Getting Started

This section explains how to create the LinearGauge and configure its properties.This section provides overview for working with LinearGauge for Xamarin.iOS.

![](images/Xamarin.iOS.png)

## Creating Your First LinearGauge in Xamarin.iOS

### Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio {version number}\lib

And below assembly reference to the iOS unified project.

iOS-unifed\Syncfusion.SfLinearGauge.iOS.dll 

### Add and Configure the LinearGauge

The following steps explain on how to create a LinearGauge and configure its elements:

* Adding reference to Autocomplete.

{% highlight c# %}

	using Syncfusion.SfLinearGauge.iOS; 

{% endhighlight %}

* Create an instance of SfLinearGauge.

{% highlight c# %}

	SFLinearGauge  linearGauge = new SFLinearGauge ();
	SetContentView(linearGauge);

{% endhighlight %}

* Configure the properties of LinearGauge

{% highlight c# %}

	linearGauge.Orientation = SFLinearGaugeOrientation.SFLinearGaugeOrientationVertical;

{% endhighlight %}

### Add Scales

We will add one or more scale value to linear gauge. Before adding that scales we have to set 
Maximum and Minimum value to this.

{% highlight c# %}

	SFLinearScale scale = new SFLinearScale ();
	scale.Minimum = 0;
	scale.Maximum = 100;
	scale.Interval = 20;
	scale.ScaleBarLength = 100;
	scale.ScaleBarColor =UIColor.FromRGB (250, 236, 236);
	scale.LabelColor = UIColor.FromRGB (84, 84, 84); 
	scale.MinorTicksPerInterval = 1;
	scale.ScaleBarSize = 13;
	scale.ScalePosition = SFLinearGaugeScalePosition.SFLinearGaugeScalePositionForward;
	
{% endhighlight %}

### Add SymbolPointer

We can point a value on scale in lineargauge by creating instance of SymbolPointer.

{% highlight c# %}

	SFSymbolPointer symbolPointer = new SFSymbolPointer ();
	symbolPointer.Value = 50;
	symbolPointer.Offset = 0;
	symbolPointer.Thickness = 3;
	symbolPointer.Color = UIColor.FromRGB (65, 77, 79);        

{% endhighlight %}		
	
### Add a BarPointer

Before adding that symbol and bar pointer into Scale’s pointer add value of that pointers.

{% highlight c# %}

    SFBarPointer rangePointer = new SFBarPointer ();
	rangePointer.Value = 50;
	rangePointer.Color = UIColor.FromRGB (206, 69, 69);
	rangePointer.Thickness = 10;
			
{% endhighlight %}

### Add a Range

We can improve the readability of data by including ranges that quickly display when values fall within specific ranges

{% highlight c# %}

    SFLinearRange range = new SFLinearRange ();
	range.StartValue = 0;
	range.EndValue = 50;
	range.Color = UIColor.FromRGB (234, 248, 249);
	range.StartWidth = 10;
	range.EndWidth = 10;
	range.Offset = nfloat.Parse("-0.17");
	scale.Ranges.Add (range);
	//Range
	SFLinearRange range2 = new SFLinearRange ();
	range2.StartValue = 50;
	range2.EndValue = 100;
	range2.Color = UIColor.FromRGB (50, 184, 198);
	range2.StartWidth = 10;
	range2.EndWidth = 10;
	range2.Offset = nfloat.Parse("-0.17");
	scale.Ranges.Add (range2);        
	linearGauge.Scales.Add (scale);

{% endhighlight %}





