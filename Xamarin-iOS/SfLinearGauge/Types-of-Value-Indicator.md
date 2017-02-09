---
layout: post
title: Pointers in Syncfuison LinearGauge in Xamarin.iOS
description: Learn how to add value and thickness of pointers in LinearGauge
platform: Xamarin.iOS
control: LinearGauge
documentation: ug
---

# Types of Value Indicator

SfLinearGauge provides support to mark the values using BarPointer and SymbolPointer.

## Through Bar Pointer

`BarPointer` is an accenting line or colored bar that is placed on the SfLinearGauge to mark the values.

{% tabs %}

{% highlight c# %}

    List<LinearPointer> pointers = new List<LinearPointer> ();
    //BarPointer
    SFBarPointer rangePointer = new SFBarPointer ();
    rangePointer.Value = 50;
    rangePointer.Color = UIColor.FromRGB (206, 69, 69);
    rangePointer.Thickness = 10;
    pointers.Add (rangePointer);

{% endhighlight %}

{% endtabs %}

![](images/BarPointer.png)


## Through Symbol Pointer

In SymbolPointer, the value is pointed by a symbol on the scale. The Symbol Pointer class is derived from Pointer class. You can modify the symbol pointer size using the `StrokeWidth` property. The color of the symbol pointer is changed using the `Color` property.

{% tabs %}

{% highlight c# %}

    //SymbolPointer
    SFSymbolPointer symbolPointer = new SFSymbolPointer ();
    symbolPointer.Value = 50;
    symbolPointer.Offset = 0.0;
    symbolPointer.Thickness = 3;
    symbolPointer.Color = UIColor.FromRGB (65, 77, 79);
    pointers.Add (symbolPointer);
	
{% endhighlight  %}

{% endtabs %}

![](images/SymbolPointer.png)
