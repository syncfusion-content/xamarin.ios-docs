---
layout: post
title: Pointers in Syncfuison LinearGauge in Xamarin.iOS
description: Learn how to add value and thickness of pointers in LinearGauge
platform: Xamarin.iOS
control: LinearGauge
documentation: ug
---

# Pointers

## BarPointer

BarPointer is an accenting line or colored bar that is placed on the SfLinearGauge to mark the values. 

{% highlight c# %}

    SFBarPointer rangePointer = new SFBarPointer ();
    rangePointer.Value = 50;
    rangePointer.Color = UIColor.FromRGB (206, 69, 69);
    rangePointer.Thickness = 10;
    pointers.Add (rangePointer);

{% endhighlight %}

![](images/BarPointer.png)


## SymbolPointer

In SymbolPointer, the value is pointed by a symbol on the scale. The Symbol Pointer class is derived from Pointer class. You can modify the symbol pointer’s size using the `StrokeWidth` property. The color of the symbol pointer is changed using the `Color` property.

{% highlight c# %}

	List<LinearPointer> pointers = new List<LinearPointer> ();
     //SymbolPointer
    SFSymbolPointer symbolPointer = new SFSymbolPointer ();
    symbolPointer.Value = 50;
    symbolPointer.Offset = 0.0;
    symbolPointer.Thickness = 3;
    symbolPointer.Color = UIColor.FromRGB (65, 77, 79);
    pointers.Add (symbolPointer);
	
{% endhighlight  %}


![](images/SymbolPointer.png)
