---
layout: post
title: Range
platform:  xamarin.ios
control: ProgressBar
documentation: ug
---

# Defining range

Range represents the entire span of the progress bar, and it can be defined using the [`Minimum`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.ProgressBar.ProgressBarBase.html#Syncfusion_iOS_ProgressBar_ProgressBarBase_Minimum) and [`Maximum`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.ProgressBar.ProgressBarBase.html#Syncfusion_iOS_ProgressBar_ProgressBarBase_Maximum) properties. The default value of range is 0 to 100.

The following code example explains how to customize the range as factor value to the progress bar.

{% highlight c# %}

// Using linear progress bar.

SfLinearProgressBar sfLinearProgressBar = new SfLinearProgressBar();            

sfLinearProgressBar.Minimum = 0;

sfLinearProgressBar.Maximum = 1;

sfLinearProgressBar.Frame = new CoreGraphics.CGRect(10,150,this.View.Frame.Width,this.View.Frame.Height);  

sfLinearProgressBar.Progress = 0.5;

// Using circular progress bar.

SfCircularProgressBar circularProgressBar = new SfCircularProgressBar();

circularProgressBar.Frame = new CoreGraphics.CGRect(0, 160, this.View.Frame.Width, this.View.Frame.Height);

circularProgressBar.Minimum = 0;

circularProgressBar.Maximum = 1;

circularProgressBar.Progress = 0.5;

{% endhighlight %} 

![](overview_images/range.png)
