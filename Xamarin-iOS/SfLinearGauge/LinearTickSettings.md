---
layout: post
title: LinearTickSettings in Syncfusion LinearGauge control in Xamarin.iOS
description: Learn how to add major and minor tick settings in  LinearGauge
platform: Xamarin.iOS
control: LinearGauge
documentation: ug
---
# LinearTickSettings

Ticks are categorized into two types: Major and Minor. These ticks are arranged with respect to the specified frequency i.e., Interval of the linear scale. The minor ticks are displayed using the 
MinorTicksPerInterval property.

{% highlight c# %}

	LinearTickSettings minor = new LinearTickSettings ();
	minor.Length = 10;
	minor.Color = Color.FromRgb (175, 175, 175);
	minor.Thickness = 1;
	scale.MinorTickSettings = minor;
	//Major Ticks setting
	LinearTickSettings major = new LinearTickSettings ();
	major.Length = 10;
	major.Color = Color.FromRgb (175, 175, 175);
    major.Thickness = 1;
    scale.MajorTickSettings = major; 
	
{% endhighlight %}


![](images/Tick.png)

