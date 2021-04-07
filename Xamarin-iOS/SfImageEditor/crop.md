---
layout: post
title: Cropping Image in Syncfusion SfImageEditor control in Xamarin.iOS
description: Learn how to crop the image with various aspect ratios from toolbar and programmatically in syncfusion image editor control for Xamarin.iOS
platform: xamarin.ios
control: ImageEditor
documentation: ug
---

# Cropping image in various aspect ratios

You can crop the desired portion of an image using the cropping tool.

## Image cropping ratio

You can crop the image to various aspect ratios. The following cropping ratios are available in built-in toolbar:  "`Free`, `Original`, `Square`, `Circular`, `Ellipse`, `3:1`, `1:3`, `3:2`, `2:3`, `4:3`, `3:4`, `5:4`, `4:5`, `16:9`, `9:16`".

Cropping operation can be done in the following two ways:

* Enabling cropping and selecting the crop region visually.
* Entering the cropping area manually.

N> You can enable the cropping in the zoomed area and crop the specific position from the zoomed area.

### Handling the cropping tool

The [`ToggleCropping`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfImageEditor.iOS.SfImageEditor.html#Syncfusion_SfImageEditor_iOS_SfImageEditor_ToggleCropping) method in the image editor control allows users to enable or disable the cropping region placed over the image to visually choose the area for cropping.

* The following code shows cropping the image to any desired size.

{% highlight C# %}

// For free hand cropping.

editor.ToggleCropping();    

{% endhighlight %}

* The following code shows cropping an image based on its original width and height.

{% highlight C# %}

// For cropping a image with its original width and height.

editor.ToggleCropping(float.NaN,float.NaN);    

{% endhighlight %}

* The following code shows cropping an image based on specific ratio.

{% highlight C# %}

// For cropping the image with ratio, x value as 9, and y value as 17.

editor.ToggleCropping(9,17);    

{% endhighlight %} 

* To position the cropping window with custom location, pass the desired rectangle in [`ToggleCropping`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfImageEditor.iOS.SfImageEditor.html#Syncfusion_SfImageEditor_iOS_SfImageEditor_ToggleCropping) method. Each value in the rectangle should be in offset value(0 to 100).

{% highlight C# %}

Rectangle rect = new Rectangle(20,20,50,50);

editor.ToggleCropping(rect);    

{% endhighlight %} 

After the cropping area has been selected, the [`Crop`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfImageEditor.iOS.SfImageEditor.html#Syncfusion_SfImageEditor_iOS_SfImageEditor_Crop_System_Drawing_Rectangle_System_Boolean_) method is called, which in turn crops the selected region and displays the cropped image on the image editor.

{% highlight C# %}

editor.Crop();

{% endhighlight %}

### Circle cropping

An image can be cropped in circle or elliptical format, which could be perfect for using it as a profile picture.
Specify the [`ToggleCropping`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfImageEditor.iOS.SfImageEditor.html#Syncfusion_SfImageEditor_iOS_SfImageEditor_ToggleCropping_System_Drawing_RectangleF_System_Boolean_) parameter as shown in the below code sample.

N> When an empty rect is specified in the parameter, a rounded rect will be formed covering the entire image and it will be either in circle or ellipse shape based on the image bounds.

{% highlight C# %}

// To crop an image as a circular dimension.

            var editor = sender as SfImageEditor;
            var size = editor.ActualImageRenderedBounds;
            var minSize = Math.Min(size.Width, size.Height);
            var leftX = (size.Width - minSize) / 2;
            var topY = (size.Height - minSize) / 2;

            var x = (leftX * 100) / size.Width;
            var y = (topY * 100) / size.Height;
            var width = (minSize * 100) / size.Width;
            var height = (minSize * 100) / size.Height;

            editor.ToggleCropping(new RectangleF(x, y, width, height), true);

{% endhighlight %}

![SfImageEditor](ImageEditor_images/CircleCropPreview.png)

The following image show cases the circularly cropped image.

![SfImageEditor](ImageEditor_images/CircleCrop.png)

 The following code shows cropping an image in elliptical format.

{% highlight C# %}

// To crop an image as a elliptical dimension.

 editor.ToggleCropping(new RectangleF(), true);

{% endhighlight %}

### Entering the cropping area manually

To manually enter the cropping area without enabling the cropping functionality, use the overloaded [`Crop(Rectangle rect)`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfImageEditor.iOS.SfImageEditor.html#Syncfusion_SfImageEditor_iOS_SfImageEditor_Crop_System_Drawing_Rectangle_System_Boolean_) method. It can be done by defining a rectangle and passing it to the [`Crop(rect)`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfImageEditor.iOS.SfImageEditor.html#Syncfusion_SfImageEditor_iOS_SfImageEditor_Crop_System_Drawing_Rectangle_System_Boolean_) method.

{% tabs %}

{% highlight C# %}

editor.Crop(new Rectangle(100,100,150,200));

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/cropaspectiOS.png)

### Selecting the cropping ratio programmatically

Programmatically, you can select the desired cropping ratio from the various aspect ratios available in the built-in cropping toolbar by specifying the corresponding index of the toolbar item using the [`ToggleCropping`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfImageEditor.iOS.SfImageEditor.html#Syncfusion_SfImageEditor_iOS_SfImageEditor_ToggleCropping_System_Boolean_System_Int32_) method.

The following code sample will add the cropping preview on the image in square shape.

{% tabs %}

{% highlight C# %}

 editor.ToggleCropping(true, 2);

{% endhighlight %}

{% endtabs %}

## Tilt the image

You can tilt the image from -45 to +45 degree by using the [`Tilt()`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfImageEditor.iOS.SfImageEditor.html#Syncfusion_SfImageEditor_iOS_SfImageEditor_Tilt_System_Double_) method. When calling the tilt method, the image will be in preview state. You can zoom and pan the image in preview state. To apply this effect to the image, you can call the [`Crop()`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfImageEditor.iOS.SfImageEditor.html#Syncfusion_SfImageEditor_iOS_SfImageEditor_Crop_System_Drawing_Rectangle_System_Boolean_) method programmatically or can crop from footer toolbar cropping options.

N> Any action performed when the image is in Tilt preview state will reset the tilt effect of that image.

{% tabs %}

{% highlight C# %}

editor.Tilt(30);

{% endhighlight %}

{% endtabs %}

The following screenshot depicts the tilt preview state.

![Tilt preview](ImageEditor_images/TiltPreview.png)

After tilt preview, cropping can be performed using the available cropping options.

![Tilt crop](ImageEditor_images/TiltCrop.png)

