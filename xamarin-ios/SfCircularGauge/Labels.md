---
layout: post
title: Getting Started | SfCircularGauge | iOS | Syncfusion
description: LABELS
platform: xamarin.iOS
control: SfCircularGauge
documentation: ug
---

# LABELS

Scale labels associate a numeric value with major scale tick marks.

## Label Customization  

The label color can be changed using the `LabelColor` property. The labels can be positioned far away from the ticks by using the `LabelOffset` property. The size of the Labels can be changed by using the `LabelFontSize` property.

{% highlight c# %}

    gauge = new SFCircularGauge ();
    scale = new SFCircularScale ();
    NSMutableArray scales = new NSMutableArray();
    scale.LabelColor = UIColor.Gray;
    scale.LabelOffset = 0.1f;
    scales.Add(scale);
    gauge.Scales = scales;
    this.AddSubview (gauge);
    this.control = gauge;

{% endhighlight %}

![](iOS_Images/Labels.png)

##Number of Decimal Digits

The `NumberOfDecimalDigits` property is used to set the number of decimal digits to be displayed in the scale labels.

{% highlight c# %}

    gauge = new SFCircularGauge ();
    scale = new SFCircularScale ();
    NSMutableArray scales = new NSMutableArray();
    scale.LabelColor = UIColor.Gray;
    scale.LabelOffset = 0.1f;
    scale.NumberOfDecimalDigits = 1;
    scales.Add(scale);
    gauge.Scales = scales;
    this.AddSubview (gauge);
    this.control = gauge;

{% endhighlight %}

![](iOS_Images/Label_DecimalDigits.png)

##Label Postfix

You can set the Postfix/Prefix values to the scale labels using `LabelPostfix` and `LabelPrefix` Properties respectively.
This property allows you to set the `Postfix` values to the scale labels. 

{% highlight c# %}

    gauge = new SFCircularGauge ();
    scale = new SFCircularScale ();
    NSMutableArray scales = new NSMutableArray();
    scale.LabelColor = UIColor.Gray;
    scale.LabelOffset = 0.1f;
    scale.LabelPostfix = (NSString)"%";
    scales.Add(scale);
    gauge.Scales = scales;
    this.AddSubview (gauge);
    this.control = gauge;

{% endhighlight %}

![](iOS_Images/Label_Postfix.png)

##Label Prefix

You can set the postfix/Prefix values to the scale labels using `LabelPostfix` and `LabelPrefix` Properties respectively.
This property allows you to set the `Prefix` values to the scale labels. 

{% highlight c# %}

    gauge = new SFCircularGauge ();
    scale = new SFCircularScale ();
    NSMutableArray scales = new NSMutableArray();
    scale.LabelColor = UIColor.Gray;
    scale.LabelOffset = 0.1f;
    scale.LabelPrefix = (NSString)"$";
    scales.Add(scale);
    gauge.Scales = scales;
    this.AddSubview (gauge);
    this.control = gauge;

{% endhighlight %}

![](iOS_Images/Label_Prefix.png)
