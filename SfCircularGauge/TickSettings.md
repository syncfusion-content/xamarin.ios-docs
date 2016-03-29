---
layout: post
title: Getting Started | SfCircularGauge | iOS | Syncfusion
description: TICK SETTINGS
platform: ios
control: SfCircularGauge
documentation: ug
---

# TICK SETTINGS

TickSettings help you identify the gauge’s data value by marking the gauge scale in regular increments.

## Tick Customization  

The `Interval` property is used to calculate the tick count for a scale. Like ticks, minor ticks are calculated using the `MinorTicksPerInterval` property.
A tick’s length, color, and thickness are set by the `Length`, `Color` and `Width` UI properties.

{% highlight c# %}

    gauge = new SFCircularGauge ();
    scale = new SFCircularScale ();
    NSMutableArray scales = new NSMutableArray();
    SFTickSettings minor = new SFTickSettings();
    minor.Size = 4;
    minor.Color = UIColor.FromRGB(68, 68, 68);
    minor.Offset = 0.041f;
    minor.Width = 1.5f;
    scale.MinorTickSettings = minor;
    //Add major Tick settings
    SFTickSettings major = new SFTickSettings();
    major.Size = 10;
    major.Offset = 0.041f;
    major.Color = UIColor.FromRGB(68,68,68);
    major.Width = 1.5f;
    scale.MajorTickSettings = major;
    scales.Add(scale);
    gauge.Scales = scales;
    this.AddSubview (gauge);
    this.control = gauge;

{% endhighlight %}

![](iOS_Images/TickCustomization.png)

##Offset

The Major and Minor ticks can be positioned far away from the rim by using the `Offset` property. The default value of this Offset property value is 0.

{% highlight c# %}

    gauge = new SFCircularGauge ();
    scale = new SFCircularScale ();
    NSMutableArray scales = new NSMutableArray();
    SFTickSettings minor = new SFTickSettings();
    minor.Size = 4;
    minor.Color = UIColor.FromRGB(68, 68, 68);
    minor.Offset = 0.5f;
    minor.Width = 1.5f;
    scale.MinorTickSettings = minor;
    //Add major Tick settings
    SFTickSettings major = new SFTickSettings();
    major.Size = 10;
    major.Offset = 0.5f;
    major.Color = UIColor.FromRGB(68,68,68);
    major.Width = 1.5f;
    scale.MajorTickSettings = major;
    scales.Add(scale);
    gauge.Scales = scales;
    this.AddSubview (gauge);
    this.control = gauge;

{% endhighlight %}


![](iOS_Images/TickOffset.png)
