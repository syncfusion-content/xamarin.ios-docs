---
layout: post
title: Getting Started | SfCircularGauge | iOS | Syncfusion
description: GAUGE TYPE
platform: xamarin.ios
control: SfCircularGauge
documentation: ug
---

# GAUGE TYPE

SfCircularGauge type is determined by positioning the control towards particular direction. `GaugeType` is an enum property that provides the option to select type of the `SfCircularGaugeType`, which contains following options. Enum property for Xamarin.iOS contains following options.

•	SFCircularGaugeTypeDefault,
•	SFCircularGaugeTypeEast,
•	SFCircularGaugeTypeWest,
•	SFCircularGaugeTypeNorth,
•	SFCircularGaugeTypeSouth,
•	SFCircularGaugeTypeNorthEast,
•	SFCircularGaugeTypeNorthWest,
•	SFCircularGaugeTypeSouthEast,
•	SFCircularGaugeTypeSouthWest,

{% highlight c# %}

    SFCircularGauge  gauge = new SFCircularGauge ();
    gauge.GaugeType = SFCircularGaugeType.SFCircularGaugeTypeEast;
    this.AddSubview (gauge);
    this.control = gauge;

{% endhighlight %}

![](iOS_Images/GaugeType.png)