---
layout: post
title: Getting Started | SfCircularGauge | iOS | Syncfusion
description: SCALES
platform: xamarin.iOS
control: SfCircularGauge
documentation: ug
---

# SCALES

The Scales contains a Collection of Circular Scale which integrates labels, tick marks, and a rim to customize the basic look and feel of the `SfCircularGauge`.

## Scale

Circular Scale contains three sub elements such as Rim, Ticks, and Labels. It defines the Radius, start angle and sweep angle, overall minimum and maximum values, and frequency of labels and tick marks. It can have multiple ranges.

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

## Multiple Scale

It helps to be able to add multiple scales to the same circular gauge, and also it helps to customize all the scales in a Scales collection.

{% highlight c# %}

    ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
    SFCircularScale scale = new SFCircularScale();
    scale.MinorTicksPerInterval = 1;
	scale.LabelColor = UIColor.White;
	scale.MinorTickSettings.Color = UIColor.White;
	scale.MajorTickSettings.Color = UIColor.White;
	
	SFCircularRange range = new SFCircularRange();
	range.StartValue = 0;
	range.EndValue = 60;
	range.Offset = 1;
	range.Color = UIColor.Gray;
	range.Width = 11;
	scale.Ranges.Add(range);
	
	SFCircularRange rangeLayer = new SFCircularRange();
	rangeLayer.StartValue = 60;
	rangeLayer.EndValue = 100;
	rangeLayer.Offset = 1;
	rangeLayer.Color = UIColor.Red;
	rangeLayer.Width = 11;
	scale.Ranges.Add(rangeLayer);
	
	ObservableCollection<SFCircularPointer> pointers = new ObservableCollection<SFCircularPointer>();
	SFMarkerPointer markerPointer = new SFMarkerPointer();
	markerPointer.Value = 30;
	markerPointer.Color = UIColor.Green;
	markerPointer.Offset = (float)0.8;
	markerPointer.MarkerShape = MarkerShape.InvertedTriangle;
	markerPointer.EnableAnimation = false;
	pointers.Add(markerPointer);
	scale.CircularPointers = pointers;
    scales.Add(scale);
	
	SFCircularScale circularSsPerInterval = 1;
	circularScale.ScaleScale = new SFCircularScale();
    circularScale.ScaleStartOffset = (float)0.5;
	circularScale.ScaleEndOffSet = (float)0.55;
	circularScale.LabelOffset = (float)0.35;
	circularScale.LabelColor = UIColor.White;
	scale.MinorTickSettings.StartOffset = (float)0.5;
	scale.MajorTickSettings.StartOffset = (float)0.5;
	scale.MinorTickSettings.EndOffset = (float)0.45;
	scale.MajorTickSettings.EndOffset = (float)0.45;
	scale.MinorTickSettings.Width = 2;
	scale.MajorTickSettings.Width = 4;
	scale.MinorTickSettings.Color = UIColor.White;
	scale.MajorTickSettings.Color = UIColor.White;
	
	SFCircularRange circularRange = new SFCircularRange();
	circularRange.StartValue = 0;
	circularRange.EndValue = 60;
	circularRange.Offset = (float)0.55;
	circularRange.Color = UIColor.Gray;
	circularRange.Width = 11;
	circularScale.Ranges.Add(range);
	
	SFCircularRange circularRangeLayer = new SFCircularRange();
	circularRangeLayer.StartValue = 60;
	circularRangeLayer.EndValue = 100;
	circularRangeLayer.Offset = (float)0.55;
	circularRangeLayer.Color = UIColor.Red;
	circularRangeLayer.Width = 11;
	circularScale.Ranges.Add(circularRangeLayer);
	
	ObservableCollection<SFCircularPointer> circularPointers = new ObservableCollection<SFCircularPointer>();
	SFNeedlePointer needlePointer = new SFNeedlePointer();
	needlePointer.Value = 30;
	needlePointer.Color = UIColor.Green;
	needlePointer.EnableAnimation = false;
	needlePointer.LengthFactor = (float)0.5;
	circularPointers.Add(needlePointer);
	circularScale.Pointers = circularPointers;
    scales.Add(circularScale);
    circular.CircularScales = scales;  
    this.View.AddSubview(circular);
	
{% endhighlight %}

![](iOS_Images/Multiple_Scales.png)

### Scale Direction

`Direction` property enables you to render the gauge scale either in `ClockWise` or in `AntiClockWise` direction.

{% highlight c# %}
 
    SFCircularGauge circular = new SFCircularGauge(this);
    ObservableCollection<SFCircularScale> circularScales = new ObservableCollection<SFCircularScale();
    SFCircularScale scale = new SFCircularScale();
    scale.StartValue = 0;
    scale.EndValue = 100;
    scale.Direction = SFCircularScaleDirection.AntiClockwise;
    circularScales.Add(scale);
    circular.Scales = circularScales;
    this.View.AddSubview(circular);
	
{% endhighlight %}

![](iOS_Images/AntiClockwise.png)

![](iOS_Images/Clockwise.png)

### Auto Angle

Scale labels can be rotated automatically based on the current angle. To enable or disable the Auto Angle, you can use `EnableAutoAngle` property.

{% highlight c# %}

    SFCircularGauge circular = new SFCircularGauge(this);
    ObservableCollection<SFCircularScale> circularScales = new ObservableCollection<SFCircularScale();
    SFCircularScale scale = new SFCircularScale();
    scale.StartValue = 0;
    scale.EndValue = 100;
    scale.EnableAutoAngle = true;
    circularScales.Add(scale);
    circular.Scales = circularScales;
    this.View.AddSubview(circular);
	
{% endhighlight %}

![](iOS_Images/Auto_Angle.png)

### Range color for Labels and Ticks

You can set the range color to scale labels and ticks by enabling `UseRangeColorForLabels` property.

{% highlight c# %}

    SFCircularGauge circular = new SFCircularGauge(this);
    ObservableCollection<SFCircularScale> circularScales = new ObservableCollection<SFCircularScale();
    SFCircularScale scale = new SFCircularScale();
    scale.StartValue = 0;
    scale.EndValue = 100; 
    scale.UseRangeColorForLabels  = true;
    circularScales.Add(scale);
    circular.Scales = circularScales;
    this.View.AddSubview(circular);
	
{% endhighlight %}

![](iOS_Images/Range_Color.png)

### LabelCreated

This event is triggered when the scale label is created. The argument contains the following information.

* `LabelCreated` - used to get or set the scale label content.