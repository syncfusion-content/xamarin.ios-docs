---
layout: post
title: Trackball | SFChart | Xamarin.iOS | Syncfusion
description: How to add trackball behavior in SFChart
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Trackball

Trackball feature displays the tooltip for the data points that are closer to the point where you touch on the chart area. This feature, especially, can be used instead of data label feature when you cannot show data labels for all data points due to space constraint. To enable this feature, add an instance of [`SFChartTrackballBehavior`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballBehavior.html) to the [`Behaviors`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.ChartBase.html#Syncfusion_SfChart_iOS_ChartBase_Behaviors) collections property of [`SFChart`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChart.html) using [`AddChartBehavior`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChart.html#Syncfusion_SfChart_iOS_SFChart_AddChartBehavior_Syncfusion_SfChart_iOS_SFChartBehavior_) method. Trackball will be activated once you long-press anywhere on the chart area. Once it is activated, it will appear in the UI and move based on your touch movement until you stop touching on the chart.

You can use the following properties to show/hide the line and labels.

* `ShowLabel` – Shows/hides trackball label. Default value is true.

* `ShowLine` – Shows/hides the trackball line. Default value is true.


{% highlight c# %}

SFChartTrackballBehavior behavior = new SFChartTrackballBehavior ();

chart.AddChartBehavior (behavior); 

{% endhighlight %}


![Trackball support in Xamarin.iOS Chart](trackball_images/trackball_img1.png)

## Label Display Mode

[`LabelDisplayMode`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballBehavior.html#Syncfusion_SfChart_iOS_SFChartTrackballBehavior_LabelDisplayMode) property is used to specify whether to display label for all the data points along the vertical line or display only single label. Following are the two options you can set to this property,

* [`FloatAllPoints`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballLabelDisplayMode.html) – Displays label for all the data points along the vertical line.
* [`GroupAllPoints`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballLabelDisplayMode.html) – Displays label for all the data points on top of the chart along the vertical line.
* [`NearestPoint`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballLabelDisplayMode.html) – Displays label for single data point that is nearer to the touch contact position.

{% highlight c# %}

SFChartTrackballBehavior behavior   = new SFChartTrackballBehavior ();

behavior.LineStyle.Visible          = false;

behavior.LabelDisplayMode           = SFChartTrackballLabelDisplayMode.NearestPoint;

chart.AddChartBehavior (behavior);


{% endhighlight %}


In the following screenshot, trackball label is shown for only single data point,

![Label display mode support for trackball in Xamarin.iOS Chart](trackball_images/trackball_img2.png)

## Activation mode

The [`ActivationMode`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballBehavior.html#Syncfusion_SfChart_iOS_SFChartTrackballBehavior_ActivationMode) property is used to restrict the visibility of trackball based on the touch actions. The default value of this property is [`SFChartTrackballActivationMode.LongPress`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballActivationMode.html).

The SFChartTrackballActivationMode enum contains the following values:

* [`LongPress`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballActivationMode.html) – Activates trackball only when performing the long press action.
* [`TouchMove`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballActivationMode.html) – Activates trackball only when performing touch move action.
* [`None`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballActivationMode.html) – Hides the visibility of trackball when setting activation mode to [`None`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballActivationMode.html). It will be activated when calling the [`Show`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballBehavior.html#Syncfusion_SfChart_iOS_SFChartTrackballBehavior_Show_CoreGraphics_CGPoint_) method.

## Customizing appearance

**Customize Trackball Labels**

The [`LabelStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballBehavior.html#Syncfusion_SfChart_iOS_SFChartTrackballBehavior_LabelStyle) property provides options to customize the trackball labels.

* [`BorderColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_BorderColor) – used to change the label border color.
* [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_BackgroundColor) – used to change the label background color.
* [`BorderWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_BorderWidth) – used to change the label border width.
* [`Color`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_Color) – used to change the text color.
* [`Font`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_Font) – used to change label font size, family and weight.
* [`Visible`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballLabelStyle.html#Syncfusion_SfChart_iOS_SFChartTrackballLabelStyle_Visible) – used to control the visibility of label.
* [`Margin`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_Margin) – used to set the margin for label.
* [`LabelFormatter`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_LabelFormatter)– used to format the label.

{% highlight c# %}

SFChartTrackballBehavior behavior   = new SFChartTrackballBehavior ();

behavior.LabelStyle.BorderColor     = UIColor.Brown;

behavior.LabelStyle.BorderWidth     = 2;

behavior.LabelStyle.Font            = UIFont.ItalicSystemFontOfSize (18);

behavior.LabelStyle.BackgroundColor = UIColor.Cyan;

behavior.LabelStyle.Color           = UIColor.Red;

chart.AddChartBehavior (behavior); 


{% endhighlight %}



**Customize Trackball Marker**

The [`MarkerStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballBehavior.html#Syncfusion_SfChart_iOS_SFChartTrackballBehavior_MarkerStyle) property provides options to customize the trackball markers.

* [`Visible`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballMarkerStyle.html#Syncfusion_SfChart_iOS_SFChartTrackballMarkerStyle_Visible) – used to enable / disable the marker. Default value is true.
* [`BorderColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballMarkerStyle.html#Syncfusion_SfChart_iOS_SFChartTrackballMarkerStyle_BorderColor) – used to change the marker border color.
* [`Color`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballMarkerStyle.html#Syncfusion_SfChart_iOS_SFChartTrackballMarkerStyle_Color) – used to change the marker background color.
* [`BorderWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballMarkerStyle.html#Syncfusion_SfChart_iOS_SFChartTrackballMarkerStyle_BorderWidth) – used to change the width of the marker border.
* [`Width`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballMarkerStyle.html#Syncfusion_SfChart_iOS_SFChartTrackballMarkerStyle_Width) – used to change the width of the marker.
* [`Height`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballMarkerStyle.html#Syncfusion_SfChart_iOS_SFChartTrackballMarkerStyle_Height) – used to change the height of the marker.
* [`MarkerType`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballMarkerStyle.html#Syncfusion_SfChart_iOS_SFChartTrackballMarkerStyle_MarkerType) – used to change the shapes of the marker.


{% highlight c# %}

SFChartTrackballBehavior behavior   = new SFChartTrackballBehavior ();

behavior.MarkerStyle.BorderWidth    = 1;

behavior.MarkerStyle.BorderColor    = UIColor.Purple;

behavior.MarkerStyle.Height         = 8;

behavior.MarkerStyle.Width          = 8;

behavior.MarkerStyle.Color          = UIColor.Green;

behavior.MarkerStyle.Visible        = true;

chart.AddChartBehavior (behavior); 


{% endhighlight %}



**Customize Trackball Line**

The [`LineStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballBehavior.html#Syncfusion_SfChart_iOS_SFChartTrackballBehavior_LineStyle) property provides options to customize the trackball line.

* [`Visible`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballLineStyle.html#Syncfusion_SfChart_iOS_SFChartTrackballLineStyle_Visible) – used to enable / disable the line. Default value is true.
* [`LineWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLineStyle.html#Syncfusion_SfChart_iOS_SFLineStyle_LineWidth) – used to change the stroke width of the line.
* [`LineColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLineStyle.html#Syncfusion_SfChart_iOS_SFLineStyle_LineColor) – used to change the stroke color of the line.
* [`Dashes`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballLineStyle.html#Syncfusion_SfChart_iOS_SFChartTrackballLineStyle_Dashes) – Specifies the dashes to be applied on the line.

{% highlight c# %}

SFChartTrackballBehavior behavior = new SFChartTrackballBehavior ();

behavior.LineStyle.Visible        = true;

behavior.LineStyle.LineWidth      = new NSNumber (2);

behavior.LineStyle.LineColor      = UIColor.Blue;

NSObject[] dashes                 = new NSObject[2];

dashes [0]                        = (NSNumber)2;

dashes [1]                        = (NSNumber)3;

behavior.LineStyle.Dashes         = NSArray.FromNSObjects (dashes);

chart.AddChartBehavior (behavior); 


{% endhighlight %}



Following screenshot illustrates the customization of trackball elements.

![Customizing the appearance of trackball label in Xamarin.iOS Chart](trackball_images/trackball_img3.png)

## Axis label alignment

The position of trackball’s axis label can be changed using the [`LabelAlignment`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballAxisLabelStyle.html#Syncfusion_SfChart_iOS_SFChartTrackballAxisLabelStyle_LabelAlignment) property of [`SFChartTrackballAxisLabelStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballAxisLabelStyle.html). The following options are available in [`LabelAlignment`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballAxisLabelStyle.html#Syncfusion_SfChart_iOS_SFChartTrackballAxisLabelStyle_LabelAlignment).

* [`Far`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartAlignment.html) - The label will be positioned below the tick in vertical axis and right of the tick in horizontal axis. 
* [`Near`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartAlignment.html) - The label will be positioned above the tick in vertical axis and left of the tick in horizontal axis.
* [`Center`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartAlignment.html) - The label will be positioned at the center of tick. This is the default value.

## Show/hide the series label

This feature is used to show/hide the trackball label of the series by using [`CartesianSeries.ShowTrackballInfo`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFCartesianSeries.html#Syncfusion_SfChart_iOS_SFCartesianSeries_ShowTrackballInfo) property. Default value of [`CartesianSeries.ShowTrackballInfo`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFCartesianSeries.html#Syncfusion_SfChart_iOS_SFCartesianSeries_ShowTrackballInfo) property is `True`.

{% highlight c# %}

SFChart chart = new SFChart();
...

SFLineSeries lineSeries = new SFLineSeries()
{
    ItemsSource = Data,
    XBindingPath = "Year",
    YBindingPath = "Value",
    ShowTrackballInfo = false

};
chart.Series.Add(lineSeries);

{% endhighlight %}

![Showing and hiding the trackball label for series in Xamarin.iOS Chart](trackball_images/series_trackball.png)

## Methods

### Show method

The [`Show`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballBehavior.html#Syncfusion_SfChart_iOS_SFChartTrackballBehavior_Show_CoreGraphics_CGPoint_) method is used to activate the trackball at the specified location.

{% highlight c# %} 
[C#]

trackball.Show(point);

{% endhighlight %}

### Hide method

The [`Hide`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballBehavior.html#Syncfusion_SfChart_iOS_SFChartTrackballBehavior_Hide) method is used to hide the trackball programmatically.

{% highlight c# %} 
[C#]

trackball.Hide();

{% endhighlight %}

### HitTest method

The [`HitTest`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballBehavior.html#Syncfusion_SfChart_iOS_SFChartTrackballBehavior_HitTest_System_Single_System_Single_) method is used to check whether the point is in trackball or not.

{% highlight c# %} 
[C#]

trackball.HitTest(pointX, pointY);

{% endhighlight %}

### TrackballLabelsGenerated

To customize the appearance of trackball label based on condition, override the TrackballLabelsGenerated method of [`SFChartTrackballBehavior`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballBehavior.html). The argument of this method is [`SFChartPointInfo`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPointInfo.html) which contains the following properties: 

* [`Label`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPointInfo.html#Syncfusion_SfChart_iOS_SFChartPointInfo_Label) -  Used to provide text for trackball label.
* [`Visible`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPointInfo.html#Syncfusion_SfChart_iOS_SFChartPointInfo_Visible) - Determines the visibility of trackball.
* [`Series`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPointInfo.html#Syncfusion_SfChart_iOS_SFChartPointInfo_Series) - Gets the respective series of the data point in which the trackball is activated.
* [`LabelStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPointInfo.html#Syncfusion_SfChart_iOS_SFChartPointInfo_LabelStyle) - Customize the appearance of trackball label.
* [`MarkerStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPointInfo.html#Syncfusion_SfChart_iOS_SFChartPointInfo_MarkerStyle) - Gets the marker style of trackball label.
* [`Data`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPointInfo.html#Syncfusion_SfChart_iOS_SFChartPointInfo_Data) - Gets the corresponding data model of the trackball label.
* [`X`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPointInfo.html#Syncfusion_SfChart_iOS_SFChartPointInfo_X) - Positions the trackball label horizontally.
* [`Y`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPointInfo.html#Syncfusion_SfChart_iOS_SFChartPointInfo_Y) - Positions the trackball label vertically.
* [`Color`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPointInfo.html#Syncfusion_SfChart_iOS_SFChartPointInfo_Color) - Customize the color of trackball label. 
