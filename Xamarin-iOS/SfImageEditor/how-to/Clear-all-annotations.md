---
layout: post
title: How to clear all annotations programmatically | Syncfusion
description: Learn here about how to clear all the annotations (Text, Shapes, Paths, Custom views) alone added in the image editor.
platform: xamarin.ios
control: SfImageEditor
documentation : ug
---

# Clear all annotations (Text, Shapes, Paths, etc) from Image Editor

By invoking the [`ClearAnnotations`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfImageEditor.iOS.SfImageEditor.html#Syncfusion_SfImageEditor_iOS_SfImageEditor_ClearAnnotations) method of SfImageEditor, you can clear all the annotations (Text, Shapes, Path, and CustomView) added in the image editor without resetting the other edits (Rotation, Flip, Crop, Effects, etc).

The following code sample demonstrates this.

{% highlight c# %}

public partial class ViewController : UIViewController
{
    SfImageEditor imageEditor;
    ...
    public override void ViewDidLoad()
    {
        base.ViewDidLoad();
        imageEditor = new SfImageEditor();
        imageEditor.Frame = new CGRect(0, 50, this.View.Frame.Width, this.View.Frame.Height - 100);
        imageEditor.Image = UIImage.FromBundle("EditorBuilding1.png");
        View.AddSubview(imageEditor);

        UIButton ClearAnnotations = new UIButton();
        ClearAnnotations.SetTitle("Clear Annotations", UIControlState.Normal);
        ClearAnnotations.BackgroundColor = UIColor.LightGray;
        ClearAnnotations.TouchDown += ClearAnnotations_TouchDown;
        ClearAnnotations.Frame = new CGRect(0, this.View.Frame.Height - 50, this.View.Frame.Width, 50);
        View.AddSubview(ClearAnnotations);
    }

    private void ClearAnnotations_TouchDown(object sender, EventArgs e)
    {
        imageEditor.ClearAnnotations();
    }
}

{% endhighlight %}

![ClearAnnotations support in Xamarin.iOS ImageEditor](images/ClearAnnotations.gif)