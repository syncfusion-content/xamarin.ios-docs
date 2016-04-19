---
layout: post
title: Getting Started | SfCircularGauge | iOS | Syncfusion
description: SCALES
platform: xamarin.iOS
control: SfCircularGauge
documentation: ug
---

# SCALES

The Scales contains a Collection of CircularScale which integrates labels, tick marks, and a rim to customize the basic look and feel of the SfCircularGauge.

## Scale

CircularScale contains three sub elements such as Rim, Ticks, and Labels. It defines the Radius, start angle and sweep angle, overall minimum and maximum values, and frequency of labels and tick marks. It can have multiple ranges.

A range is a visual element which begins and ends at specified values within a scale. It can have one or more pointers to point out the values in the scale. It also has a Header that can be used to set a unique header for the circular gauge.

{% highlight c# %}

    gauge = new SFCircularGauge ();
    scale = new SFCircularScale ();
    NSMutableArray scales = new NSMutableArray();
    scale = new SFCircularScale();
    scale.StartValue = 0;
    scale.EndValue = 100;
    scale.Interval = 10;
    scale.StartAngle = 40;
    scale.SweepAngle = 320;
    scale.RimWidth = 5;
    scale.ShowTicks = true;
    scale.ShowLabels = true;
    scale.RimColor = UIColor.Gray;
    scale.LabelColor = UIColor.Gray;
    scale.LabelOffset = 0.1f;
    scale.MinorTicksPerInterval = 1;
    scales.Add(scale);     
    gauge.Scales = scales;
    this.AddSubview (gauge);
    this.control = gauge;

{% endhighlight %}

![](iOS_Images/Scales.png)

##Multiple Scale

It helps to be able to add multiple scales to the same circular gauge, and also it helps to customize all the scales in a Scales collection.
