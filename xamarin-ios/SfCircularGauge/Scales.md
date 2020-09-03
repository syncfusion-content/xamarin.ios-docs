---

layout: post
title: Getting Started | SfCircularGauge | iOS | Syncfusion
description: Scales
platform: xamarin.iOS
control: SfCircularGauge
documentation: ug

---

# Scales

CircularScales contain a collection of [`SFCircularScale`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html) elements, which integrates labels, tick marks, and a rim to customize the basic look and feel of the circular gauge.

## Scale

[`SFCircularScale`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html) contains the sub elements such as rim, ticks, labels, ranges, and pointers. It defines the radius, start angle, sweep direction, sweep angle, overall minimum and maximum values, frequency of labels, and tick marks. It will have multiple ranges.

A range is a visual element, which begins and ends at specified values within a [`SFCircularScale`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html). It will have one or more pointers to point out the values in scale.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](scales_images/scale.png)

## Setting start and end values for scale

The [`StartValue`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_StartValue) and [`EndValue`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_EndValue) properties allow  you to set the start and end values for scale.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = -30;
            scale.EndValue = 50;
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](scales_images/start-end-value.png)

## Setting start and sweep angles for scale

The [`StartAngle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_StartAngle) and [`SweepAngle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_SweepAngle) properties allow you to set the start and end angles for scale.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.StartAngle = 125;
            scale.SweepAngle = 350;
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](scales_images/start-end-angle.png)

## Setting interval for scale

The [`Interval`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_Interval) property allows you to set the interval for scale.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 500;
            scale.Interval = 100;
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](scales_images/interval.png)

## Setting auto interval for scale

By default, the interval value is calculated by 10. By using the [`EnableAutoInterval`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_EnableAutoInterval) property, you can set auto interval based on the start and end values.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 500;
            scale.EnableAutoInterval = true;
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](scales_images/auto-interval.png)

## Setting scale direction for scale

The [`Direction`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_Direction) property allows you to render the gauge scale in either clockwise or counterclockwise direction.

{% highlight c# %}

           SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.Direction = SFCircularScaleDirection.AntiClockwise;
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](scales_images/scale-direction.png)

## Setting multiple scales for scale

It helps you to add multiple scales to the same circular gauge. You can customize all the scales in a [`Scales`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularGauge.html#Syncfusion_SfGauge_iOS_SFCircularGauge_Scales) collection.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 240;
            scale.Interval = 20;
            scale.MinorTicksPerInterval = 1;
            scale.RimColor = UIColor.FromRGB(198, 46, 10);
            scale.LabelOffset = 0.88f;
            scale.LabelColor = UIColor.FromRGB(198, 46, 10);
            scale.ScaleStartOffset = 0.7f;
            scale.ScaleEndOffSet = 0.69f;

            SFTickSettings majorTicks = new SFTickSettings();
            majorTicks.StartOffset = 0.7f;
            majorTicks.EndOffset = 0.77f;
            majorTicks.Width = 2;
            majorTicks.Color = UIColor.FromRGB(198, 46, 10);
            scale.MajorTickSettings = majorTicks;

            SFTickSettings minorTicks = new SFTickSettings();
            minorTicks.StartOffset = 0.7f;
            minorTicks.EndOffset = 0.75f;
            minorTicks.Width = 2;
            minorTicks.Color = UIColor.FromRGB(198, 46, 10);
            scale.MinorTickSettings = minorTicks;
            scales.Add(scale);

            SFCircularScale circularScale = new SFCircularScale();
            circularScale.StartValue = 0;
            circularScale.EndValue = 160;
            circularScale.Interval = 40;
            circularScale.MinorTicksPerInterval = 1;
            circularScale.RimColor = UIColor.FromRGB(51, 51, 51);
            circularScale.LabelOffset = 0.45f;
            circularScale.LabelColor = UIColor.FromRGB(51, 51, 51);
            circularScale.ScaleStartOffset = 0.65f;
            circularScale.ScaleEndOffSet = 0.64f;

            SFTickSettings majorTick = new SFTickSettings();
            majorTick.StartOffset = 0.64f;
            majorTick.EndOffset = 0.57f;
            majorTick.Width = 2;
            majorTick.Color = UIColor.FromRGB(51, 51, 51);
            circularScale.MajorTickSettings = majorTick;

            SFTickSettings minorTick = new SFTickSettings();
            minorTick.StartOffset = 0.64f;
            minorTick.EndOffset = 0.59f;
            minorTick.Width = 2;
            minorTick.Color = UIColor.FromRGB(51, 51, 51);
            circularScale.MinorTickSettings = minorTick;

            scales.Add(circularScale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

	
{% endhighlight %}

![](scales_images/multiple-scale.png)
