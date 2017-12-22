---
layout : post
title : Zooming and Panning in Syncfusion SfImageEditor control in Xamarin.iOS
description : Learn how to perform Zooming and panning image in ImageEditor for Xamarin.iOS
platform : Xamarin.iOS
control : ImageEditor
documentation : ug
---

# Zooming

The image editor control provides support for zooming and panning.You can Zoom in and Zoom out image  in imageeditor control.

The following properties are related to the zooming feature of the imageeditor control:

* EnableZooming
* Maximum ZoomLevel

### EnableZooming

 You can Enable or Disable zooming by setting Enable Zooming to either true or false.

{% tabs %}

{% highlight C# %}

     editor.EnableZooming = true;

{% endhighlight %}

{% endtabs %}

### Maximum ZoomLevel

You can customize maximum zoom level  by setting value to Maximum ZoomLevel property in imageeditor control.

{% tabs %}

{% highlight C# %}

     editor.EnableZooming = true;
     editor.MaximumZoomLevel = 8;

{% endhighlight %}

{% endtabs %}

## Panning

Imageeditor control provides support for panning.Imageeditor allows to pan image with only two fingers to identify touch interaction between panning and Resizing or shifting shapes.

![SfImageEditor](ImageEditor_images/zoom.gif)


