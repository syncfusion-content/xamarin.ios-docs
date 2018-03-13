---

layout: post
title: Accessing Header in LinearGauge
description:  Learn how to set header in LinearGauge
platform: Xamarin.iOS
control: LinearGauge
documentation: ug

---

# Header

You can add a title to gauge using the [`SFLinearLabel`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearLabel.html) option to provide information to users about the data that is being plotted in the linear gauge.

## Adding header to linear gauge

{% highlight c# %}

            SFLinearGauge linearGauge = new SFLinearGauge();
            linearGauge.BackgroundColor = UIColor.White;
            SFLinearLabel linearHeader = new SFLinearLabel();
            linearHeader.Text = (Foundation.NSString)"Thermometer";
           linearHeader.Font = UIFont.FromName("Helvetica", 15f);
            linearHeader.Position = new CoreGraphics.CGPoint(0.4, 0.1);
            linearHeader.Color = UIColor.Black;
            linearGauge.Header = linearHeader;

            linearGauge.Orientation = SFLinearGaugeOrientation.SFLinearGaugeOrientationVertical;

            SFLinearScale linearScale = new SFLinearScale();
            linearScale.Interval = 10;
            linearScale.ScaleBarColor = UIColor.FromRGB(224, 224, 224);
            linearScale.MajorTickSettings.Length = 12;
            linearScale.MinorTickSettings.Length = 5;
            linearScale.ScaleBarLength = 350;
            linearScale.LabelColor = UIColor.FromRGB(66, 66, 66);
            linearGauge.Scales.Add(linearScale);
            this.View.AddSubview(linearGauge);

{% endhighlight %}

![](header_images/header.png)

##  Positioning the header

To change the position of header, use the [`Position`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearLabel~Position.html)  property in the linear header. It ranges from 0 to 1. By default, the header will be positioned on the top of linear gauge.

{% highlight c# %}

            SFLinearGauge linearGauge = new SFLinearGauge();
            linearGauge.BackgroundColor = UIColor.White;
            SFLinearLabel linearHeader = new SFLinearLabel();
            linearHeader.Text = (Foundation.NSString)"Thermometer";
            linearHeader.Font = UIFont.FromName("Helvetica", 15f);
            linearHeader.Position = new CoreGraphics.CGPoint(0.4, 0.4);
            linearHeader.Color = UIColor.Black;
            linearGauge.Header = linearHeader;

            SFLinearScale linearScale = new SFLinearScale();
            linearScale.Interval = 10;
            linearScale.ScaleBarColor = UIColor.FromRGB(224, 224, 224);
            linearScale.MajorTickSettings.Length = 12;
            linearScale.MinorTickSettings.Length = 5;
            linearScale.ScaleBarLength = 350;
            linearScale.LabelColor = UIColor.FromRGB(66, 66, 66);
            linearGauge.Scales.Add(linearScale);
            this.View.AddSubview(linearGauge);
    
{% endhighlight %}

![](header_images/header2.png)

##  Customizing header text

You can customize the text of [`SFLinearLabel`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearLabel.html) by using the [`Color`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearLabel~Color.html) and [`Font`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFLinearLabel~Font.html) properties as shown in the following code snippet.

{% highlight c# %}

           SFLinearGauge linearGauge = new SFLinearGauge();
            linearGauge.BackgroundColor = UIColor.White;
            SFLinearLabel linearHeader = new SFLinearLabel();
            linearHeader.Text = (Foundation.NSString)"Thermometer";
            linearHeader.Font = UIFont.FromName("Chalkduster", 18f);
            linearHeader.Position = new CoreGraphics.CGPoint(0.35, 0.4);
            linearHeader.Color = UIColor.FromRGB(0 , 255 , 255);
            linearGauge.Header = linearHeader;

            SFLinearScale linearScale = new SFLinearScale();
            linearScale.Interval = 10;
            linearScale.ScaleBarColor = UIColor.FromRGB(224, 224, 224);
            linearScale.MajorTickSettings.Length = 12;
            linearScale.MinorTickSettings.Length = 5;
            linearScale.ScaleBarLength = 350;
            linearScale.LabelColor = UIColor.FromRGB(66, 66, 66);
            linearGauge.Scales.Add(linearScale);
            this.View.AddSubview(linearGauge);
 
{% endhighlight %}

![](header_images/header3.png)
