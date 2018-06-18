---

layout: post
title: Getting Started | SfCircularGauge | iOS | Syncfusion
description: Labels
platform: xamarin.iOS
control: SfCircularGauge
documentation: ug

---

# Labels

The [`SFCircularScale`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularScale.html) labels associate a numeric value with major scale tick marks.

## Label color customization

The label color can be changed using the [`LabelColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularScale~LabelColor.html) property.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.LabelColor = UIColor.Blue;
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);
    
{% endhighlight %}

![](labels_images/label-color-customization.png)

## Label font customization

The label font can be customized by using the [`LabelFont`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularScale~LabelFont.html) property.
{% highlight c# %}

           SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.LabelFont = UIFont.FromName("Chalkduster", 20f);
            scales.Add(scale);
            circularGauge.Scales = scales; 
            this.View.AddSubview(circularGauge);
    
{% endhighlight %}

![](labels_images/label-font-customization.png)

## Setting position for labels

The labels can be positioned far away from the ticks by using the [`LabelOffset`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularScale~LabelOffset.html) property.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.LabelOffset = 0.4f;
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);
    
{% endhighlight %}

![](labels_images/label-offset.png)

## Setting number of decimal digits for labels

The [`NumberOfDecimalDigits`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularScale~NumberOfDecimalDigits.html) property is used to set the number of decimal digits to be displayed in the scale labels.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.NumberOfDecimalDigits = 3;
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);
    
{% endhighlight %}

![](labels_images/number-of-decimal-digits.png)

## Setting postfix and prefix for labels

You can postfix/prefix values to the scale labels by using the [`LabelPostfix`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularScale~LabelPostfix.html) and [`LabelPrefix`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularScale~LabelPrefix.html) properties, respectively.

### Label postfix

[`LabelPostfix`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularScale~LabelPostfix.html) property allows you to postfix the values to the scale labels.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.LabelPostfix = "$";
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);
    
{% endhighlight %}

![](labels_images/label-postfix.png)

### Label prefix

[`LabelPrefix`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularScale~LabelPrefix.html) property allows you to prefix the values to the scale labels.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.LabelPrefix = "$";
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);
    
{% endhighlight %}

![](labels_images/label-prefix.png)

## Edge label customization

You can customize the edge label by using the [`ShowFirstLabel`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularScale~ShowFirstLabel.html) and [`ShowLastLabel`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularScale~ShowLastLabel.html) properties, which are Boolean properties. The [`ShowFirstLabel`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularScale~ShowFirstLabel.html) property is used to enable or disable first label, and the [`ShowLastLabel`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularScale~ShowLastLabel.html) property is used to enable or disable the last label in circular gauge.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.Interval = 1;
            scale.MinorTicksPerInterval = 5;
            scale.EndValue = 12;
            scale.StartAngle = -180;
            scale.SweepAngle = 180;
            scale.ShowFirstLabel = false;
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);
    
{% endhighlight %}

![](labels_images/label-edge-customization.png)

## Show labels

The [`ShowLabels`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularScale~ShowLabels.html) property is a Boolean property, which is used to enable or disable the labels in circular gauge.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.ShowLabels = false;
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);
    
{% endhighlight %}

![](labels_images/show-labels.png)

## Setting auto angle for label

Scale labels can be rotated automatically based on the current angle. To enable or disable the auto angle, use the [`EnableAutoAngle`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularScale~EnableAutoAngle.html) property.

{% highlight c# %}

            SfCircularGauge circularGauge = new SfCircularGauge(this);
            ObservableCollection<CircularScale> scales = new ObservableCollection<CircularScale>();
            CircularScale scale = new CircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.EnableAutoAngle = true;
            scales.Add(scale);
            circularGauge.CircularScales = scales;  
    
{% endhighlight %}

![](labels_images/auto-angle.png)

