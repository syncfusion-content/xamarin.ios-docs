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

Data labels are enabled by default but you can also change the visibility of the labels using [`ShowLabel`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartDataMarker~ShowLabel.html) property of [`SFChartDataMarker`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartDataMarker.html). The label appearance can be customized using [`LabelStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartDataMarker~LabelStyle.html) property.

 The following properties are used to customize the data marker label appearance.

* [`Color`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFLabelStyle~Color.html) – used to change the color of the label.
* [`BackgroundColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFLabelStyle~BackgroundColor.html) – used to change the background color of the label.
* [`BorderColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFLabelStyle~BorderColor.html) – used to change the border color.
* [`BorderWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFLabelStyle~BorderWidth.html) – used to change the thickness of the border.
* [`Font`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFLabelStyle~Font.html) – used to change the text size, font family and font weight of the label.
* [`Margin`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFLabelStyle~Margin.html) - used to set the margin of the label.
* [`Angle`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFDataMarkerLabelStyle~Angle.html) – used to rotate the labels.
* [`LabelPadding`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFDataMarkerLabelStyle~LabelPadding.html) - used to move the data label in the respective direction. For example, the positive labels in column series will be moved upwards and negative labels in column series will be moved downwards.

Following code snippet illustrates the customization of label and its background,

{% highlight c# %}

lineSeries.DataMarker.LabelStyle.Color           = UIColor.Blue;

lineSeries.DataMarker.LabelStyle.BorderColor     = UIColor.Red;

lineSeries.DataMarker.LabelStyle.BorderWidth     = 2;

lineSeries.DataMarker.LabelStyle.BackgroundColor = UIColor.Cyan;

lineSeries.DataMarker.LabelStyle.Angle           = 315;

lineSeries.DataMarker.LabelStyle.Margin          = new UIEdgeInsets(5,5,5,5);

lineSeries.DataMarker.LabelStyle.Font            = UIFont.ItalicSystemFontOfSize (18);
{% endhighlight %}

![](Datamarker_images/Customizing_Labels.png)

## Formatting Label Content

You can customize the content of the label using [`LabelContent`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartDataMarker~LabelContent.html) property. Following are the two options that are supported now,

* [`SFChartLabelContent.Percentage`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartLabelContent.html) – This will show the percentage value of corresponding data point Y value, this is often used in pie, doughnut, funnel and pyramid series types.
* [`SFChartLabelContent.YValues`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartLabelContent.html) – This will show the corresponding Y value (Default).

{% highlight c# %}

pieSeries.DataMarker.LabelContent = SFChartLabelContent.Percentage;
{% endhighlight %}

![](Datamarker_images/Label_Content.png)

## Label Position

The [`LabelPosition`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFDataMarkerLabelStyle~LabelPosition.html) property is used to position the data marker labels at [`Center`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartDataMarkerLabelPosition.html), [`Inner`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartDataMarkerLabelPosition.html) and [`Outer`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartDataMarkerLabelPosition.html) position of the actual data point position. By default, labels are positioned based on the series types for better readability. You can move the labels horizontally and vertically using [`OffsetX`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFDataMarkerLabelStyle~OffsetX.html) and [`OffsetY`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFDataMarkerLabelStyle~OffsetY.html) properties respectively.

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
overlapping of labels. The property [`EnableSmartLabels`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFCircularSeries~EnableSmartLabels.html) in [`CircularSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFCircularSeries.html), is used to arrange the data marker labels
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

Shapes can be added to chart data marker by setting the [`ShowMarker`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartDataMarker~ShowMarker.html) property to true. There are different shapes you can set to the chart using [`MarkerType`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartDataMarker~MarkerType.html) property such as rectangle, circle, diamond etc. Following properties are used to customize marker appearance,

* [`MarkerWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartDataMarker~MarkerWidth.html) - used to change the width of the marker
* [`MarkerHeight`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartDataMarker~MarkerHeight.html) - used to change the height of the marker
* [`MarkerColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartDataMarker~MarkerColor.html) - used to change the color of the marker
* [`MarkerBorderColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartDataMarker~MarkerBorderColor.html) - used to change the border color of the shape
* [`MarkerBorderWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartDataMarker~MarkerBorderWidth.html) – used to change the marker border thickness

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

## Apply series color

The [`UseSeriesPalette`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartDataMarker~UseSeriesPalette.html) property is used to apply the series color to background color of data marker labels. The default value of this property is true.

{% highlight c# %}

lineSeries.DataMarker.ShowLabel  = true;

lineSeries.DataMarker.UseSeriesPalette = false;

{% endhighlight %}

## Connector Line

This feature is used to connect label and data point using a line. It can be enabled for any chart types but this is often used with Pie and Doughnut chart types. The [`ConnectorLineStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartDataMarker~ConnectorLineStyle.html) property used to customize the connector line.

* [`LineColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFLineStyle~LineColor.html) – used to change the color of the line.
* [`LineWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFLineStyle~LineWidth.html) – used to change the stroke thickness of the line.
* [`Dashes`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFConnectorLineStyle~Dashes.html) – used to set the dashes for the line.
* [`ConnectorHeight`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFConnectorLineStyle~ConnectorHeight.html) - used to set the height of the line.
* [`ConnectorRotationAngle`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFConnectorLineStyle~ConnectorRotationAngle.html) - used to set the rotation angle of the line.

The following code illustrates how to specify the connector height and its angle,


{% highlight c# %}

lineSeries.DataMarker.ConnectorLineStyle.ConnectorHeight = 50;

lineSeries.DataMarker.ConnectorLineStyle.ConnectorRotationAngle = 175;

lineSeries.DataMarker.ConnectorLineStyle.LineColor = UIColor.Blue;

lineSeries.DataMarker.ConnectorLineStyle.LineWidth = 3;

NSObject[] dashes = new NSObject[2];

dashes [0] = (NSNumber)2;

dashes [1] = (NSNumber)3;

lineSeries.DataMarker.ConnectorLineStyle.Dashes = NSArray.FromNSObjects (dashes);

{% endhighlight %}


![](Datamarker_images/ConnectorLine.png)

N> For Pie and Doughnut series, you can set the Bezier curve for connector line using [`ConnectorLineType`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFCircularSeries~ConnectorLineType.html) property of Pie and Doughnut series.

## Event

### DataMarkerLabelCreated

The [`DataMarkerLabelCreated`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~DataMarkerLabelCreated_EV.html) event occurs when the data marker label is created. This argument contains object of the [`DataMarkerLabel`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.DataMarkerLabel.html). The following properties are available in DataMarkerLabel to customize the appearance of data markers based on condition.

* [`Label`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.DataMarkerLabel~Label.html) – Gets or sets the text of data marker.
* [`BackgroundColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.DataMarkerLabel~BackgroundColor.html) – Gets or sets the background color of data marker label.
* [`Index`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.DataMarkerLabel~Index.html) – Gets the data point index of data marker label.
* [`XPosition`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.DataMarkerLabel~XPosition.html) – Gets the x-position of data marker label.
* [`YPosition`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.DataMarkerLabel~YPosition.html) – Gets the y-position of data marker label.
* [`LabelStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.DataMarkerLabel~LabelStyle.html) – Gets or sets the label style to customize the appearance of individual data marker label.
* [`MarkerWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.DataMarkerLabel~MarkerWidth.html) – Gets or sets the marker width.
* [`MarkerHeight`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.DataMarkerLabel~MarkerHeight.html) – Gets or sets the marker height.
* [`MarkerBorderWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.DataMarkerLabel~MarkerBorderWidth.html) – Gets or sets the border width of marker symbol.
* [`MarkerBorderColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.DataMarkerLabel~MarkerBorderColor.html) – Gets or sets the border color of marker symbol.
* [`MarkerColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.DataMarkerLabel~MarkerColor.html) – Gets or sets the marker color.
* [`MarkerType`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.DataMarkerLabel~MarkerType.html) – Gets or sets the shape type of marker. The available shapes are ellipse, diamond, hexagon, cross, HorizontalLine, VerticalLine, InvertedTriangle, triangle, pentagon, plus, and square.
* [`View`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.DataMarkerLabel~View.html) - Gets or sets the view.
