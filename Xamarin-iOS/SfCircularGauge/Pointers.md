---

layout: post
title: Getting Started | SfCircularGauge | iOS | Syncfusion
description: Pointers   
platform: xamarin.iOS
control: SfCircularGauge
documentation: ug

---

# Pointers

You can add multiple pointers to the gauge to point multiple values on the same scale. It is used to show low and high values at the same time. The value of the pointer is set by using the [`Value`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularPointer.html#Syncfusion_SfGauge_iOS_SFCircularPointer_Value) property.

## Needle pointer

[`SFNeedlePointer`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFNeedlePointer.html) contains three parts, namely needle, knob, and tail and that can be placed on a gauge to mark the values.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();   
            scale.StartValue = 0;
            scale.EndValue = 100;
            SFNeedlePointer needlePointer = new SFNeedlePointer();
            needlePointer.Value = 70;
            scale.Pointers.Add(needlePointer);
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](pointers_images/needle-pointer/default.png)

### Setting needle pointer type

The appearance of the needle pointer can be customized by using the [`PointerType`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularPointer.html#Syncfusion_SfGauge_iOS_SFCircularPointer_PointerType) property. The default value of this property is `Triangle`. This is an enum property, and it has the following options:

1. Bar
2. Triangle

### Setting bar pointer type

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();   
            scale.StartValue = 0;
            scale.EndValue = 100;
            SFNeedlePointer needlePointer = new SFNeedlePointer();
            needlePointer.Value = 60;
            needlePointer.PointerType = SFCiruclarGaugePointerType.SFCiruclarGaugePointerTypeBar;
            scale.Pointers.Add(needlePointer);
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](pointers_images/needle-pointer/bar-pointer.png)

### Setting needle pointer type

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();   
            scale.StartValue = 0;
            scale.EndValue = 100;
            SFNeedlePointer needlePointer = new SFNeedlePointer();
            needlePointer.Value = 60;
            needlePointer.PointerType = SFCiruclarGaugePointerType.SFCiruclarGaugePointerTypeTriangle;
            scale.Pointers.Add(needlePointer);
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](pointers_images/needle-pointer/needle-pointer.png)

### Needle pointer customization

The length of the needle is controlled by using the [`LengthFactor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularPointer.html#Syncfusion_SfGauge_iOS_SFCircularPointer_LengthFactor) property. The [`LengthFactor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularPointer.html#Syncfusion_SfGauge_iOS_SFCircularPointer_LengthFactor) property’s minimum and maximum bounds are 0 and 1. The needle’s UI is customized by using the [`Color`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularPointer.html#Syncfusion_SfGauge_iOS_SFCircularPointer_Color) and [`Width`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularPointer.html#Syncfusion_SfGauge_iOS_SFCircularPointer_Width) properties.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();   
            scale.StartValue = 0;
            scale.EndValue = 100;
            SFNeedlePointer needlePointer = new SFNeedlePointer();
            needlePointer.Value = 60;
            needlePointer.Color = UIColor.FromRGB(0, 191, 255);
            needlePointer.Width = 7f;
            needlePointer.LengthFactor = 0.7f;
            scale.Pointers.Add(needlePointer);
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](pointers_images/needle-pointer/needle-customization.png)

### Knob customization

Knob of the needle pointer can be customized by using the [`KnobColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularPointer.html#Syncfusion_SfGauge_iOS_SFCircularPointer_KnobColor), [`KnobRadius`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularPointer.html#Syncfusion_SfGauge_iOS_SFCircularPointer_KnobRadius), [`KnobRadiusFactor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularPointer.html#Syncfusion_SfGauge_iOS_SFCircularPointer_KnobRadiusFactor), [`KnobStrokeColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFNeedlePointer.html#Syncfusion_SfGauge_iOS_SFNeedlePointer_KnobStrokeColor), and [`KnobStrokeWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFNeedlePointer.html#Syncfusion_SfGauge_iOS_SFNeedlePointer_KnobStrokeWidth) properties. You can set the radius of knob to pixel and percentage values by using the [`KnobRadius`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularPointer.html#Syncfusion_SfGauge_iOS_SFCircularPointer_KnobRadius) and [`KnobRadiusFactor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularPointer.html#Syncfusion_SfGauge_iOS_SFCircularPointer_KnobRadiusFactor) properties.

{% highlight c# %}

             SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();   
            scale.StartValue = 0;
            scale.EndValue = 100;
            SFNeedlePointer needlePointer = new SFNeedlePointer();
            needlePointer.Value = 10;
            needlePointer.KnobRadius = 15;
            needlePointer.KnobStrokeColor = UIColor.FromRGB(0, 125, 209);
            needlePointer.KnobColor = UIColor.White;
            needlePointer.KnobStrokeWidth = 8;
            scale.Pointers.Add(needlePointer);
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](pointers_images/needle-pointer/knob-customization.png)

### Setting tail for needle pointer

Tail of the needle pointer can be customized by using the [`TailColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFNeedlePointer.html#Syncfusion_SfGauge_iOS_SFNeedlePointer_TailColor), [`TailLengthFactor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFNeedlePointer.html#Syncfusion_SfGauge_iOS_SFNeedlePointer_TailLengthFactor), [`TailStrokeColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFNeedlePointer.html#Syncfusion_SfGauge_iOS_SFNeedlePointer_TailStrokeColor), and [`TailStrokeWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFNeedlePointer.html#Syncfusion_SfGauge_iOS_SFNeedlePointer_TailStrokeWidth) properties.

{% highlight c# %}

             SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();   
            scale.StartValue = 0;
            scale.EndValue = 100;
            SFNeedlePointer needlePointer = new SFNeedlePointer();
            needlePointer.Value = 90;
            needlePointer.KnobRadius = 15;
            needlePointer.TailColor = UIColor.FromRGB(117, 117, 117);
            needlePointer.TailLengthFactor = 0.2f;
            needlePointer.TailStrokeWidth = 1;
            needlePointer.TailStrokeColor = UIColor.FromRGB(117, 117, 117);
            scale.Pointers.Add(needlePointer);
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](pointers_images/needle-pointer/tail.png)

## Range pointer

A range pointer is an accenting line or shaded background range that can be placed on a gauge to mark the values. The [`RangeStart`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFRangePointer.html#Syncfusion_SfGauge_iOS_SFRangePointer_RangeStart) property allows you to set the starting value of the range pointer.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();   
            scale.StartValue = 0;
            scale.EndValue = 100;
            SFRangePointer rangePointer = new SFRangePointer();
            rangePointer.RangeStart = 0;
            rangePointer.Value = 85;
            scale.Pointers.Add(rangePointer);
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](pointers_images/range-pointer/range-pointer.png)

### Range pointer customization

The range pointer’s UI is customized by using the [`Color`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularPointer.html#Syncfusion_SfGauge_iOS_SFCircularPointer_Color) and [`Width`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularPointer.html#Syncfusion_SfGauge_iOS_SFCircularPointer_Width) properties. First, you should set the [`Offset`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFRangePointer.html#Syncfusion_SfGauge_iOS_SFRangePointer_Offset) property for range pointer, and then increase the thickness of the range pointer.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();   
            scale.StartValue = 0;
            scale.EndValue = 100;
            SFRangePointer rangePointer = new SFRangePointer();
            rangePointer.Value = 60;
            rangePointer.Color = UIColor.FromRGB(0,255,255);
            rangePointer.Width = 30;
            rangePointer.Offset = 0.7f;
            scale.Pointers.Add(rangePointer);
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](pointers_images/range-pointer/rangepointer-customization.png)

### Setting position for range pointer

The [`SFRangePointer`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFRangePointer.html) in the scale can be placed inside or outside of the scale by using the following two ways:

1. The [`Offset`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFRangePointer.html#Syncfusion_SfGauge_iOS_SFRangePointer_Offset) property.
2. The [`StartOffset`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFRangePointer.html#Syncfusion_SfGauge_iOS_SFRangePointer_StartOffset) and [`EndOffset`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFRangePointer.html#Syncfusion_SfGauge_iOS_SFRangePointer_EndOffset) properties.

#### Setting offset for range pointer

{% highlight c# %}

           SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();   
            scale.StartValue = 0;
            scale.EndValue = 100;
            SFRangePointer rangePointer = new SFRangePointer();
            rangePointer.Value = 100;
            rangePointer.Offset = 0.5f;
            rangePointer.Width = 30;
            scale.Pointers.Add(rangePointer);
            scales.Add(scale);
            circularGauge.Scales = scales; 
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](pointers_images/range-pointer/rangepointer-offset.png)

#### Setting start and end offset for range pointer

{% highlight c# %}

           SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();   
            scale.StartValue = 0;
            scale.EndValue = 100;
            SFRangePointer rangePointer = new SFRangePointer();
            rangePointer.RangeStart = 0;
            rangePointer.Value = 85;
            rangePointer.StartOffset = 0.5f;
            rangePointer.EndOffset = 0.7f;
            scale.Pointers.Add(rangePointer);
            scales.Add(scale);
            circularGauge.Scales = scales; 
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](pointers_images/range-pointer/rangepointer-start-end-offset.png)

### Setting range cap for range pointer

The [`RangeCap`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFRangePointer.html#Syncfusion_SfGauge_iOS_SFRangePointer_RangeCap) property provides options to position the range cap of the [`SFRangePointer`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFRangePointer.html), which contains the start, end, both, and none options. The [`RangeCap`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFRangePointer.html#Syncfusion_SfGauge_iOS_SFRangePointer_RangeCap) property is an enum property.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();   
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.MajorTickSettings.Offset = 0.9f;
            scale.MinorTickSettings.Offset = 0.9f;
            scale.LabelOffset = 0.75f;
            scale.ScaleStartOffset = 0.9f;
            scale.ScaleEndOffSet = 1;
            SFRangePointer rangePointer = new SFRangePointer();
            rangePointer.RangeStart = 15;
            rangePointer.StartOffset = 0.9f;
            rangePointer.EndOffset = 1;
            rangePointer.Value = 80;
            rangePointer.RangeCap = SFCiruclarGaugeRangeCap.End;
            scale.Pointers.Add(rangePointer);
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](pointers_images/range-pointer/range-cap.png)

## Marker pointer

The different types of marker shapes are used to mark the pointer values in a scale. You can change the marker shape by using the [`MarkerShape`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFMarkerPointer.html#Syncfusion_SfGauge_iOS_SFMarkerPointer_MarkerShape) property. Gauge supports the following types of marker shapes:

* Circle
* Rectangle
* Triangle
* Inverted triangle
* Diamond
* Image

The image is used to denote the pointer value instead of rendering the marker shape. It can be achieved by setting the [`MarkerShape`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFMarkerPointer.html#Syncfusion_SfGauge_iOS_SFMarkerPointer_MarkerShape) to `Image`, and assigning the image path to [`ImageSource`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFMarkerPointer.html#Syncfusion_SfGauge_iOS_SFMarkerPointer_ImageSource) in pointer.

{% highlight c# %}

           SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();   
            scale.StartValue = 0;
            scale.EndValue = 100;
            SFMarkerPointer markerPointer = new SFMarkerPointer();
            markerPointer.Value = 70;
            markerPointer.MarkerShape = MarkerShape.Triangle;
            scale.Pointers.Add(markerPointer);
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](pointers_images/marker-pointer/marker-pointer.png)

### Setting image marker shape

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();   
            scale.StartValue = 0;
            scale.EndValue = 100;
            SFMarkerPointer markerPointer = new SFMarkerPointer();
            markerPointer.Value = 40;
            markerPointer.MarkerShape = MarkerShape.Image;
            markerPointer.ImageSource = "location.png";
            scale.Pointers.Add(markerPointer);
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](pointers_images/marker-pointer/image.png)

### Marker pointer customization

The marker can be customized in terms of color, width, and height by using the [`Color`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularPointer.html#Syncfusion_SfGauge_iOS_SFCircularPointer_Color), [`MarkerWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFMarkerPointer.html#Syncfusion_SfGauge_iOS_SFMarkerPointer_MarkerWidth), and [`MarkerHeight`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFMarkerPointer.html#Syncfusion_SfGauge_iOS_SFMarkerPointer_MarkerHeight) properties in pointer. First, you should set the [`Offset`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFMarkerPointer.html#Syncfusion_SfGauge_iOS_SFMarkerPointer_Offset) property for marker pointer, then increase the height and width of the marker pointer.

{% highlight c# %}

           SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();   
            scale.StartValue = 0;
            scale.EndValue = 100;
            SFMarkerPointer markerPointer = new SFMarkerPointer();
            markerPointer.Value = 70;
            markerPointer.Color = UIColor.FromRGB(255,192,203);
            markerPointer.MarkerHeight = 20;
            markerPointer.MarkerWidth = 20;
            markerPointer.Offset = 1;
            scale.Pointers.Add(markerPointer);
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](pointers_images/marker-pointer/markerpointer-customization.png)

### Setting multiple pointers

In addition to the default pointer, you can add n number of pointers to a scale by using the [`Pointers`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_Pointers) property.

{% highlight c# %}

          SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();   
            scale.StartValue = 0;
            scale.EndValue = 100;
            ObservableCollection<SFCircularPointer> pointers = new ObservableCollection<SFCircularPointer>();
            SFMarkerPointer markerPointer = new SFMarkerPointer();
            markerPointer.Value = 40;
            pointers.Add(markerPointer);

            SFCircularScale scale1 = new SFCircularScale();
            scale1.StartValue = 0;
            scale1.EndValue = 100;
            scale1.ShowLabels = false;
            scale1.ShowTicks = false;
            scale1.ScaleStartOffset = 0.5f;
            scale1.ScaleEndOffSet = 0.6f;

            SFNeedlePointer needlePointer = new SFNeedlePointer();
            needlePointer.Value = 60;
            needlePointer.LengthFactor = 0.3f;
            pointers.Add(needlePointer);

            scale1.Pointers = pointers;
            scale.Pointers = pointers;
            scales.Add(scale1);

            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](pointers_images/marker-pointer/multiple-pointers.png)

### Setting animation for pointer

The [`EnableAnimation`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularPointer.html#Syncfusion_SfGauge_iOS_SFCircularPointer_EnableAnimation) property is a Boolean property that enables or disables the animation of the pointers in circular gauge.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.RimColor = UIColor.FromRGB(211, 211, 211);
            scale.RimWidth = 30;
            scale.RadiusFactor = 1;
            scale.ShowTicks = false;
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.Interval = 10;
            scale.LabelOffset = 0.75f;
            scale.LabelColor = UIColor.FromRGB(66, 66, 66);
            scale.LabelFont = UIFont.FromName("Helvetica", 15f);

            SFRangePointer pointer1 = new SFRangePointer();
            pointer1.Color = UIColor.Orange;
            pointer1.Width = 30;
            pointer1.Offset = 1;
            pointer1.EnableAnimation = true;
            pointer1.AnimationDuration = 5;
            pointer1.Value = 80;
            scale.Pointers.Add(pointer1);

            SFNeedlePointer pointer2 = new SFNeedlePointer();
            pointer2.Width = 7;
            pointer2.LengthFactor = 0.55f;
            pointer2.Color = UIColor.FromRGB(211, 211, 211);
            pointer2.KnobColor = UIColor.White;
            pointer2.TailColor = UIColor.FromRGB(211, 211, 211);
            pointer2.TailLengthFactor = 0.2f;
            pointer2.PointerType = SFCiruclarGaugePointerType.SFCiruclarGaugePointerTypeTriangle;
            pointer2.KnobRadius = 15;
            pointer2.KnobRadius = 12;
            pointer2.Value = 80;
            pointer2.AnimationDuration = 5;
            pointer2.TailStrokeWidth = 2;
            pointer2.TailStrokeColor = UIColor.FromRGB(211, 211, 211);
            pointer2.KnobStrokeColor = UIColor.FromRGB(211, 211, 211);
            pointer2.KnobStrokeWidth = 8;
            scale.Pointers.Add(pointer2);
            circularGauge.Scales.Add(scale);
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](pointers_images/marker-pointer/animation.gif)

### Setting pointer drag

Pointers can be dragged over the scale value. It can be achieved by clicking and dragging the pointer. To enable or disable the pointer drag, use the `EnableDragging` property.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.RimColor = UIColor.FromRGB(0 ,191 , 255);
            scale.RimWidth = 20;
            scale.RadiusFactor = 1;
            scale.ShowTicks = false;
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.Interval = 10;
            scale.LabelOffset = 0.75f;
            scale.LabelColor = UIColor.FromRGB(66, 66, 66);
            scale.LabelFont = UIFont.FromName("Helvetica", 15f);

            SFMarkerPointer pointer1 = new SFMarkerPointer();
            pointer1.MarkerShape = MarkerShape.Triangle;
            pointer1.Color = UIColor.FromRGB(72, 61,139);
            pointer1.MarkerHeight = 18;
            pointer1.MarkerWidth = 18;
            pointer1.Value = 30;
            pointer1.EnableAnimation = false;
            pointer1.EnableDragging = true;
            scale.Pointers.Add(pointer1);

            circularGauge.Scales.Add(scale);
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](pointers_images/marker-pointer/pointer-interaction.gif)
