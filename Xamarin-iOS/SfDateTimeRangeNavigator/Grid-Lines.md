---
layout: post
title: Grid Lines | SFDateTimeRangeNavigator | Xamarin.iOS | Syncfusion
description: How to customize the minor and major grid lines of range navigator
platform: xamarin.ios
control: SFDateTimeRangeNavigator
documentation: ug
---

# Grid Lines

The `MinorScaleStyle` and `MajorScaleStyle` properties of `SFDateTimeRangeNavigator` used to customize the minor and major grid lines. Following properties are available in each scale style to configure the grid lines.

* `ShowGridLines` – used to set the visibility of grid lines
* `GridLineWidth` – used to set the width for grid lines
* `GridLineColor` – used to set the color for grid lines
* `GridLineDashes` – used to set dashes for grid lines

{% highlight c# %}

SFDateTimeRangeNavigator rangeNavigator = new SFDateTimeRangeNavigator ();

rangeNavigator.MajorScaleStyle.ShowGridLines = true;
rangeNavigator.MajorScaleStyle.GridLineWidth = 2;
rangeNavigator.MajorScaleStyle.GridLineColor = UIColor.Red;
        
rangeNavigator.MinorScaleStyle.ShowGridLines = true;
rangeNavigator.MinorScaleStyle.GridLineWidth = 1;
rangeNavigator.MinorScaleStyle.GridLineColor = UIColor.Green;
rangeNavigator.MinorScaleStyle.GridLineDashes = NSArray.FromObjects (5, 10);

this.View.AddSubview(rangeNavigator);

{% endhighlight %}

![]( GridLines_images/GridLines.png)