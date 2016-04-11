---
layout: post
title: Getting Started | SfCircularGauge | iOS | Syncfusion
description: RANGES
platform: xamarin.iOS
control: SfCircularGauge
documentation: ug
---

# RANGES

A range is a visual element which begins and ends at specified values within a scale.

## Ranges Customization  

Ranges start and end values are set by the `StartValue` and `EndValue` properties of the range. A range’s UI is customized by the `Color` and `Width` properties.

{% highlight c# %}

    gauge = new SFCircularGauge ();
    scale = new SFCircularScale ();
    NSMutableArray scales = new NSMutableArray();
    NSMutableArray range = new NSMutableArray ();
    SFCircularRange range1 = new SFCircularRange ();
    SFCircularRange range2 = new SFCircularRange ();
    range1.StartValue = 0;
    range1.EndValue = 70;
    range1.Color= UIColor.FromRGB(43, 191, 184);
    range1.Width = 5;
    range1.Offset = 0;
    range2.StartValue = 70;
    range2.EndValue = 100;
    range2.Color = UIColor.FromRGB((byte)209,(byte)70,(byte)70); 
    range2.Width = 5;
    range2.Offset = 0;
    range.Add (range1);
    range.Add (range2);
    scale.Ranges = range;
    scales.Add(scale);
    gauge.Scales = scales;
    this.AddSubview (gauge);
    this.control = gauge;

{% endhighlight %}

![](iOS_Images/Ranges.png)

##Range Offset

The range can be placed inside the scale, outside the scale, or on the scale by setting `Offset` property.

{% highlight c# %}

    gauge = new SFCircularGauge ();
    scale = new SFCircularScale ();
    NSMutableArray scales = new NSMutableArray();
    NSMutableArray range = new NSMutableArray ();
    SFCircularRange range1 = new SFCircularRange ();
    SFCircularRange range2 = new SFCircularRange ();
    range1.StartValue = 0;
    range1.EndValue = 70;
    range1.Color= UIColor.FromRGB(43, 191, 184);
    range1.Width = 5;
    range1.Offset = 0.5f;
    range2.StartValue = 70;
    range2.EndValue = 100;
    range2.Color = UIColor.FromRGB((byte)209,(byte)70,(byte)70); 
    range2.Width = 5;
    range2.Offset = 0.5f;
    range.Add (range1);
    range.Add (range2);
    scale.Ranges = range;
    scales.Add(scale);
    gauge.Scales = scales;
    this.AddSubview (gauge);
    this.control = gauge;

{% endhighlight %}

![](iOS_Images/Ranges_Offset.png)

