---

layout: post
title: Scales in LinearGauge for Xamarin.iOS
description:  Learn how to define settings of linear scale in LinearGauge
platform:  Xamarin.iOS
control: LinearGauge
documentation: ug

---

# Scales

Scales is a collection of [`SFLinearScale`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale.html), which integrates labels, tick marks, ranges, and pointers to customize the basic look and feel of the [`SFLinearGauge`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearGauge.html).

## Linear scale

[`SFLinearScale`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale.html) contains sub elements such as ticks, labels, [`Ranges`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale~Ranges.html), and [`Pointers`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale~Pointers.html). 

{% highlight c# %}

             SFLinearGauge linearGauge = new SFLinearGauge();
            linearGauge.BackgroundColor = UIColor.White;
            linearGauge.Header = new SFLinearLabel();
            SFLinearScale linearScale = new SFLinearScale();
            linearScale.ScaleBarColor = UIColor.FromRGB(224, 224, 224);
            linearScale.LabelColor = UIColor.FromRGB(66, 66, 66);
            linearScale.MajorTickSettings.Color = UIColor.Gray;
            linearScale.MinorTickSettings.Color = UIColor.Gray;
            linearScale.MajorTickSettings.Length = 12;
            linearScale.MinorTickSettings.Length = 5;
            linearScale.MinorTicksPerInterval = 3;
            linearGauge.Scales.Add(linearScale);
            this.View.AddSubview(linearGauge);
  
{% endhighlight %}

![](scales_images/scale1.png)

## Setting minimum and maximum values for scale

To change minimum and maximum values of linear scale, use the [`Minimum`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale~Minimum.html) and [`Maximum`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale~Maximum.html) properties as shown in the following code snippet.

{% highlight c# %}

            SFLinearGauge linearGauge = new SFLinearGauge();
            linearGauge.BackgroundColor = UIColor.White;
            linearGauge.Header = new SFLinearLabel();
            SFLinearScale linearScale = new SFLinearScale();
            linearScale.ScaleBarColor = UIColor.FromRGB(224, 224, 224);
            linearScale.LabelColor = UIColor.FromRGB(66, 66, 66);
            linearScale.MajorTickSettings.Color = UIColor.Gray;
            linearScale.MinorTickSettings.Color = UIColor.Gray;
            linearScale.MajorTickSettings.Length = 12;
            linearScale.MinorTickSettings.Length = 5;
            linearScale.MinorTicksPerInterval = 3;
            linearScale.Minimum = 20;
            linearScale.Maximum = 200;
            linearGauge.Scales.Add(linearScale);
            linearGauge.Scales.Add(linearScale);
            this.View.AddSubview(linearGauge);
  
{% endhighlight %}

![](scales_images/scale2.png)

## Setting interval for scale

The [`Interval`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale~Interval.html) property allows  you to set the intervals for scale. The default [`Interval`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale~Interval.html) property of scale is auto interval. Auto interval defines the count of the scale labels as 3 for 100 pixels.

{% highlight c# %}

             SFLinearGauge linearGauge = new SFLinearGauge();
            linearGauge.BackgroundColor = UIColor.White;
            linearGauge.Header = new SFLinearLabel();
            SFLinearScale linearScale = new SFLinearScale();
            linearScale.ScaleBarColor = UIColor.FromRGB(224, 224, 224);
            linearScale.LabelColor = UIColor.FromRGB(66, 66, 66);
            linearScale.MajorTickSettings.Color = UIColor.Gray;
            linearScale.MinorTickSettings.Color = UIColor.Gray;
            linearScale.MajorTickSettings.Length = 12;
            linearScale.MinorTickSettings.Length = 5;
            linearScale.MinorTicksPerInterval = 3;
            linearScale.Minimum = 0;
            linearScale.Maximum = 500;
            linearScale.Interval = 100;
            linearGauge.Scales.Add(linearScale);
            linearGauge.Scales.Add(linearScale);
            this.View.AddSubview(linearGauge);
  
{% endhighlight %}

![](scales_images/scale3.png)

## Setting maximum labels

The [`MaximumLabels`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale~MaximumLabels.html) property defines the count of the scale labels in the 100 pixels. By default, the maximum labels for 100 pixels is 3.

{% highlight c# %}

           SFLinearGauge linearGauge = new SFLinearGauge();
            linearGauge.BackgroundColor = UIColor.White;
            linearGauge.Header = new SFLinearLabel();
            SFLinearScale linearScale = new SFLinearScale();
            linearScale.ScaleBarColor = UIColor.FromRGB(224, 224, 224);
            linearScale.LabelColor = UIColor.FromRGB(66, 66, 66);
            linearScale.MajorTickSettings.Color = UIColor.Gray;
            linearScale.MinorTickSettings.Color = UIColor.Gray;
            linearScale.MajorTickSettings.Length = 12;
            linearScale.MinorTickSettings.Length = 5;
            linearScale.MinorTicksPerInterval = 3;
            linearScale.MinorTicksPerInterval = 1;
            linearScale.MaximumLabels = 4;
            linearGauge.Scales.Add(linearScale);
            linearGauge.Scales.Add(linearScale);
            this.View.AddSubview(linearGauge);


{% endhighlight %}

![](scales_images/scale4.png)

## Scale customization

You can customize the color, length, size, and position of the [`SFLinearScale`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale.html) by using the [`ScaleBarColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale~ScaleBarColor.html), [`ScaleBarLength`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale~ScaleBarLength.html), [`ScaleBarSize`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale~ScaleBarSize.html), and [`Offset`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale~Offset.html) properties, respectively.

{% highlight c# %}

            SFLinearGauge linearGauge = new SFLinearGauge();
            linearGauge.BackgroundColor = UIColor.White;
            linearGauge.Header = new SFLinearLabel();
            SFLinearScale linearScale = new SFLinearScale();
            linearScale.ScaleBarColor = UIColor.FromRGB(224, 224, 224);
            linearScale.LabelColor = UIColor.FromRGB(66, 66, 66);
            linearScale.MajorTickSettings.Color = UIColor.Gray;
            linearScale.MinorTickSettings.Color = UIColor.Gray;
            linearScale.MajorTickSettings.Length = 12;
            linearScale.MinorTickSettings.Length = 5;
            linearScale.MinorTicksPerInterval = 3;
            linearScale.LabelOffset = -5;
            linearScale.Offset = 10;
            linearScale.ScaleBarLength = 300;
            linearScale.ScaleBarSize = 5;
            linearGauge.Scales.Add(linearScale);
            linearGauge.Scales.Add(linearScale);
            this.View.AddSubview(linearGauge);

{% endhighlight %}

![](scales_images/scale5.png)

## Setting opposite position

To place the scale at opposite to its original position, set the [`OpposedPosition`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale~OpposedPosition.html) property to true in the scale.

{% highlight c# %}

           SFLinearGauge linearGauge = new SFLinearGauge();
            linearGauge.BackgroundColor = UIColor.White;
            linearGauge.Header = new SFLinearLabel();
            SFLinearScale linearScale = new SFLinearScale();
            linearScale.ScaleBarColor = UIColor.FromRGB(224, 224, 224);
            linearScale.LabelColor = UIColor.FromRGB(66, 66, 66);
            linearScale.MajorTickSettings.Color = UIColor.Gray;
            linearScale.MinorTickSettings.Color = UIColor.Gray;
            linearScale.MajorTickSettings.Length = 12;
            linearScale.MinorTickSettings.Length = 5;
            linearScale.MinorTicksPerInterval = 1;
            linearScale.OpposedPosition = true;
            linearGauge.Scales.Add(linearScale);
            linearGauge.Scales.Add(linearScale);
            this.View.AddSubview(linearGauge);

{% endhighlight %}

![](scales_images/scale6.png)

## Setting scale direction

You can set the scale position to its forward and backward using the [`ScalePosition`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale~ScalePosition.html) property.

{% highlight c# %}

            SFLinearGauge linearGauge = new SFLinearGauge();
            linearGauge.BackgroundColor = UIColor.White;
            linearGauge.Header = new SFLinearLabel();
            SFLinearScale linearScale = new SFLinearScale();
            linearScale.ScaleBarColor = UIColor.FromRGB(224, 224, 224);
            linearScale.LabelColor = UIColor.FromRGB(66, 66, 66);
            linearScale.MajorTickSettings.Color = UIColor.Gray;
            linearScale.MinorTickSettings.Color = UIColor.Gray;
            linearScale.MajorTickSettings.Length = 12;
            linearScale.MinorTickSettings.Length = 5;
            linearScale.MinorTicksPerInterval = 1;
            linearScale.ScalePosition = SFLinearGaugeScalePosition.SFLinearGaugeScalePositionBackward;
            linearGauge.Scales.Add(linearScale);
            linearGauge.Scales.Add(linearScale);
            this.View.AddSubview(linearGauge);
	
{% endhighlight %}

![](scales_images/scale7.png)

## Setting corner radius type for scale

Corners of the [`SFLinearScale`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale.html) can be customized by setting the value to the [`CornerRadiusType`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale~CornerRadiusType.html) property. All corners of linear scale can be customized using the `Start`, `End`, `Both`, and `None` options.
 [`CornerRadius`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale~CornerRadius.html) property used to reduce the radius of the corners.

{% highlight c# %}

           SFLinearGauge linearGauge = new SFLinearGauge();
            linearGauge.BackgroundColor = UIColor.White;
            linearGauge.Header = new SFLinearLabel();
            SFLinearScale linearScale = new SFLinearScale();
            linearScale.ScaleBarColor = UIColor.FromRGB(224, 224, 224);
            linearScale.LabelColor = UIColor.FromRGB(66, 66, 66);
            linearScale.MajorTickSettings.Color = UIColor.Gray;
            linearScale.MinorTickSettings.Color = UIColor.Gray;
            linearScale.MajorTickSettings.Length = 12;
            linearScale.MinorTickSettings.Length = 5;
            linearScale.CornerRadiusType = CornerRadiusType.Start;
            linearScale.CornerRadius = 10;
            linearGauge.Scales.Add(linearScale);
            linearGauge.Scales.Add(linearScale);
            this.View.AddSubview(linearGauge);
	
{% endhighlight %}

![](scales_images/scale8.png)

## Multiple scales 

It helps you to add multiple scales to the same linear gauge and customize all the scales in a [`Scales`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearGauge~Scales.html) collection.

{% highlight c# %}

            SFLinearGauge linearGauge = new SFLinearGauge();
            linearGauge.Orientation = SFLinearGaugeOrientation.SFLinearGaugeOrientationVertical;
            linearGauge.BackgroundColor = UIColor.White;
            SFLinearScale linearScale = new SFLinearScale();
            linearScale.ScaleBarLength = 500;
            linearScale.Minimum = 0;
            linearScale.Interval = 10;
            linearScale.Maximum = 100;
            linearScale.Offset = 9;
            linearScale.ScaleBarColor = UIColor.Gray;
            linearScale.ScaleBarSize = 5;
            linearScale.MajorTickSettings.Color = UIColor.Gray;
            linearScale.MinorTickSettings.Color = UIColor.Gray;
            linearScale.MajorTickSettings.Thickness = 1;
            linearScale.LabelColor = UIColor.Gray;
            linearScale.MinorTicksPerInterval = 1;
            linearScale.LabelPostfix =(Foundation.NSString) "°F";
            linearScale.LabelOffset = -6;
            linearScale.ScalePosition = SFLinearGaugeScalePosition.SFLinearGaugeScalePositionBackward;
            linearGauge.Scales.Add(linearScale);

            SFLinearScale scale = new SFLinearScale();
            scale.Minimum = 0;
            scale.ScaleBarLength = 500;
            scale.Interval = 10;
            scale.Maximum = 100;
            scale.ShowTicks = false;
            scale.ShowScaleLabel = false;
            scale.ScaleBarSize = 5;
            scale.ScaleBarColor = UIColor.FromRGB(255,255,255);
            scale.CornerRadiusType = CornerRadiusType.Both;
            scale.MajorTickSettings.Color = UIColor.Black;
            scale.MinorTickSettings.Color = UIColor.Black;
            scale.LabelColor = UIColor.Black;
            scale.ScalePosition = SFLinearGaugeScalePosition.SFLinearGaugeScalePositionBackward;
            SFBarPointer barPointer = new SFBarPointer();
            barPointer.Value = 45;
            barPointer.Thickness = 7;
            barPointer.CornerRadiusType = CornerRadiusType.End;
            barPointer.CornerRadius = 3;
            barPointer.Color = UIColor.FromRGB(249, 92, 133);
            scale.Pointers.Add(barPointer);
            linearGauge.Scales.Add(scale);

            SFLinearScale linearScale1 = new SFLinearScale();
            linearScale1.Minimum = 0;
            linearScale1.ScaleBarLength = 500;
            linearScale1.MinorTicksPerInterval = 1;
            linearScale1.Maximum = 38;
            linearScale1.Interval = 2;
            linearScale1.ScaleBarColor = UIColor.Gray;
            linearScale1.ScaleBarSize = 5;
            linearScale1.MajorTickSettings.Color = UIColor.Gray;
            linearScale1.MinorTickSettings.Color = UIColor.Gray;
            linearScale1.LabelColor = UIColor.Gray;
            linearScale1.OpposedPosition = true;
            linearScale1.Offset = -9;
            linearScale1.MajorTickSettings.Thickness = 1;
            linearScale1.LabelOffset = -5;
            linearScale1.ScalePosition = SFLinearGaugeScalePosition.SFLinearGaugeScalePositionBackward;
            linearScale1.LabelPostfix = (Foundation.NSString)"°C";

            linearGauge.Scales.Add(linearScale1);
            this.View.AddSubview(linearGauge);
	
{% endhighlight %}

![](scales_images/scale9.png)

## Setting gradient color for scale

You can give smooth color transition to scale to specifying the different colors based on scale value by using [`GradientStops`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearScale~GradientStops.html) property.

{% highlight c# %}

            SFLinearGauge linearGauge = new SFLinearGauge();
            linearGauge.BackgroundColor = UIColor.White;
            linearGauge.Header = new SFLinearLabel();

            SFLinearScale linearScale = new SFLinearScale();

            GaugeGradientStop gaugeGradientStop = new GaugeGradientStop();
            gaugeGradientStop.Value = 10;
            gaugeGradientStop.Color = UIColor.FromRGB(81, 201, 225);
            linearScale.GradientStops.Add(gaugeGradientStop);

            GaugeGradientStop gaugeGradientStop1 = new GaugeGradientStop();
            gaugeGradientStop1.Value = 40;
            gaugeGradientStop1.Color = UIColor.FromRGB(147, 233, 225);
            linearScale.GradientStops.Add(gaugeGradientStop1);

            GaugeGradientStop gaugeGradientStop2 = new GaugeGradientStop();
            gaugeGradientStop2.Value = 50;
            gaugeGradientStop2.Color = UIColor.FromRGB(197, 230, 146);
            linearScale.GradientStops.Add(gaugeGradientStop2);

            GaugeGradientStop gaugeGradientStop3 = new GaugeGradientStop();
            gaugeGradientStop3.Value = 60;
            gaugeGradientStop3.Color = UIColor.FromRGB(254, 221, 43);
            linearScale.GradientStops.Add(gaugeGradientStop3);

            GaugeGradientStop gaugeGradientStop4 = new GaugeGradientStop();
            gaugeGradientStop4.Value = 100;
            gaugeGradientStop4.Color = UIColor.FromRGB(232, 120, 19);
            linearScale.GradientStops.Add(gaugeGradientStop4);

            linearScale.ScaleBarSize = 15;
            linearScale.MajorTickSettings.Color = UIColor.Black;
            linearScale.MinorTickSettings.Color = UIColor.Black;
            linearScale.MajorTickSettings.Length = 12;
            linearScale.MinorTickSettings.Length = 5;
            linearScale.MinorTicksPerInterval = 1;
            linearScale.LabelColor = UIColor.Black;
            linearGauge.Scales.Add(linearScale);
            this.View.AddSubview(linearGauge);
	
{% endhighlight %}

![](scales_images/scale10.png)
