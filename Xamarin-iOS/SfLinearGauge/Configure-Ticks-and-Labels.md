---
layout: post
title: Scale of syncfusion Lineargauge control in Xamarin.iOS
description: Learn how to set maximum and minim value of lineargauge.
platform: Xamarin.iOS
control: LinearGauge
documentation: ug
---

# Configure Ticks and Labels

LinearScale is used to set the Labels, Values and Ticks to specify the basic look and feel of the SfLinearGauge. It defines the overall minimum and maximum values, along with the frequency of labels and ticks through the interval of the scale. It can contain multiple ranges within a scale. It also contains one or more pointers to point out the measures of the linear scale.

{% tabs %}

{% highlight c# %}

SFLinearScale scale=new SFLinearScale();
scale.MinimumValue=0;
scale.MaximumValue=100;
scale.Interval=20;
scale.ScaleBarLength=100;
scale.ScaleBarColor= UIColor.FromRGB (250, 236, 236);
scale.LabelColor = UIColor.FromRGB (84, 84, 84); 
scale.MinorTicksPerInterval = 1;
scale.ScaleBarSize = 13;
scale.ScalePosition = SFLinearGaugeScalePosition.SFLinearGaugeScalePositionBackWard;	
sfLinearGauge.Scales.Add(scale);
	
{% endhighlight %}

{% endtabs %}


![](images/Scale.png)