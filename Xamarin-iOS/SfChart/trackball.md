---
layout: post
title: Trackball | SFChart | Xamarin.iOS | Syncfusion
description: How to add trackball behavior in SFChart
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Trackball

Trackball feature displays the tooltip for the data points that are closer to the point where you touch on the chart area. This feature, especially, can be used instead of data label feature when you cannot show data labels for all data points due to space constraint. To enable this feature, add an instance of `SFChartTrackballBehavior` to the `SFChart` using `AddChartBehavior:` method. Trackball will be activated once you long-press anywhere on the chart area. Once it is activated, it will appear in the UI and move based on your touch movement until you stop touching on the chart.

You can use the following properties to show/hide the line and labels.

* `ShowLabel` – Shows/hides trackball label. Default value is true.

* `ShowLine` – Shows/hides the trackball line. Default value is true.


{% highlight c# %}

SFChartTrackballBehavior behavior = new SFChartTrackballBehavior ();

chart.AddChartBehavior (behavior); 

{% endhighlight %}


![](trackball_images/trackball_img1.png)

## Label Display Mode

`LabelDisplayMode` property is used to specify whether to display label for all the data points along the vertical line or display only single label. Following are the two options you can set to this property,

* `FloatAllPoints` – Displays label for all the data points along the vertical line.
* `GroupAllPoints` – Displays label for all the data points on top of the chart along the vertical line.
* `NearestPoint` – Displays label for single data point that is nearer to the touch contact position.

{% highlight c# %}

SFChartTrackballBehavior behavior   = new SFChartTrackballBehavior ();

behavior.LineStyle.Visible          = false;

behavior.LabelDisplayMode           = SFChartTrackballLabelDisplayMode.NearestPoint;

chart.AddChartBehavior (behavior);


{% endhighlight %}


In the following screenshot, trackball label is shown for only single data point,

![](trackball_images/trackball_img2.png)

## Customizing appearance

**Customize Trackball Labels**

Following properties are used to customize the trackball labels.

* `BorderColor` – used to change the label border color.
* `BackgroundColor` – used to change the label background color.
* `BorderWidth` – used to change the label border width.
* `Color` – used to change the text color.
* `Font` – used to change label font size, family and weight.
* `Visible` – used to control the visibility of label.
* `Margin` – used to set the margin for label.
* `LabelFormatter` – used to format the label.

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

Following properties are used to customize the trackball marker.

* `Visible` – used to enable / disable the marker. Default value is true.
* `BorderColor` – used to change the marker border color.
* `Color` – used to change the marker background color.
* `BorderWidth` – used to change the width of the marker border.
* `Width` – used to change the width of the marker.
* `Height` – used to change the height of the marker.
* `MarkerType` – used to change the shapes of the marker.


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

Following properties are used to customize the trackball line.

* `Visible` – used to enable / disable the line. Default value is true.
* `LineWidth` – used to change the stroke width of the line.
* `LineColor` – used to change the stroke color of the line.
* `Dashes` – Specifies the dashes to be applied on the line.

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

![](trackball_images/trackball_img3.png)