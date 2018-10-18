---
layout : post
title : Custom view of Syncfusion SfImageEditor control in Xamarin.iOS
description : Learn how to add custom view in ImageEditor for Xamarin.iOS
platform : xamarin.ios
control : ImageEditor
documentation : ug
---

## CustomView

You can add any custom shapes or views to an image using the `AddCustomView` method in the image editor control. To add a custom view, specify the view and its desired `CustomViewSettings` as shown in the following code snippet.

{% highlight C# %}

            UIImageView customImage = new UIImageView();
            customImage.Frame = new CoreGraphics.CGRect(0, 0, 200, 200);
            customImage.Image = UIImage.FromBundle("CustomViewImage.png");
            editor.AddCustomView(customImage, new CustomViewSettings());

{% endhighlight %}

## CustomViewSettings

The CustomViewSettings is defined to set the values for `CanMaintainAspectRatio`, `Bounds` and `Angle`.

* The CanMaintainAspectRatio property is used to decide whether the aspect ratio value needs to be maintained when resizing the custom view.

* Bounds property is used to set the bounds of the custom view. Using this property, you can position the custom view wherever you want on the image. In percentage, the value should fall between 0 and 100.

* Angle property is used to set the angle of the custom view. Using this property, you can rotate the custom view at desired angle.

{% highlight C# %}

            CustomViewSettings customViewSettings = new CustomViewSettings()
            {
                CanMaintainAspectRatio = false,
                Bounds = new Rectangle(0, 0, 100, 100),
                Angle = 45
            };

{% endhighlight %}

![SfImageEditor](ImageEditor_images/CustomView.png)

## CustomView Rotation

You can rotate and resize the custom view by enabling the `RotatableElements` property of image editor. `ImageEditorElements` is an enum type with values Text, CustomView and None as shown in the following code snippet.

{% tabs %}

{% highlight C# %}

    editor.RotatableElements = ImageEditorElements.CustomView;

{% endhighlight %}

{% endtabs %}

N> The default value for RotatableElements is `None`.

You can rotate the custom view based on a particular angle using `Angle` property in `CustomViewSettings` as shown in the following code snippet. 

{% tabs %}

{% highlight C# %}

        imageEditor.AddCustomView(customImage, new CustomViewSettings(){Angle = 45});    

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/rotation.png)