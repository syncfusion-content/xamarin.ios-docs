---
layout : post
title : Zooming and Panning in Syncfusion SfImageEditor control in Xamarin.iOS
description : Learn how to perform Zooming and panning image in ImageEditor for Xamarin.iOS
platform : xamarin.ios
control : ImageEditor
documentation : ug
---

# Zooming

The image editor control provides support to zoom and pan actions over an image.

The following properties are used for zooming feature of the image editor control:

* EnableZooming
* Maximum ZoomLevel
* PanningMode

## Enable zooming

You can enable or disable the zooming functionality by setting the `EnableZooming` value to true or false. By default, the `EnableZooming` value is set to true.

{% tabs %}

{% highlight C# %}

     editor.EnableZooming = true;

{% endhighlight %}

{% endtabs %}

## Maximum ZoomLevel

You can customize maximum zoom level  by setting value to `MaximumZoomLevel` property in image editor control.

{% tabs %}

{% highlight C# %}

     editor.EnableZooming = true;
     editor.MaximumZoomLevel = 8;

{% endhighlight %}

{% endtabs %}

## Panning mode

The image editor control provides support for panning and allows to pan the image with two fingers or single finger by setting the `PanningMode`.

The following properties are used for panning:

* `SingleFinger`: Zooms or pans the image with single finger, but shapes and text selection cannot be performed with this mode.
* `TwoFinger`: Zooms or pans the image with two finger. The shapes and text selection can be performed with this mode.

By default, the `PanningMode` value is set to `TwoFinger`.

![SfImageEditor](ImageEditor_images/zoom.gif)