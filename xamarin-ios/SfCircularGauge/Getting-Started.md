---

layout: post
title: Getting Started | SfCircularGauge | iOS | Syncfusion
description: getting started
platform: xamarin.iOS
control: SfCircularGauge
documentation: ug

---


# Getting Started

This section explains the steps required to configure the [`SFCircularGauge`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularGauge.html), and also explains the steps required to add basic elements to [`SFCircularGauge`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularGauge.html) through various APIs available within it.


## Create your first Circular Gauge in Xamarin.iOS

Essential Gauge for Xamarin.iOS allows you to visualize numeric values over a circular scale. The appearance of the gauge can be fully customized to seamlessly integrate with your applications.
This section provides a quick overview for working with Essential Gauge for Xamarin.iOS. It walks through the entire process of creating a real world gauge.

CircularGauge
{:.caption}

### Reference Essential Studio Components in your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:
{Syncfusion Installed location}\Essential Studio{version number}\lib

You have to add the following assembly reference to the iOS unified project
ios-unified \ Syncfusion.SfGauge.iOS.dll

N> Assemblies are available in unzipped package location in Mac. 

### Adding namespace for the assemblies

{% highlight c# %}

    using Syncfusion.SfGauge.iOS;

{% endhighlight %}


## Initialize gauge 

You can initialize the [`SFCircularGauge`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularGauge.html) control with a required optimal name by using the included namespace.

{% highlight c# %}

                public override void ViewDidLoad()
		{
			base.ViewDidLoad();
                        SFCircularGauge circularGauge = new SFCircularGauge();
                        this.View.AddSubview(circularGauge);
		}

{% endhighlight %}

## Adding header

You can assign a unique header to [`SFCircularGauge`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularGauge.html) by using the [`SFGaugeHeader`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFGaugeHeader.html) property and position it by using the [`Position`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFGaugeHeader~Position.html) property as you want.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            SFGaugeHeader header = new SFGaugeHeader();
            header.Text = (Foundation.NSString) "Speedometer";
            header.TextColor = UIColor.Black;
            circularGauge.Headers.Add(header);
            this.View.AddSubview(circularGauge);
	
{% endhighlight %}

## Configuring scales

You can configure the [`SFCircularScale`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularScale.html) elements by using following APIs, which are available in [`SFCircularGauge`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularGauge.html):

* `StartAngle`
* `SweepAngle`
* `StartValue`
* `EndValue`
* `Interval`
* `RimThickness`
* `RimColor`

{% highlight c# %}

            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scales.Add(scale);
            circularGauge.Scales = scales;
	
{% endhighlight %}

## Adding ranges

You can add ranges to [`SFCircularGauge`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularGauge.html) by creating ranges collection using the [`SFCircularRange`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularRange.html) property.

{% highlight c# %}

           ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scales.Add(scale);
            circularGauge.Scales = scales;
            SFCircularRange range = new SFCircularRange();
            range.StartValue = 0;
            range.EndValue = 40;
            scale.Ranges.Add(range);
	
{% endhighlight %}

## Adding a needle pointer

Create a [`SFNeedlePointer`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFNeedlePointer.html), and associate it with a scale that is to be displayed the current value.

{% highlight c# %}

           ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scales.Add(scale);
            circularGauge.Scales = scales;
            SFNeedlePointer needlePointer = new SFNeedlePointer();
            needlePointer.Value = 60;
            scale.Pointers.Add(needlePointer);
	
{% endhighlight %}

## Adding a range pointer

[`SFRangePointer`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFRangePointer.html) provides an alternative way to indicate the current value.

{% highlight c# %}    

           ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scales.Add(scale);
            circularGauge.Scales = scales;
            SFRangePointer rangePointer = new SFRangePointer();
            rangePointer.Value = 60;
            scale.Pointers.Add(rangePointer);
	
{% endhighlight %}

## Adding a marker pointer

[`SFMarkerPointer`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFMarkerPointer.html) points the current value in scale.

{% highlight c# %}  
   
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scales.Add(scale);
            circularGauge.Scales = scales;
            SFMarkerPointer markerPointer = new SFMarkerPointer();
            markerPointer.Value = 70;
            scale.Pointers.Add(markerPointer);
	
{% endhighlight %}
 
![](getting-started_images/default.png)