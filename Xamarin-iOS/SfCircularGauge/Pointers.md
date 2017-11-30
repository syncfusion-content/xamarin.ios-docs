---
layout: post
title: Getting Started | SfCircularGauge | iOS | Syncfusion
description: POINTERS
platform: xamarin.iOS
control: SfCircularGauge
documentation: ug
---

# POINTERS

You can add multiple pointers to the gauge to point at multiple values on the same scale. This can be useful for showing a low and a high value at the same time. The value of the pointer is set using the `Value` property. There are two types of pointers. You can choose a pointer using the `PointerType` property. Movement of the pointer can be animated by enabling the `EnableAnimation` property.

## Needle Pointer  

A needle pointer contains two parts, the needle and the knob that can be placed on a gauge to mark values. The needle length is controlled by the `LengthFactor` property. The `LengthFactor` property’s minimum and maximum bounds are 0 and 1. The needle’s UI is customized by the `Color` and `Width` properties. The user can modify the Knob’s size by changing the `KnobRadius` property.

### Needle Pointer Type

`NeedlePointer` appearance can be customized by using the `PointerType` property the default value of this property is Rectangle.
It is enum includes the following option.

•	SFCircularGaugePointerTypeBar
•	SFCircularGaugePointerTypeTriangle

{% highlight c# %}

    gauge = new SFCircularGauge ();
    scale = new SFCircularScale ();
    NSMutableArray scales = new NSMutableArray();
    NSMutableArray pointers = new NSMutableArray();
    needlePointer = new SFNeedlePointer();
    needlePointer.PointerType = SFCircularGaugePointerType.SFCircularGaugePointerTypeBar;
    needlePointer.Value = 70;
    needlePointer.Color = UIColor.Gray;
    needlePointer.KnobRadius = 12;
    needlePointer.KnobColor = UIColor.FromRGB(43, 191, 184);
    needlePointer.Width = 2.5f;
    needlePointer.LengthFactor =nfloat.Parse("0.7");
    scale.Pointers = pointers;
    scales.Add(scale);
    gauge.Scales = scales;
    this.View.AddSubview(circular);

{% endhighlight %}

![](iOS_Images/NeedlePointer.png)

### Knob Customization

Knob of `NeedlePointer` can be customized by using `KnobColor`, `KnobRadius`, `KnobRadiusFactor`, `KnobStrokeColor`, and `KnobStrokeWidth` properties. You can set the radius of knob as pixel value by using `KnobRadius` property, and as percentage value by using `KnobRadiusFactor` property.

{% highlight c# %}
    
    SFCircularGauge circular = new SFCircularGauge(this);
    ObservableCollection<SFCircularScale> circularScales = new ObservableCollection<SFCircularScale();
    SFCircularScale scale = new SFCircularScale();
    ObservableCollection<SFCircularPointer> pointers = new ObservableCollection<SFCircularPointer();
    SFNeedlePointer needlePointer = new SFNeedlePointer();
    needlePointer.Value = 90;
    needlePointer.KnobColor = UIColor.White;
    needlePointer.KnobRadius = 15;
    needlePointer.KnobStrokeColor = UIColor.Blue;
    needlePointer.KnobStrokeWidth = 8; 
    pointers.Add(needlePointer);
    scale.Pointers = pointers;
    circularScales.Add(scale);
    circular.Scales = circularScales;
    this.View.AddSubview(circular);

{% endhighlight %}

![](iOS_Images/Knob_Customization.png)

### Tail Support

Tail of `NeedlePointer` can be customized by using `TailColor`, `TailLengthFactor`, `TailStrokeColor`, and `TailStrokeWidth` properties.

{% highlight c# %}

    SFCircularGauge circular = new SFCircularGauge(this);
    ObservableCollection<SFCircularScale> circularScales = new ObservableCollection<SFCircularScale();
    SFCircularScale scale = new SFCircularScale();
    ObservableCollection<SFCircularPointer> pointers = new ObservableCollection<SFCircularPointer();
    SFNeedlePointer needlePointer = new SFNeedlePointer();
    needlePointer.Value = 90;
    needlePointer.TailColor = UIColor.DarkGray;
    needlePointer.TailLengthFactor = 0.2;
    needlePointer.TailStrokeWidth = 1;
    needlePointer.TailStrokeColor = UIColor.DarkGray;
    pointers.Add(needlePointer);
    scale.Pointers = pointers;
    circularScales.Add(scale);
    circular.Scales = circularScales;
    this.View.AddSubview(circular);

{% endhighlight %}

![](iOS_Images/Tail.png)

##Range Pointer

A range pointer is an accenting line or shaded background range that can be placed on a gauge to mark values. The range pointer’s UI is customized by the `Color` and `Width` properties.

### Range Pointer Position

The `RangePointer` in the scale can be placed inside the scale or outside the scale by setting `Offset` property.

{% highlight c# %}

    gauge = new SFCircularGauge ();
    scale = new SFCircularScale ();
    NSMutableArray scales = new NSMutableArray();
    rangePointer = new SFRangePointer();
    rangePointer.Value = 70;
    rangePointer.Color = UIColor.FromRGB(43, 191, 184);
    rangePointer.Width = 5;
    pointers.Add(rangePointer);
    scale.Pointers = pointers;
    scales.Add(scale);
    gauge.Scales = scales;
    this.View.AddSubview(circular);

{% endhighlight %}

![](iOS_Images/RangePointer.png)

### Range Cap

`RangeCap` is an enum property that provides the position options for range cap of the `RangePointer`, which contains Start, End, Both, and None options.

{% highlight c# %}

    SFCircularGauge circular = new SFCircularGauge();
    ObservableCollection<SFCircularScale> circularScales = new ObservableCollection<SFCircularScale();
    SFCircularScale scale = new SFCircularScale();
    ObservableCollection<SFCircularPointer> pointers = new ObservableCollection<SFCircularPointer();
    SFRangePointer rangePointer = new SFRangePointer();
    rangePointer.Value = 80;
    rangePointer.RangeCap = SFCircularGaugeRangeCap.Both;
    pointers.Add(rangePointer);
    scale.Pointers = pointers;
    circularScales.Add(scale);
    circular.Scales = circularScales;
    this.View.AddSubview(circular);

{% endhighlight %}

![](iOS_Images/Range_Cap.png)

## Marker Pointer

Different types of marker shape can be used to mark the pointer value in scale. You can change the marker shape by using `MarkerShape` property in pointer. Gauge supports the following types of  marker shape:-

* Circle
* Rectangle
* Triangle
* InvertedTriangle
* Diamond
* Image

The image can be used instead of rendering marker shape to denote the pointer value. It can be achieved by setting `MarkerShape` to Image, and assigning image path to `ImageSource` in pointer.

{% highlight c# %}

    SFCircularGauge circular = new SFCircularGauge(this);
    ObservableCollection<SFCircularScale> circularScales = new ObservableCollection<SFCircularScale();
    SFCircularScale scale = new SFCircularScale();
    ObservableCollection<SFCircularPointer> pointers = new ObservableCollection<SFCircularPointer>();
    SFMarkerPointer markerPointer = new SFMarkerPointer();
    markerPointer.Value = 80;
    markerPointer.MarkerShape = MarkerShape.Triangle;
    markerPointer.Color = UIColor.Green;
    pointers.Add(markerPointer);
    scale.Pointers = pointers;
    circularScales.Add(scale);
    circular.Scales = circularScales;
    this.View.AddSubview(circular);

{% endhighlight %}

![](iOS_Images/Marker_Pointer.png)

### Marker Pointer Customization

The marker can be customized in terms of color, width, and height by using `Color`, `MarkerWidth`, and `MarkerHeight` property in pointer.

{% highlight c# %}

    SFCircularGauge circular = new SFCircularGauge(this);
    ObservableCollection<SFCircularScale> circularScales = new ObservableCollection<SFCircularScale();
    SFCircularScale scale = new SFCircularScale();
    ObservableCollection<SFCircularPointer> pointers = new ObservableCollection<SFCircularPointer>();
    SFMarkerPointer markerPointer = new SFMarkerPointer();
    markerPointer.Value = 80;
    markerPointer.MarkerShape = MarkerShape.Triangle;
    markerPointer.Color = UIColor.Red;
    markerPointer.MarkerHeight = 30;
    markerPointer.MarkerWidth = 30;
    pointers.Add(markerPointer);
    scale.Pointers = pointers;
    circularScales.Add(scale);
    circular.Scales = circularScales;
    this.View.AddSubview(circular);

{% endhighlight %}

![](iOS_Images/Marker_Customization.png)

### Multiple Pointers

In addition to the default pointer, you can add n number of pointers to a scale by using `Pointers` property.

{% highlight c# %}

    SFCircularGauge circular = new SFCircularGauge(this);
    ObservableCollection<SFCircularScale> circularScales = new ObservableCollection<SFCircularScale();
    SFCircularScale scale = new SFCircularScale();
    ObservableCollection<SFCircularPointer> pointers = new ObservableCollection<SFCircularPointer>();
    SFMarkerPointer markerPointer = new SFMarkerPointer();
    markerPointer.Value = 80;
    markerPointer.MarkerShape = MarkerShape.Triangle;
    markerPointer.Color = UIColor.Green;
    markerPointer.Offset = 0.79;
    pointers.Add(markerPointer);
    SFNeedlePointer needlePointer = new SFNeedlePointer();
    needlePointer.Value = 80;
    needlePointer.Color = UIColor.Purple;
    needlePointer.LengthFactor = 0.5;
    needlePointer.KnobColor = UIColor.White;
    needlePointer.KnobStrokeColor = UIColor.DarkGray;
    needlePointer.KnobStrokeWidth = 2;
    needlePointer.Width = 10;
    needlePointer.PointerType = SFCircularGaugePointerType.SFCircularGaugePointerTypeTriangle;
    pointers.Add(needlePointer);
    SFRangePointer rangePointer = new SFRangePointer();
    rangePointer.Value = 80;
    rangePointer.Color = UIColor.Yellow;
    rangePointer.Offset = 0.5;
    rangePointer.Width = 10;
    pointers.Add(rangePointer);
    scale.Pointers = pointers;
    circularScales.Add(scale);
    circular.Scales = circularScales;
    this.View.AddSubview(circular);

{% endhighlight %}

![](iOS_Images/Multiple_Pointer.png)

## Pointer Animation

EnableAnimation property is a Boolean property that enables or disables the animation of the pointers in CircularGauge.

{% highlight c# %}

    SFNeedlePointer needlePointer = new SFNeedlePointer();
    needlePointer.Value = 60;    
    needlePointer.EnableAnimation = true;          
    pointers.Add(needlePointer);
    scale.Pointers = pointers;
    circularScales.Add(scale);
    circular.Scales = circularScales;

{% endhighlight  %}

### Pointer Drag

Pointers can be dragged over the scale value. This can be achieved by clicking and dragging the pointer. To enable or disable the pointer drag, use `EnableDragging` property.

{% highlight c# %}

    SFCircularGauge circular = new SFCircularGauge(this);
    ObservableCollection<SFCircularScale> circularScales = new ObservableCollection<SFCircularScale();
    SFCircularScale scale = new SFCircularScale();
    ObservableCollection<SFCircularPointer> pointers = new ObservableCollection<SFCircularPointer>();
    SFNeedlePointer needlePointer = new SFNeedlePointer();
    needlePointer.Value = 90;
    needlePointer.Color = UIColor.DarkGray;
    needlePointer.KnobColor = UIColor.DarkGray;
     needlePointer.PointerType = SFCircularGaugePointerType.SFCircularGaugePointerTypeTriangle;
    needlePointer.EnableDragging = true;
    pointers.Add(needlePointer);
    scale.Pointers = pointers;
    circularScales.Add(scale);
    circular.Scales = circularScales;

{% endhighlight  %}