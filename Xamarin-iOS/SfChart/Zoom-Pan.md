---
layout: post
title: Zooming and Panning | SFChart | Xamarin.iOS | Syncfusion
description: How to add ZoomPan behavior in SFChart
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Zooming and Panning

## Enable Zooming

Chart supports zooming to view the data clearly. To enable this feature, you need to add an instance of `SFChartZoomPanBehavior` to the `Behaviors` collection using the `AddChartBehavior` method of `SFChart`.

Following properties are used to configure the zooming feature,

* `EnableZooming` – used to enable/disable the pinch zooming. Default value is true 
* `EnableDoubleTap` – when you enable this property, you can double tap on the chart to reset it to the original size or zoom in by one level
* `EnableSelectionZooming` – when this property is set to true, you can double tap and drag to select a range on the chart to be zoomed in
* `EnablePanning` – used to enable/disable the panning. Default value is true

Following code snippet illustrates how to enable zooming.


{% highlight c# %}

SFChartZoomPanBehavior zoomPan = new SFChartZoomPanBehavior ();

chart.AddChartBehavior (zoomPan); 


{% endhighlight %}


Following code snippet illustrates how to enable the box selection zooming,

{% highlight c# %}

SFChartZoomPanBehavior zoomPan = new SFChartZoomPanBehavior();
zoomPan.EnableSelectionZooming = true;
chart.AddChartBehavior (zoomPan); 

{% endhighlight %}


Following screenshot shows the box selection on chart area,

![](zoompan_images/zoompan_img1.png)


Following screenshot shows the zoomed area,

![](zoompan_images/zoompan_img2.png)

## Zoom Mode

The `ZoomMode` property specifies whether chart should be allowed to scale along horizontal axis or vertical axis or along both axis. The default value of `ZoomMode` is `SFChartZoomMode.XY` (both axis).

Following code example illustrates how to restrict the chart to be zoomed only along horizontal axis,

{% highlight c# %}

SFChartZoomPanBehavior zoomPan = new SFChartZoomPanBehavior();

zoomPan.ZoomMode               = SFChartZoomMode.X;

chart.AddChartBehavior(zoomPan); 

{% endhighlight %}

![](zoompan_images/zoompan_img3.png)

## Delegates


We need to implement delegate to deal with the user interactions in chart for zooming and panning. In order to do this,you need to adopt the `SFChartDelegate` protocol through the class extension as shown below.


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

This delegate is called when the axis object has started a zoom operation and it returns the following values.

* `SFChartZoomingInfo` – used to get the zooming state.

**DidZoom**

This delegate is called when the axis object has finished a zoom operation and it returns the following values.

* `SFChartZoomInfo` – used to get the zoomed state.

**WillPan**

This delegate is called when the axis object has started a scroll operation and it returns the following values.

* `SFChartPanningInfo` – used to get the scrolled state.

**DidPan**

This delegate is called when the axis object has finished a scroll operation and it returns the following values.

* `SFChartPanInfo` – used to get the zoomed state.

**WillSelectionZoom**

This delegate is called when the axis object has started a selection zoom operation and it returns the following values.

* `SFChartSelectionZoomingInfo` – used to get the selection zoom state.

**DidSelectionZoom**

This delegate is called when the axis object has finished a selection zoom operation and it returns the following values.

* `SFChartSelectionZoomInfo` – used to get the selection zoom state.

**DidResetZoom**

This delegate is called when the axis object has reset the zoom level and it returns the following values.

* `SFChartResetZoomInfo` – used to get the reset object.
