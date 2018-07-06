---
layout: post
title: Appearance
platform: xamarin.ios
control: ProgressBar
documentation: ug
---
# Appearance

## Angle

The appearance of the circular progress bar can be customized to semi-circle, arc, etc. The start and end angles can be customized using the [`StartAngle`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.SfCircularProgressBar~StartAngle.html) and [`EndAngle`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.SfCircularProgressBar~EndAngle.html) properties. 

The following code example explains how to change the appearance of the circular progress bar to semi-circle.

{% highlight c# %}

SfCircularProgressBar circularProgressBar = new SfCircularProgressBar();

circularProgressBar.Progress = 75;

circularProgressBar.StartAngle = 180;

circularProgressBar.EndAngle = 360;

circularProgressBar.Frame = new CoreGraphics.CGRect(0, 160, this.View.Frame.Width, this.View.Frame.Height);

{% endhighlight %} 

![](overview_images/angle.png)


## Range colors

You can also visualize multiple ranges with different colors that are mapped to each range to enhance readability of progress.Currently, it is applicable only for linear progress bar.

The colors can be mapped to the specific ranges using the [`RangeColors`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.SfLinearProgressBar~RangeColors.html) property in the linear progress bar, which holds a collection of [`RangeColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.RangeColor.html). 

The following properties in [`RangeColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.RangeColor.html) are used to map the colors to range:

* [`Color`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.RangeColor~Color.html): Represents the color to the specified range.
* [`Start`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.RangeColor~Start.html): Represents the start range of the color.
* [`End`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.RangeColor~End.html): Represents the end range of the color.
* [`IsGradient`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.RangeColor~IsGradient.html): Represents whether the gradient effect is applied to the color.

The following code example shows mapping the solid color range in the linear progress bar.

{% highlight c# %}

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();

linearProgressBar.Progress = 100;

linearProgressBar.RangeColors.Add(new RangeColor() { Color = Color.ParseColor("#00bdaf"), Start = 0, End = 25 });

linearProgressBar.RangeColors.Add(new RangeColor() { Color = Color.ParseColor("#2f7ecc"), Start = 25, End = 50 });

linearProgressBar.RangeColors.Add(new RangeColor() { Color = Color.ParseColor("#e9648e"), Start = 50, End = 75 });

linearProgressBar.RangeColors.Add(new RangeColor() { Color = Color.ParseColor ("#fbb78a"), Start = 75, End = 100 });

{% endhighlight %} 

![](overview_images/rangecolors.png)

The following code example shows how to apply gradient transition effect to the range colors in the linear progress bar.

{% highlight c# %}

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();

linearProgressBar.Progress = 100;

linearProgressBar.RangeColors.Add(

new RangeColor() { Color = Color.ParseColor("#88A0D9EF"), IsGradient = true, Start = 0 , End = 25 });

linearProgressBar.RangeColors.Add(

new RangeColor() { Color = Color.ParseColor("#AA62C1E5"), IsGradient = true, Start = 25, End = 50 });

linearProgressBar.RangeColors.Add(

new RangeColor() { Color = Color.ParseColor("#DD20A7DB"), IsGradient = true, Start = 50, End = 75 });

linearProgressBar.RangeColors.Add(

new RangeColor() { Color = Color.ParseColor("#FF1C96C5"), IsGradient = true, Start = 75, End = 100 });

{% endhighlight %} 

![](overview_images/gradient.png)

## Thickness

**Linear** **progress** **bar**

In the linear progress bar, the height of the track and padding of the progress indicator can be customized using the [`TrackHeight`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.SfLinearProgressBar~TrackHeight.html) and [`IndicatorPadding`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.SfLinearProgressBar~IndicatorPadding.html) properties, respectively.

{% highlight c# %}

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();

linearProgressBar.Progress = 100;

linearProgressBar.TrackHeight = 10;

linearProgressBar.Padding = new UIEdgeInsets(0,2,0,0);

linearProgressBar.Frame = new CoreGraphics.CGRect(0, 160, this.View.Frame.Width, this.View.Frame.Height);

{% endhighlight %}

![](overview_images/thickness_linear.png)


**Circular** **progress** **bar**

The following properties are used to customize the appearance of the circular progress bar:

* [`IndicatorOuterRadius`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.SfCircularProgressBar~IndicatorOuterRadius.html): Defines the outer radius of the progress indicator.
* [`IndicatorInnerRadius`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.SfCircularProgressBar~IndicatorInnerRadius.html): Defines the inner radius of the progress indicator.
* [`TrackOuterRadius`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.SfCircularProgressBar~TrackOuterRadius.html): Defines the outer radius of the track indicator.
* [`TrackInnerRadius`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.SfCircularProgressBar~TrackInnerRadius.html): Defines the inner radius of the track indicator.

The following code example shows how to customize the appearance of circular progress bar.

{% highlight c# %}

SfCircularProgressBar trackOutsideProgressBar = new SfCircularProgressBar(this);

trackOutsideProgressBar.Progress = 75;

trackOutsideProgressBar.IndicatorOuterRadius = 0.7;

trackOutsideProgressBar.IndicatorInnerRadius = 0.65;

trackOutsideProgressBar.ShowProgressValue = false;

{% endhighlight %} 

![](overview_images/appearance.png)


## Corner radius

The [`CornerRadius`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.SfLinearProgressBar~CornerRadius.html) property is used to customize the rounded edges in the linear progress bar, as shown in the following code example.

{% highlight c# %}

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar(this);

linearProgressBar.Progress = 50;

linearProgressBar.CornerRadius = 10;

{% endhighlight %} 

![](overview_images/cornerradius.png)


## Color customization

The following properties are used to customize the color in the progress bar:

* [`ProgressColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.ProgressBarBase~ProgressColor.html): Represents the color of the progress indicator.
* [`TrackColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.ProgressBarBase~TrackColor.html): Represents the color of the track indicator.

The following code example shows the color customization in progress and track indicator.

{% highlight c# %}

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar(this);

linearProgressBar.Progress = 75;

linearProgressBar.ProgressColor = Color.ParseColor("#FF51483a");

linearProgressBar.TrackColor = Color.ParseColor("#3351483a");

{% endhighlight %} 

![](overview_images/color1.png)

The linear progress bar provides support to customize the color for the secondary progress bar using the [`SecondaryProgressColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.SfLinearProgressBar~SecondaryProgressColor.html) property,as shown in the following code example.

{% highlight c# %}
SfLinearProgressBar linearProgressBar = new SfLinearProgressBar(this);

linearProgressBar.Progress = 25;

linearProgressBar.SecondaryProgress = 75;

linearProgressBar.SecondaryProgressColor = Color.CornflowerBlue;

{% endhighlight %} 

![](overview_images/color2.png)


