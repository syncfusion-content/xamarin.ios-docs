---
layout : post
title : Transformation in Syncfusion SfImageEditor control in Xamarin.iOS
description : Learn how to perform transformations in Syncfusion Essential Studio Xamarin.iOS ImageEditor Control, its elements, and more.
platform : xamarin.ios
control : ImageEditor
documentation : ug
---

# Transformation in Xamarin.iOS ImageEditor

The image editor control is capable of performing the image transformations such as `rotation` and `flip`.

## Rotation

You can use the `Rotate` method of the image editor to rotate an image. For each rotation, image will be rotated to 90 degrees towards clockwise direction.

N> Angle cannot be specified in code to alter the rotation angle of an image.

{% tabs %}

{% highlight C# %}

editor.Rotate();

{% endhighlight %}

{% endtabs %}

## Flip

The image editor control is capable of showing the mirror image. The `Flip` method flips the image horizontally or vertically based on the `FlipDirection` specified as argument of the flip method.

N> The default flip direction is horizontal.

{% tabs %}

{% highlight C# %}

editor.Flip(FlipDirection.Horizontal);

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/flip.gif)