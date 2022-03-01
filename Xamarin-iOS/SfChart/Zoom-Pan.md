---
layout: post
title: Zooming and Panning | SFChart | Xamarin.iOS | Syncfusion
description: This section explains how to add ZoomPanBehavior to the chart and its features such as zooming types, zooming modes, delegates, and methods.
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Zooming and Panning

## Enable Zooming

Chart supports zooming to view the data clearly. To enable this feature, you need to add an instance of [`SFChartZoomPanBehavior`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html) to the [`Behaviors`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.ChartBase.html#Syncfusion_SfChart_iOS_ChartBase_Behaviors) collection using the [`AddChartBehavior`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChart.html#Syncfusion_SfChart_iOS_SFChart_AddChartBehavior_Syncfusion_SfChart_iOS_SFChartBehavior_) method of [`SFChart`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChart.html).

Following properties are used to configure the zooming feature,

* [`EnableZooming`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html#Syncfusion_SfChart_iOS_SFChartZoomPanBehavior_EnableZooming) – used to enable/disable the pinch zooming. Default value is true. 
* [`EnableDirectionalZooming`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html#Syncfusion_SfChart_iOS_SFChartZoomPanBehavior_EnableDirectionalZooming) - Enables or disables the pinch zooming based on pinch gesture direction. The default value of this property is false.
* [`EnableDoubleTap`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html#Syncfusion_SfChart_iOS_SFChartZoomPanBehavior_EnableDoubleTap) – when you enable this property, you can double tap on the chart to reset it to the original size or zoom in by one level.
* [`EnablePanning`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html#Syncfusion_SfChart_iOS_SFChartZoomPanBehavior_EnablePanning) – used to enable/disable the panning. Default value is true.
* [`MaximumZoomLevel`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html#Syncfusion_SfChart_iOS_SFChartZoomPanBehavior_MaximumZoomLevel) - used to determine the maximum zoom level of the chart.

Following code snippet illustrates how to enable zooming.

{% highlight c# %}

SFChartZoomPanBehavior zoomPan = new SFChartZoomPanBehavior ();

chart.AddChartBehavior (zoomPan); 

{% endhighlight %}

## Selection zooming

By specifying [`EnableSelectionZooming`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html#Syncfusion_SfChart_iOS_SFChartZoomPanBehavior_EnableSelectionZooming) property to true, you can double tap and drag to select a range on the chart to be zoomed in.

Following code snippet illustrates how to enable the box selection zooming,

{% highlight c# %}

SFChartZoomPanBehavior zoomPan = new SFChartZoomPanBehavior();
zoomPan.EnableSelectionZooming = true;
chart.AddChartBehavior (zoomPan); 

{% endhighlight %}

Following screenshot shows the box selection on chart area,

![Box selection support in Xamarin.iOS Chart](zoompan_images/zoompan_img1.png)

Following screenshot shows the zoomed area,

![Zoomed area in Xamarin.iOS Chart](zoompan_images/zoompan_img2.png)

### Selection rectangle customization

You can customize the selection rectangle using the below properties.

* [`SelectionRectBorderWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html#Syncfusion_SfChart_iOS_SFChartZoomPanBehavior_SelectionRectBorderWidth) - used to change the border width of selection rectangle.
* [`SelectionRectStrokeColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html#Syncfusion_SfChart_iOS_SFChartZoomPanBehavior_SelectionRectBorderColor) - used to change the border color of selection rectangle.
* [`SelectionRectBorderDashes`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html#Syncfusion_SfChart_iOS_SFChartZoomPanBehavior_SelectionRectBorderDashes) - used to change the border dashes of selection rectangle.
* [`SelectionRectFillColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html#Syncfusion_SfChart_iOS_SFChartZoomPanBehavior_SelectionRectFillColor) - used to change the fill color of selection rectangle.

### Show axis tooltip

The axis tooltip on selection zooming can be enabled using the [`SFChartAxis.TrackballLabelStyle.Visible`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballLabelStyle.html#Syncfusion_SfChart_iOS_SFChartTrackballLabelStyle_Visible) property. You can customize the appearance of the axis tooltip by the below properties of [`SFChartAxis.SFChartTrackballAxisLabelStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballAxisLabelStyle.html).

* [`LabelAlignment`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballAxisLabelStyle.html#Syncfusion_SfChart_iOS_SFChartTrackballAxisLabelStyle_LabelAlignment) - used to change the position of the axis label.
* [`BorderColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_BorderColor) – used to change the label border color.
* [`BorderWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_BorderWidth) – used to change the label border width.
* [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_BackgroundColor) – used to change the label background color.
* [`Color`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_Color) – used to change the label text color.
* [`Font`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_Font) – used to change the label font size, family and weight.
* [`LabelFormatter`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_LabelFormatter) – used to format the label.
* [`Margin`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_Margin) - used to change the margin for label.
* [`Visible`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartTrackballLabelStyle.html#Syncfusion_SfChart_iOS_SFChartTrackballLabelStyle_Visible) – used to control the visibility of axis tooltip label.

{% highlight c# %}

SFChart chart = new SFChart ();

SFNumericalAxis primaryAxis = new SFNumericalAxis();
primaryAxis.TrackballLabelStyle.Visible = true;
chart.PrimaryAxis = primaryAxis; 

SFNumericalAxis secondaryAxis = new SFNumericalAxis();
secondaryAxis.TrackballLabelStyle.Visible = true;
chart.SecondaryAxis = secondaryAxis; 

SFChartZoomPanBehavior zoomPan = new SFChartZoomPanBehavior();
zoomPan.EnableSelectionZooming = true;

chart.AddChartBehavior (zoomPan);

{% endhighlight %}

![Show axis tooltip on selection zooming in Xamarin.iOS Chart](zoompan_images/zoompan_img4.png)

## Zoom Mode

The [`ZoomMode`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html#Syncfusion_SfChart_iOS_SFChartZoomPanBehavior_ZoomMode) property specifies whether chart should be allowed to scale along horizontal axis or vertical axis or along both axis. The default value of [`ZoomMode`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html#Syncfusion_SfChart_iOS_SFChartZoomPanBehavior_ZoomMode) is [`SFChartZoomMode.XY`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomMode.html) (both axis).

Following code example illustrates how to restrict the chart to be zoomed only along horizontal axis,

{% highlight c# %}

SFChartZoomPanBehavior zoomPan = new SFChartZoomPanBehavior();

zoomPan.ZoomMode               = SFChartZoomMode.X;

chart.AddChartBehavior(zoomPan); 

{% endhighlight %}

![Zoom mode support in Xamarin.iOS Chart](zoompan_images/zoompan_img3.png)

## Auto interval on zooming

[`EnableAutoIntervalOnZooming`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_EnableAutoIntervalOnZooming) property determines the update of axis internal based on the current visible range while zooming the chart. Default value of this property is true. If this property is false, the nice internal will not be calculated for new range after zoom in and actual interval will be sustained.

## Delegates


We need to implement delegate to deal with the user interactions in chart for zooming and panning. In order to do this,you need to adopt the [`SFChartDelegate`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDelegate.html) protocol through the class extension as shown below.


{% highlight c# %}

public override void ViewDidLoad ()
{
    chart.Delegate = new ChartDelegate ();
}

public class ChartDelegate : SFChartDelegate
{
    public override void WillZoom (SFChart chart, SFChartZoomingInfo info)
    {

    }
}

{% endhighlight %}


**WillZoom**

The [`WillZoom`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDelegate.html#Syncfusion_SfChart_iOS_SFChartDelegate_WillZoom_Syncfusion_SfChart_iOS_SFChart_Syncfusion_SfChart_iOS_SFChartZoomingInfo_) delegate is called when the axis is started zooming, the argument includes the [`SFChartZoomingInfo`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomingInfo.html) which is used to get the zooming state. The argument contains the following information.

* [`Axis`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomInfo.html#Syncfusion_SfChart_iOS_SFChartZoomInfo_Axis) - the zoom start event will be triggered for all the axis in the chart.
* [`CurrentZoomFactor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomInfo.html#Syncfusion_SfChart_iOS_SFChartZoomInfo_CurrentZoomFactor) - used to get the new zoom factor of the corresponding axis.
* [`CurrentZoomPosition`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomInfo.html#Syncfusion_SfChart_iOS_SFChartZoomInfo_CurrentZoomPosition) - used to get the new zoom position of the corresponding axis.
* [`PreviousZoomFactor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomInfo.html#Syncfusion_SfChart_iOS_SFChartZoomInfo_PreviousZoomFactor) - used to get the previous zoom factor of the corresponding axis.
* [`PreviousZoomPosition`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomInfo.html#Syncfusion_SfChart_iOS_SFChartZoomInfo_PreviousZoomPosition) - used to get the previous zoom position of the corresponding axis.
* [`Cancel`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomingInfo.html#Syncfusion_SfChart_iOS_SFChartZoomingInfo_Cancel) - used to set the value indicating whether the zooming should be canceled. 
* [`State`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomInfo.html#Syncfusion_SfChart_iOS_SFChartZoomInfo_State) - used to get the [`SFChartZoomPanState`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanState.html) of the zooming.

**DidZoom**

The [`DidZoom`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDelegate.html#Syncfusion_SfChart_iOS_SFChartDelegate_DidZoom_Syncfusion_SfChart_iOS_SFChart_Syncfusion_SfChart_iOS_SFChartZoomInfo_) delegate is called when the axis is started zooming, the argument includes the [`SFChartZoomInfo`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomInfo.html) which is used to get the zooming state. The argument contains the following information.

* [`Axis`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomInfo.html#Syncfusion_SfChart_iOS_SFChartZoomInfo_Axis) - the zoom start event will be triggered for all the axis in the chart.
* [`CurrentZoomFactor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomInfo.html#Syncfusion_SfChart_iOS_SFChartZoomInfo_CurrentZoomFactor) - used to get the new zoom factor of the corresponding axis.
* [`CurrentZoomPosition`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomInfo.html#Syncfusion_SfChart_iOS_SFChartZoomInfo_CurrentZoomPosition) - used to get the new zoom position of the corresponding axis.
* [`PreviousZoomFactor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomInfo.html#Syncfusion_SfChart_iOS_SFChartZoomInfo_PreviousZoomFactor) - used to get the previous zoom factor of the corresponding axis.
* [`PreviousZoomPosition`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomInfo.html#Syncfusion_SfChart_iOS_SFChartZoomInfo_PreviousZoomPosition) - used to get the previous zoom position of the corresponding axis.
* [`State`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomInfo.html#Syncfusion_SfChart_iOS_SFChartZoomInfo_State) - used to get the [`SFChartZoomPanState`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanState.html) of the zooming.


**WillPan**

The [`WillPan`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDelegate.html#Syncfusion_SfChart_iOS_SFChartDelegate_WillPan_Syncfusion_SfChart_iOS_SFChart_Syncfusion_SfChart_iOS_SFChartPanningInfo_) delegate is called when the axis is started zooming, the argument includes the [`SFChartPanningInfo`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPanningInfo.html)which is used to get the zooming state. The argument contains the following information.

* [`Axis`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPanInfo.html#Syncfusion_SfChart_iOS_SFChartPanInfo_Axis) - the zoom start event will be triggered for all the axis in the chart.
* [`CurrentZoomPosition`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPanInfo.html#Syncfusion_SfChart_iOS_SFChartPanInfo_CurrentZoomPosition) - used to get the new zoom position of the corresponding axis.
* [`PreviousZoomPosition`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPanInfo.html#Syncfusion_SfChart_iOS_SFChartPanInfo_PreviousZoomPosition) - used to get the previous zoom position of the corresponding axis.
* [`Cancel`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPanningInfo.html#Syncfusion_SfChart_iOS_SFChartPanningInfo_Cancel) - used to set the value indicating whether the zooming should be canceled. 
* [`State`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPanInfo.html#Syncfusion_SfChart_iOS_SFChartPanInfo_State) - used to get the [`SFChartZoomPanState`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanState.html) of the zooming.

**DidPan**

The [`DidPan`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDelegate.html#Syncfusion_SfChart_iOS_SFChartDelegate_DidPan_Syncfusion_SfChart_iOS_SFChart_Syncfusion_SfChart_iOS_SFChartPanInfo_) delegate is called when the axis is started zooming, the argument includes the [`SFChartPanInfo`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPanInfo.html) which is used to get the zooming state. The argument contains the following information.

* [`Axis`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPanInfo.html#Syncfusion_SfChart_iOS_SFChartPanInfo_Axis) - the zoom start event will be triggered for all the axis in the chart.
* [`CurrentZoomPosition`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPanInfo.html#Syncfusion_SfChart_iOS_SFChartPanInfo_CurrentZoomPosition) - used to get the new zoom position of the corresponding axis.
* [`PreviousZoomPosition`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPanInfo.html#Syncfusion_SfChart_iOS_SFChartPanInfo_PreviousZoomPosition) - used to get the previous zoom position of the corresponding axis. 
* [`State`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartPanInfo.html#Syncfusion_SfChart_iOS_SFChartPanInfo_State) - used to get the [`SFChartZoomPanState`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanState.html) of the zooming.

**WillSelectionZoom**

The [`WillSelectionZoom`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDelegate.html#Syncfusion_SfChart_iOS_SFChartDelegate_WillSelectionZoom_Syncfusion_SfChart_iOS_SFChart_Syncfusion_SfChart_iOS_SFChartSelectionZoomingInfo_) delegate is called when the axis is started zooming, the argument includes the [`SFChartSelectionZoomingInfo`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartSelectionZoomingInfo.html) which is used to get the zooming state. The argument contains the following information.

* [`ZoomRect`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartSelectionZoomInfo.html#Syncfusion_SfChart_iOS_SFChartSelectionZoomInfo_ZoomRect) - contains the bounds of the currently selected region.
* [`Cancel`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartSelectionZoomingInfo.html#Syncfusion_SfChart_iOS_SFChartSelectionZoomingInfo_Cancel) - used to set the value indicating whether the box selection zooming should be canceled.
* [`State`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartSelectionZoomInfo.html#Syncfusion_SfChart_iOS_SFChartSelectionZoomInfo_State) - used to get the [`SFChartZoomPanState`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanState.html) of the zooming.

**DidSelectionZoom**

The [`DidSelectionZoom`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDelegate.html#Syncfusion_SfChart_iOS_SFChartDelegate_DidSelectionZoom_Syncfusion_SfChart_iOS_SFChart_Syncfusion_SfChart_iOS_SFChartSelectionZoomInfo_) delegate is called when the axis is started zooming, the argument includes the [`SFChartSelectionZoomInfo`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartSelectionZoomInfo.html) which is used to get the zooming state. The argument contains the following information.

* [`ZoomRect`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartSelectionZoomInfo.html#Syncfusion_SfChart_iOS_SFChartSelectionZoomInfo_ZoomRect) - contains the bounds of the currently selected region.
* [`State`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartSelectionZoomInfo.html#Syncfusion_SfChart_iOS_SFChartSelectionZoomInfo_State) - used to get the [`SFChartZoomPanState`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanState.html) of the zooming.

**DidResetZoom**

The [`DidResetZoom`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDelegate.html#Syncfusion_SfChart_iOS_SFChartDelegate_DidResetZoom_Syncfusion_SfChart_iOS_SFChart_Syncfusion_SfChart_iOS_SFChartResetZoomInfo_) delegate is called when the axis is started zooming, the argument includes the [`SFChartResetZoomInfo`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartResetZoomInfo.html) which is used to get the zooming state. The argument contains the following information.

 * [`Axis`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartResetZoomInfo.html#Syncfusion_SfChart_iOS_SFChartResetZoomInfo_Axis) – Instance of the axis whose range is changed because of this event. This event is triggered for each axis in the chart.
 * [`PreviousZoomFactor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartResetZoomInfo.html#Syncfusion_SfChart_iOS_SFChartResetZoomInfo_PreviousZoomFactor) – used to get the previous zoom factor.
 * [`PreviousZoomPosition`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartResetZoomInfo.html#Syncfusion_SfChart_iOS_SFChartResetZoomInfo_PreviousZoomPosition) – used to get the previous zoom position.


## Methods

Zooming and panning can be performed programmatically with the following methods:

### ZoomIn

The [`ZoomIn`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html#Syncfusion_SfChart_iOS_SFChartZoomPanBehavior_ZoomIn) method is used to increase the magnification of the plot area to view the data clearly.

{% highlight c# %}

SFChartZoomPanBehavior zoomPan = new SFChartZoomPanBehavior();

zoomPan.ZoomIn();

{% endhighlight %}

### ZoomOut 

The [`ZoomOut`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html#Syncfusion_SfChart_iOS_SFChartZoomPanBehavior_ZoomOut) method is used to decrease the magnification of the plot area to reset the default view.

{% highlight c# %}

SFChartZoomPanBehavior zoomPan = new SFChartZoomPanBehavior();

zoomPan.ZoomOut();

{% endhighlight %}

### Zoom

**Zoom(factor)**

The [`Zoom(factor)`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html) method is used to change the zoom level by using [`ZoomFactor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_ZoomFactor).

{% highlight c# %}

SFChartZoomPanBehavior zoomPan = new SFChartZoomPanBehavior();

zoomPan.Zoom(0.5f);

{% endhighlight %}

**Zoom(CGRect)**

The [`Zoom(CGRect)`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html#Syncfusion_SfChart_iOS_SFChartZoomPanBehavior_Zoom_CoreGraphics_CGRect_) method is used to zoom the chart for a given rectangle value.

{% highlight c# %}

SFChartZoomPanBehavior zoomPan = new SFChartZoomPanBehavior();

zoomPan.Zoom(new CGRect(10, 10, 200, 350));

{% endhighlight %}

**Zoom(chartAxis, zoomPosition, zoomFactor)**

The [`Zoom(chartAxis, zoomPosition, zoomFactor)`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html) method is used to change the zoom level by using [`ZoomPosition`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_ZoomPosition) and [`ZoomFactor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_ZoomFactor). Zoom position value specifies the starting point of zooming, and zoom factor value specifies the level of zooming.

{% highlight c# %}

SFChartZoomPanBehavior zoomPan = new SFChartZoomPanBehavior();

zoomPan.Zoom(axis, 0.5f, 0.5f);

{% endhighlight %}

**Zoom(chartAxis, start, end)**

The [`Zoom(chartAxis, start, end)`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html#Syncfusion_SfChart_iOS_SFChartZoomPanBehavior_Zoom_Syncfusion_SfChart_iOS_SFAxis_System_Object_System_Object_) method is used to zoom the given axis to given range.

{% highlight c# %}

SFChartZoomPanBehavior zoomPan = new SFChartZoomPanBehavior();

zoomPan.Zoom(axis, 20, 25);

{% endhighlight %}


### ZoomWithCumulativeScale(cumulativeLevel, origin, chartAxis)

The [`ZoomWithCumulativeScale`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html#Syncfusion_SfChart_iOS_SFChartZoomPanBehavior_ZoomWithCumulativeScale_System_Double_System_Double_Syncfusion_SfChart_iOS_SFAxis_) method is used to change the zoom level of given axis to the specified level and origin.

{% highlight c# %}

SFChartZoomPanBehavior zoomPan = new SFChartZoomPanBehavior();

zoomPan.ZoomWithCumulativeScale(0.5, 0.5, axis);

{% endhighlight %}

### Reset

The [`Reset`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html#Syncfusion_SfChart_iOS_SFChartZoomPanBehavior_Reset) method is used to return the plot area back to its original position after zooming. 

{% highlight c# %}

SFChartZoomPanBehavior zoomPan = new SFChartZoomPanBehavior();

zoomPan.Reset();

{% endhighlight %}
