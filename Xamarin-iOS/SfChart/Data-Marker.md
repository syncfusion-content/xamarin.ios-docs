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


![Data markers support in Xamarin.iOS Chart](Datamarker_images/DataMarker.png)

## Customizing Labels

Data labels are enabled by default but you can also change the visibility of the labels using [`ShowLabel`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarker.html#Syncfusion_SfChart_iOS_SFChartDataMarker_ShowLabel) property of [`SFChartDataMarker`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarker.html). The label appearance can be customized using [`LabelStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarker.html#Syncfusion_SfChart_iOS_SFChartDataMarker_LabelStyle) property.

 The following properties are used to customize the data marker label appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_Color) – used to change the color of the label.
* [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_BackgroundColor) – used to change the background color of the label.
* [`BorderColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_BorderColor) – used to change the border color.
* [`BorderWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_BorderWidth) – used to change the thickness of the border.
* [`Font`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_Font) – used to change the text size, font family and font weight of the label.
* [`Margin`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_Margin) - used to set the margin of the label.
* [`Angle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDataMarkerLabelStyle.html#Syncfusion_SfChart_iOS_SFDataMarkerLabelStyle_Angle) – used to rotate the labels.
* [`LabelPadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDataMarkerLabelStyle.html#Syncfusion_SfChart_iOS_SFDataMarkerLabelStyle_LabelPadding) - used to move the data label in the respective direction. For example, the positive labels in column series will be moved upwards and negative labels in column series will be moved downwards.

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

![Customizing the labels of data markers in Xamarin.iOS Chart](Datamarker_images/Customizing_Labels.png)

## Formatting Label Content

You can customize the content of the label using [`LabelContent`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarker.html#Syncfusion_SfChart_iOS_SFChartDataMarker_LabelContent) property. Following are the two options that are supported now,

* [`SFChartLabelContent.Percentage`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartLabelContent.html) – This will show the percentage value of corresponding data point Y value, this is often used in pie, doughnut, funnel and pyramid series types.
* [`SFChartLabelContent.YValues`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartLabelContent.html) – This will show the corresponding Y value (Default).

{% highlight c# %}

pieSeries.DataMarker.LabelContent = SFChartLabelContent.Percentage;
{% endhighlight %}

![Formatting the label content of data markers in Xamarin.iOS Chart](Datamarker_images/Label_Content.png)

## Label Position

The [`LabelPosition`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDataMarkerLabelStyle.html#Syncfusion_SfChart_iOS_SFDataMarkerLabelStyle_LabelPosition) property is used to position the data marker labels at [`Center`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarkerLabelPosition.html), [`Inner`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarkerLabelPosition.html) and [`Outer`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarkerLabelPosition.html) position of the actual data point position. By default, labels are positioned based on the series types for better readability. You can move the labels horizontally and vertically using [`OffsetX`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDataMarkerLabelStyle.html#Syncfusion_SfChart_iOS_SFDataMarkerLabelStyle_OffsetX) and [`OffsetY`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDataMarkerLabelStyle.html#Syncfusion_SfChart_iOS_SFDataMarkerLabelStyle_OffsetY) properties respectively.

The following screenshot illustrates the default position of data marker labels,

![Positioning the data marker labels support in Xamarin.iOS Chart](Datamarker_images/LabelPosition_Default.png)


The following code sample illustrates the center position of data marker labels,

{% highlight c# %}

series.DataMarker.LabelStyle.LabelPosition = SFChartDataMarkerLabelPosition.Center;
{% endhighlight %}

![Positioning the data marker labels support in Xamarin.iOS Chart](Datamarker_images/LabelPosition_Center.png)

The following code sample illustrates the Inner position of data marker labels,

{% highlight c# %}

series.DataMarker.LabelStyle.LabelPosition = SFChartDataMarkerLabelPosition.Inner;
{% endhighlight %}

![Positioning the data marker labels support in Xamarin.iOS Chart](Datamarker_images/LabelPosition_Inner.png)


The following code sample illustrates the outer position of data marker labels, 

{% highlight c# %}

series.DataMarker.LabelStyle.LabelPosition = SFChartDataMarkerLabelPosition.Outer;
{% endhighlight %}


![Positioning the data marker labels support in Xamarin.iOS Chart](Datamarker_images/LabelPosition_Outer.png)


# Smart Labels

This feature is used to arrange the data marker labels smartly and avoid the intersection when there is
overlapping of labels. The property [`EnableSmartLabels`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFCircularSeries.html#Syncfusion_SfChart_iOS_SFCircularSeries_EnableSmartLabels) in [`CircularSeries`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFCircularSeries.html), is used to arrange the data marker labels
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

![Smart labels support for data markers in Xamarin.iOS Chart](Datamarker_images/Smartlabels.png)

## Customizing Marker Shapes

Shapes can be added to chart data marker by setting the [`ShowMarker`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarker.html#Syncfusion_SfChart_iOS_SFChartDataMarker_ShowMarker) property to true. There are different shapes you can set to the chart using [`MarkerType`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarker.html#Syncfusion_SfChart_iOS_SFChartDataMarker_MarkerType) property such as rectangle, circle, diamond etc. Following properties are used to customize marker appearance,

* [`MarkerWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarker.html#Syncfusion_SfChart_iOS_SFChartDataMarker_MarkerWidth) - used to change the width of the marker
* [`MarkerHeight`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarker.html#Syncfusion_SfChart_iOS_SFChartDataMarker_MarkerHeight) - used to change the height of the marker
* [`MarkerColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarker.html#Syncfusion_SfChart_iOS_SFChartDataMarker_MarkerColor) - used to change the color of the marker
* [`MarkerBorderColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarker.html#Syncfusion_SfChart_iOS_SFChartDataMarker_MarkerBorderColor) - used to change the border color of the shape
* [`MarkerBorderWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarker.html#Syncfusion_SfChart_iOS_SFChartDataMarker_MarkerBorderWidth) – used to change the marker border thickness

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

![Data markers shape customization support in Xamarin.iOS Chart](Datamarker_images/Marker.png)

## Apply series color

The [`UseSeriesPalette`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarker.html#Syncfusion_SfChart_iOS_SFChartDataMarker_UseSeriesPalette) property is used to apply the series color to background color of data marker labels. The default value of this property is true.

{% highlight c# %}

lineSeries.DataMarker.ShowLabel  = true;

lineSeries.DataMarker.UseSeriesPalette = false;

{% endhighlight %}

## Connector Line

This feature is used to connect label and data point using a line. It can be enabled for any chart types but this is often used with Pie and Doughnut chart types. The [`ConnectorLineStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarker.html#Syncfusion_SfChart_iOS_SFChartDataMarker_ConnectorLineStyle) property used to customize the connector line.

* [`LineColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLineStyle.html#Syncfusion_SfChart_iOS_SFLineStyle_LineColor) – used to change the color of the line.
* [`LineWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLineStyle.html#Syncfusion_SfChart_iOS_SFLineStyle_LineWidth) – used to change the stroke thickness of the line.
* [`Dashes`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFConnectorLineStyle.html#Syncfusion_SfChart_iOS_SFConnectorLineStyle_Dashes) – used to set the dashes for the line.
* [`ConnectorHeight`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFConnectorLineStyle.html#Syncfusion_SfChart_iOS_SFConnectorLineStyle_ConnectorHeight) - used to set the height of the line.
* [`ConnectorRotationAngle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFConnectorLineStyle.html#Syncfusion_SfChart_iOS_SFConnectorLineStyle_ConnectorRotationAngle) - used to set the rotation angle of the line.

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


![Connector line support for data markers in Xamarin.iOS Chart](Datamarker_images/ConnectorLine.png)

N> For Pie and Doughnut series, you can set the [`Bezier`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartConnectorLineType.html) curve for connector line using [`ConnectorLineType`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFCircularSeries.html#Syncfusion_SfChart_iOS_SFCircularSeries_ConnectorLineType) property of Pie and Doughnut series.

## Event

### DataMarkerLabelCreated

The [`DataMarkerLabelCreated`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFSeries.html) event occurs when the data marker label is created. This argument contains object of the [`DataMarkerLabel`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.DataMarkerLabel.html). The following properties are available in DataMarkerLabel to customize the appearance of data markers based on condition.

* [`Label`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.DataMarkerLabel.html#Syncfusion_SfChart_iOS_DataMarkerLabel_Label) – Gets or sets the text of data marker.
* [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.DataMarkerLabel.html#Syncfusion_SfChart_iOS_DataMarkerLabel_BackgroundColor) – Gets or sets the background color of data marker label.
* [`Index`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.DataMarkerLabel.html#Syncfusion_SfChart_iOS_DataMarkerLabel_Index) – Gets the data point index of data marker label.
* [`XPosition`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.DataMarkerLabel.html#Syncfusion_SfChart_iOS_DataMarkerLabel_XPosition) – Gets the x-position of data marker label.
* [`YPosition`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.DataMarkerLabel.html#Syncfusion_SfChart_iOS_DataMarkerLabel_YPosition) – Gets the y-position of data marker label.
* [`LabelStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.DataMarkerLabel.html#Syncfusion_SfChart_iOS_DataMarkerLabel_LabelStyle) – Gets or sets the label style to customize the appearance of individual data marker label.
* [`MarkerWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.DataMarkerLabel.html#Syncfusion_SfChart_iOS_DataMarkerLabel_MarkerWidth) – Gets or sets the marker width.
* [`MarkerHeight`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.DataMarkerLabel.html#Syncfusion_SfChart_iOS_DataMarkerLabel_MarkerHeight) – Gets or sets the marker height.
* [`MarkerBorderWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.DataMarkerLabel.html#Syncfusion_SfChart_iOS_DataMarkerLabel_MarkerBorderWidth) – Gets or sets the border width of marker symbol.
* [`MarkerBorderColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.DataMarkerLabel.html#Syncfusion_SfChart_iOS_DataMarkerLabel_MarkerBorderColor) – Gets or sets the border color of marker symbol.
* [`MarkerColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.DataMarkerLabel.html#Syncfusion_SfChart_iOS_DataMarkerLabel_MarkerColor) – Gets or sets the marker color.
* [`MarkerType`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.DataMarkerLabel.html#Syncfusion_SfChart_iOS_DataMarkerLabel_MarkerType) – Gets or sets the shape type of marker. The available shapes are [`Ellipse`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarkerType.html), [`Diamond`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarkerType.html), [`Hexagon`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarkerType.html), [`Cross`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarkerType.html), [`HorizontalLine`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarkerType.html), [`VerticalLine`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarkerType.html), [`InvertedTriangle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarkerType.html), [`Triangle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarkerType.html), [`Pentagon`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarkerType.html), [`Plus`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarkerType.html), and [`Square`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDataMarkerType.html).
* [`View`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.DataMarkerLabel.html#Syncfusion_SfChart_iOS_DataMarkerLabel_View) - Gets or sets the view.
