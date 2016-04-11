---
layout: post
title: Getting Started | SfCircularGauge | iOS | Syncfusion
description: RIM
platform: xamarin.iOS
control: SfCircularGauge
documentation: ug
---

# RIM

Scale determines the structure of the circular gauge using the circular rim. By setting the `StartAngle` and `SweepAngle` properties, you can shape the circular gauge into a full circular gauge, half circular gauge, or quarter circular gauge.
The `StartValue` and `EndValue` properties will determine the overall range of the circular rim. The rim’s color and thickness can be set using the `RimColor` and `RimWidth` properties.

{% highlight c# %}

    gauge = new SFCircularGauge ();
    scale = new SFCircularScale ();
    NSMutableArray scales = new NSMutableArray();
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
    scale.MinorTicksPerInterval = 0;
    scales.Add(scale);
    gauge.Scales = scales;
    this.AddSubview (gauge);
    this.control = gauge;

{% endhighlight %}

![](iOS_Images/Rim.png)