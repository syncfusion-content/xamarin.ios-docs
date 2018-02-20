---
layout: post
title: Chart Appearance | SFChart | Xamarin.iOS | Syncfusion
description: How to customize the chart appearance
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Color Palette

## Apply palette for Chart

[`ColorModel`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.ChartBase~ColorModel.html) property of [`SFChart`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChart.html) is used to define the colors for each series. [`ColorModel`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.ChartBase~ColorModel.html) contains the following color palettes.

**Predefined Palettes**

Currently, Chart supports three different palettes. They are 

* Metro
* TomatoSpectrum
* Pineapple

Metro is the default palette for [`SFChart`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChart.html). 

The following screenshot shows the default appearance of multiple series.

![](appearance_images/appearance_img1.png)

**Custom Palette**

Chart will use the colors from [`CustomColors`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartColorModel~CustomColors.html) property if [`ColorModel.Palette`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartColorModel~Palette.html) is set to [`SFChartColorPalette.Custom`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartColorPalette.html).

Following code illustrates how to set the custom colors.

{% highlight c# %}

chart.ColorModel.Palette          = SFChartColorPalette.Custom;

chart.ColorModel.CustomColors     = NSArray.FromObjects 
                                    (UIColor.FromRGB (238, 241, 11),
                                    UIColor.FromRGB (139, 139, 139),
                                    UIColor.FromRGB (100, 0, 5)); 


{% endhighlight %}

![](appearance_images/appearance_img2.png)

**None Palette**

None palette will not apply any color to the series. So in order to define the color for any series, you can use the Color property or the [`ColorModel`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.ChartBase~ColorModel.html) property of ChartSeries (The ColorModel of Series will be explained later in this document).

## Apply palette for Series

[`ColorModel`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~ColorModel.html) property of [`SFSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries.html) is used to define the colors for each data point. Following palettes are used to define the colors.

**Predefined Palettes**

Currently, Series supports three types of palette and None palette is the default palette for Series.
 
These predefined palettes are

* Metro
* Pineapple
* TomatoSpectrum

{% highlight c# %}

SFColumnSeries series       = new SFColumnSeries ();

series.ColorModel.Palette   = SFChartColorPalette.Metro; 

{% endhighlight %}

![](appearance_images/appearance_img3.png)

**Custom Palette**

Series will use the colors from `CustomBrushes` property if the [`ColorModel.Palette`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartColorModel~Palette.html) property of series is set to [`Custom`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartColorPalette.html).

Following code illustrates how to set the custom colors.


{% highlight c# %}

SFColumnSeries series           = new SFColumnSeries ();

series.ColorModel.Palette       = SFChartColorPalette.Custom;

series.ColorModel.CustomColors  = NSArray.FromObjects 
                                    (UIColor.Red, 
                                    UIColor.Gray,
                                    UIColor.Blue, 
                                    UIColor.Brown, 
                                    UIColor.Purple); 


{% endhighlight %}


![](appearance_images/appearance_img4.png)

**None Palette**

None palette will not apply any color to the data points. So in order to define the color for the data points, you can use the [`Color`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~Color.html) property of ChartSeries.