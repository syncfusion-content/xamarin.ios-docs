---
layout: post
title: Getting Started | SfCircularGauge | iOS | Syncfusion
description: POINTERS
platform: xamarin.iOS
control: SfCircularGauge
documentation: ug
---

# POINTERS

You can add multiple pointers to the gauge to point at multiple values on the same scale. This can be useful for showing a low and a high value at the same time. The value of the pointer is set using the Value property. There are two types of pointers. You can choose a pointer using the PointerType property. Movement of the pointer can be animated by enabling the `EnableAnimation` property.

## Needle Pointer  

A needle pointer contains two parts, the needle and the knob that can be placed on a gauge to mark values. The needle length is controlled by the `LengthFactor` property. The LengthFactor property’s minimum and maximum bounds are 0 and 1. The needle’s UI is customized by the `Color` and `Width` properties. The user can modify the Knob’s size by changing the `KnobRadius` property.

### NeedlePointerType

NeedlePointer appearance can be customized by using the `Type` property the default value of this property is Rectangle.
It is enum includes the following option.

•	SFCiruclarGaugePointerTypeBar
•	SFCiruclarGaugePointerTypeTriangle

{% highlight c# %}

    gauge = new SFCircularGauge ();
    scale = new SFCircularScale ();
    NSMutableArray scales = new NSMutableArray();
    NSMutableArray pointers = new NSMutableArray();
    needlePointer = new SFNeedlePointer();
    needlePointer.PointerType = SFCiruclarGaugePointerType.SFCiruclarGaugePointerTypeBar;
    needlePointer.Value = 70;
    needlePointer.Color = UIColor.Gray;
    needlePointer.KnobRadius = 12;
    needlePointer.KnobColor = UIColor.FromRGB(43, 191, 184);
    needlePointer.Width = 2.5f;
    needlePointer.LengthFactor =nfloat.Parse("0.7");
    scale.Pointers = pointers;
    scales.Add(scale);
    gauge.Scales = scales;
    this.AddSubview (gauge);
    this.control = gauge;

{% endhighlight %}

![](iOS_Images/NeedlePointer.png)

##Range Pointer

A range pointer is an accenting line or shaded background range that can be placed on a gauge to mark values. The range pointer’s UI is customized by the `Color` and `Width` properties.

### RangePointerPosition

The RangePointer in the scale can be placed inside the scale or outside the scale by setting `Offset` property.

{% highlight c# %}

    gauge = new SFCircularGauge ();
    scale = new SFCircularScale ();
    NSMutableArray scales = new NSMutableArray();
    rangePointer = new SFRangePointer();
    rangePointer.Value = 70;
    rangePointer.Color = UIColor.FromRGB(43, 191, 184);
    rangePointer.Width = 5;
    pointers.Add(rangePointer);
    scale.Pointers = pointers;
    scales.Add(scale);
    gauge.Scales = scales;
    this.AddSubview (gauge);
    this.control = gauge;

{% endhighlight %}

![](iOS_Images/RangePointer.png)