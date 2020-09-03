---

layout: post
title: Getting Started | SfCircularGauge | iOS | Syncfusion
description: Header
platform: xamarin.iOS
control: SfCircularGauge
documentation: ug

---

# Header

The [`SFGaugeHeader`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFGaugeHeader.html) support allows you to show text, image, or any UI content inside the gauge control. A circular gauge can be made self-descriptive about the data. It can be  measured with use of the header.

## Adding header in circular gauge

###  Header

The [`SFGaugeHeader`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFGaugeHeader.html) can be used to set a unique header for the circular gauge. You can add text as headers in a circular gauge. Multiple headers also can be added in a circular gauge.

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            SFGaugeHeader header = new SFGaugeHeader();
            header.Text = (Foundation.NSString)"Speedometer";
            header.TextColor = UIColor.Black;
            circularGauge.Headers.Add(header);
            scale.StartValue = 0;
            scale.EndValue = 100;
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);

{% endhighlight %}

![](header_images/header.png)

##  Setting position for header

The [`Position`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFGaugeHeader.html#Syncfusion_SfGauge_iOS_SFGaugeHeader_Position) property is used to place the header in a circular gauge. The value for [`Position`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFGaugeHeader.html#Syncfusion_SfGauge_iOS_SFGaugeHeader_Position) should be specified in offset value. In the Point value, which has been given for the `Position`, first value represent x-coordinate and second value represents y-coordinate. By default, it is placed at (0.5, 0.7).

{% highlight c# %}

            SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            SFGaugeHeader header = new SFGaugeHeader();
            header.Text =(Foundation.NSString) "Speedometer";
            header.TextColor = UIColor.Black;
            header.Position = new CoreGraphics.CGPoint((float)0.5, (float)0.5);
            circularGauge.Headers.Add(header);
            scale.StartValue = 0;
            scale.EndValue = 100;
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);
    
{% endhighlight %}

![](header_images/header-position.png)

##  Customization of header

You can customize the header's text by using the [`TextStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFGaugeHeader.html#Syncfusion_SfGauge_iOS_SFGaugeHeader_TextStyle), [`TextColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFGaugeHeader.html#Syncfusion_SfGauge_iOS_SFGaugeHeader_TextColor) and [`ArcRadius`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfGauge.iOS.SFGaugeHeader.html#Syncfusion_SfGauge_iOS_SFGaugeHeader_ArcRadius) properties.

{% highlight c# %}

             SFCircularGauge circularGauge = new SFCircularGauge();
            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            SFGaugeHeader header = new SFGaugeHeader();
            header.Text = (Foundation.NSString)"Speedometer";
            header.TextStyle = UIFont.FromName("Chalkduster", 20f);
            header.TextColor = UIColor.Blue;
            circularGauge.Headers.Add(header);
            scale.StartValue = 0;
            scale.EndValue = 100;
            scales.Add(scale);
            circularGauge.Scales = scales;
            this.View.AddSubview(circularGauge);
    
{% endhighlight %}

![](header_images/header-customise.png)
