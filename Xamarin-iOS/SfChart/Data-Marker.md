---
layout: post
title: Markers and data labels in SFChart | SFChart | Xamarin.iOS | Syncfusion
description: Learn how to add markers and data point labels to a Chart series
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Data Markers

Data markers are used to provide information about the data points to the user. You can add a shape and label to adorn each data point. This can be enabled using following code snippet,

{% highlight c# %}

lineSeries.DataMarker.ShowLabel	 = true;

lineSeries.DataMarker.ShowMarker = true;
{% endhighlight %}


![](Datamarker_images/DataMarker.png)

## Customizing Labels

 The following properties are used to customize the data marker label appearance.

* `Color` – used to change the color of the label
* `BackgroundColor` – used to change the label background color
* `BorderColor` – used to change the border color
* `BorderWidth` – used to change the thickness of the border
* `Font` – used to change the text size, font family and font weight
* `Margin` - used to change the margin size for labels
* `Angle` – used to rotate the labels

Following code snippet illustrates the customization of label and its background,

{% highlight c# %}

lineSeries.DataMarker.LabelStyle.Color           = UIColor.Blue;

lineSeries.DataMarker.LabelStyle.BorderColor     = UIColor.Red;

lineSeries.DataMarker.LabelStyle.BorderWidth     = 2;

lineSeries.DataMarker.LabelStyle.BackgroundColor = UIColor.Cyan;

lineSeries.DataMarker.LabelStyle.Angle           = 315;

lineSeries.DataMarker.LabelStyle.Margin          = new UIEdgeInsets(5,0,0,0);

lineSeries.DataMarker.LabelStyle.Font            = UIFont.ItalicSystemFontOfSize (18);
{% endhighlight %}

![](Datamarker_images/Customizing_Labels.png)

## Formatting Label Content

You can customize the content of the label using `LabelContent` property. Following are the two options that are supported now,

* `SFChartLabelContent.Percentage` – This will show the percentage value of corresponding data point Y value, this is often used in pie, doughnut, funnel and pyramid series types
* `SFChartLabelContent.YValues` – This will show the corresponding Y value (Default)

{% highlight c# %}

pieSeries.DataMarker.LabelContent = SFChartLabelContent.Percentage;
{% endhighlight %}

![](Datamarker_images/Label_Content.png)

## Label Position

This feature is used to position the data marker labels at Center, Inner and Outer position of the actual data point position. By default, labels are positioned based on the series types for better readability. You can move the labels horizontally and vertically using `OffsetX` and `OffsetY` properties respectively.

The following screenshot illustrates the default position of data marker labels,

![](Datamarker_images/LabelPosition_Default.png)


The following code sample illustrates the center position of data marker labels,

{% highlight c# %}

series.DataMarker.LabelStyle.LabelPosition = SFChartDataMarkerLabelPosition.Center;
{% endhighlight %}

![](Datamarker_images/LabelPosition_Center.png)

The following code sample illustrates the Inner position of data marker labels,

{% highlight c# %}

series.DataMarker.LabelStyle.LabelPosition = SFChartDataMarkerLabelPosition.Inner;
{% endhighlight %}

![](Datamarker_images/LabelPosition_Inner.png)


The following code sample illustrates the outer position of data marker labels, 

{% highlight c# %}

series.DataMarker.LabelStyle.LabelPosition = SFChartDataMarkerLabelPosition.Outer;
{% endhighlight %}


![](Datamarker_images/LabelPosition_Outer.png)


# Smart Labels

This feature is used to arrange the data marker labels smartly and avoid the intersection when there is
overlapping of labels. The property EnableSmartLabels in CircularSeries, is used to arrange the data marker labels
smartly. By default, it is false, we need to enable this property.

The following code sample illustrates how to enable the smart labels.	


{% highlight c# %}

SFPieSeries series              = new SFPieSeries ();

series.StartAngle               = 75;

series.EndAngle                 = 435;

series.EnableSmartLabels        = true;

series.DataMarkerPosition       = SFChartCircularSeriesLabelPosition.OutsideExtended;

series.ConnectorLineType        = SFChartConnectorLineType.Bezier;

series.DataMarker.ShowLabel     = true;

series.LegendIcon               = SFChartLegendIcon.Rectangle;
return series; 


{% endhighlight %}

![](Datamarker_images/Smartlabels.png)

## Customizing Marker Shapes

Shapes can be added to chart data marker by setting the `ShowMarker` property to true. There are different shapes you can set to the chart using MarkerType property such as rectangle, circle, diamond etc. Following properties are used to customize marker appearance,

* `MarkerWidth` - used to change the width of the marker
* `MarkerHeight` - used to change the height of the marker
* `MarkerColor` - used to change the color of the marker
* `MarkerBorderColor` - used to change the border color of the shape
* `MarkerBorderWidth` – used to change the marker border thickness

The following code example shows how to enable marker and specify its types,


{% highlight c# %}

lineSeries.DataMarker.ShowLabel         = false;

lineSeries.DataMarker.ShowMarker        = true;

lineSeries.DataMarker.MarkerType        = SFChartDataMarkerType.Hexagon;

lineSeries.DataMarker.MarkerWidth       = 20;

lineSeries.DataMarker.MarkerHeight      = 20;

lineSeries.DataMarker.MarkerColor       = UIColor.Cyan;

lineSeries.DataMarker.MarkerBorderColor = UIColor.Red;

lineSeries.DataMarker.MarkerBorderWidth = 2;
{% endhighlight %}

![](Datamarker_images/Marker.png)


## Connector Line

This feature is used to connect label and data point using a line. It can be enabled for any chart types but this is often used with Pie and Doughnut chart types. Following properties used to customize connector line,

* `LineColor` – used to change the color of the line
* `LineWidth` – used to change the stroke thickness of the line
* `Dashes` – used to set the dashes for the line

The following code illustrates how to specify the connector height and its angle,


{% highlight c# %}

lineSeries.DataMarker.ConnectorLineStyle.ConnectorHeight        = 50;

lineSeries.DataMarker.ConnectorLineStyle.ConnectorRotationAngle = 175;

lineSeries.DataMarker.ConnectorLineStyle.LineColor              = UIColor.Blue;

lineSeries.DataMarker.ConnectorLineStyle.LineWidth              = 3;

NSObject[] dashes   = new NSObject[2];

dashes [0]          = (NSNumber)2;

dashes [1]          = (NSNumber)3;

lineSeries.DataMarker.ConnectorLineStyle.Dashes                 = NSArray.FromNSObjects (dashes);
{% endhighlight %}


![](Datamarker_images/ConnectorLine.png)

N> For Pie and Doughnut series, you can set the Bezier curve for connector line using connectorType property of Pie and Doughnut series.