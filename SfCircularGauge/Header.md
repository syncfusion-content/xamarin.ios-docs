---
layout: post
title: Getting Started | SfCircularGauge | iOS | Syncfusion
description: Header
platform: ios
control: SfCircularGauge
documentation: ug
---

# Header

Header support allows you to show text, an image, or any UI content inside the Gauge control. A circular gauge can be made self-descriptive about the data it is measuring through the use of a header.

## Adding Header in Circular Gauge

### Header

The Header can be used to set a unique header for the Circular Gauge. You can add text as headers in a circular gauge, multiple headers can be added in a circular gauge.

#### Position

This property places the header in a circular gauge. The value for Position should be specified in `offset` value. By default, it is placed at (0.33,0.63).

{% highlight c# %}

    gauge = new SFCircularGauge ();
    SFGaugeHeader header = new SFGaugeHeader();
    header.Text = (NSString)"Speedometer";
    header.Position = new CGPoint (0.4f, 0.7f);
    header.TextColor = UIColor.Gray;
    gauge.Headers.Add(header);
    this.AddSubview (gauge);
    this.control = gauge;

{% endhighlight %}

![](iOS_Images/Header.png)
