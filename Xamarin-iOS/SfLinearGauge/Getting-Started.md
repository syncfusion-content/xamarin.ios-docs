---
layout: post
title: Getting Started with Syncfusion LinearGauge control for Xamarin.iOS
description: A quick tour to initial users on Syncfusion linearGauge control for Xamarin.iOS platform 
platform: Xamarin.iOS
control: LinearGauge
documentation: ug
---

# Getting Started

This section explains you the steps to configure a SfLinearGauge control in a real-time scenario and also provides a walk-through on some of the customization features available in SfLinearGauge control.

### Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio {version number}\lib

And below assembly reference to the iOS unified project.

iOS-unifed\Syncfusion.SfGauge.iOS.dll 

### Add SfLinearGauge

The following steps explain on how to create a SfLinearGauge and configure its elements

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight c# %}

	using Syncfusion.SFLinearGauge.iOS; 

{% endhighlight %}

{% endtabs %}

* Now add the SfLinearGauge control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight c# %}

SFLinearGauge  linearGauge = new SFLinearGauge ();
this.AddSubview(linearGauge);

{% endhighlight %}

{% endtabs %}

* Configure the properties of SfLinearGauge

{% tabs %}

{% highlight c# %}

linearGauge.Orientation = SFLinearGaugeOrientation.SFLinearGaugeOrientationVertical;

{% endhighlight %}

{% endtabs %}

## Add Scales

The scale that point out to the values can be added by instantiating LinearScale class and setting minimum values, maximum values, scale intervals and colors etc.

{% tabs %}

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

{% endtabs %}

## Add a Symbol Pointer

An arrow head that points to the value is called the Symbol Pointer which can be added by instantiating the SymbolPointer class and assigning it to the Pointers collection.

{% tabs %}

{% highlight c# %}

SFSymbolPointer symbolPointer = new SFSymbolPointer ();
symbolPointer.Value = 50;
symbolPointer.Offset = 0;
symbolPointer.Thickness = 3;
symbolPointer.Color = UIColor.FromRGB (65, 77, 79);        

{% endhighlight %}	

{% endtabs %}	
	
## Add a Bar Pointer

A flat solid bar that points to the current value can be added by instantiating BarPointer and it can be added to pointers collection.

{% tabs %}

{% highlight c# %}

SFBarPointer rangePointer = new SFBarPointer ();
rangePointer.Value = 50;
rangePointer.Color = UIColor.FromRGB (206, 69, 69);
rangePointer.Thickness = 10;
			
{% endhighlight %}

{% endtabs %}

## Add a Range

We can improve the readability of data by including ranges that quickly displays when values fall within a specific ranges.

{% tabs %}

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

{% endtabs %}

![](images/Xamarin.iOS.png)



