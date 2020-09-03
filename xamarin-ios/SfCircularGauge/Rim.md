---

layout: post
title: Getting Started | SfCircularGauge | iOS | Syncfusion
description: Rim
platform: xamarin.iOS
control: SfCircularGauge
documentation: ug

---

# Rim

Scale determines the structure of a circular gauge by using the circular rim. By setting the [`StartAngle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_StartAngle) and [`SweepAngle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_SweepAngle) properties, you can change the shape of the circular gauge into a full circular gauge, half circular gauge, or quarter circular gauge.

The [`StartValue`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_StartValue) and [`EndValue`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_EndValue) properties will determine the overall range of the circular rim.

{% highlight c# %}

           SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartAngle = -180;
            scale.SweepAngle = 180;
            scale.StartValue = 0;
            scale.EndValue = 360;
            scale.Interval = 20;
            scale.MinorTicksPerInterval = 0;
            scale.ShowFirstLabel = false;
            circularGauge.Scales.Add(scale);
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](rim_images/rim.png)

## Rim customization

The color and thickness of rim can be set by using the [`RimColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_RimColor) and [`RimWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_RimWidth) properties. To increase the [`RimWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_RimWidth), set the [`RadiusFactor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_RadiusFactor).

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.RadiusFactor = 1;
            scale.RimWidth = 40;
            scale.LabelOffset = 0.6f;
            scale.MajorTickSettings.Offset = 0.8f;
            scale.MinorTickSettings.Offset = 0.8f;
            scale.RimColor = UIColor.FromRGB(135,206,250);
            circularGauge.Scales.Add(scale); 
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](rim_images/rim-customization.png)

## Setting position for rim

You can customize the position of [`Scales`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularGauge.html#Syncfusion_SfGauge_iOS_SFCircularGauge_Scales) in the following two ways:
1. [`RadiusFactor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_RadiusFactor) with the [`RimWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_RimWidth) property.
2. The [`ScaleStartOffset`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_ScaleStartOffset) and [`ScaleEndOffset`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_ScaleEndOffSet) properties.

### Setting radius factor for rim

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.RadiusFactor = 0.7f;
            scale.RimWidth = 30;
            circularGauge.Scales.Add(scale); 
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](rim_images/rim-offset.png)

### Setting scale start and end offsets for rim

{% highlight c# %}

             SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.ScaleStartOffset = 0.6f;
            scale.ScaleEndOffSet = 0.7f;
            circularGauge.Scales.Add(scale); 
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](rim_images/rim-start-end-offset.png)

## Show rim

The [`ShowRim`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFCircularScale.html#Syncfusion_SfGauge_iOS_SFCircularScale_ShowRim) property is a Boolean property, which is used to enable or disable the rim in circular gauge.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.ShowRim = false;
            circularGauge.Scales.Add(scale); 
            this.View.AddSubview(circularGauge);
    
{% endhighlight %}

![](rim_images/show-rim.png)


