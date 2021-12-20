---
layout: post
title: How to select annotations programmatically | Syncfusion
description: Learn here about how to select the annotations (Text, Shapes, Paths, Custom views) added in the image editor programmatically.
platform: xamarin.ios
control: SfImageEditor
documentation: ug
---

# Select annotations programmatically in Image Editor (SfImageEditor)

In ImageEditor, the Unique ID is generated for all annotations (Text, Shapes, Paths, and CustomViews) when they are added to the image editor and you can get this Unique ID from the ItemsSelected event arguments or from the serialized JSON. By passing this Unique ID to the [`SelectShape`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfImageEditor.iOS.SfImageEditor.html#Syncfusion_SfImageEditor_iOS_SfImageEditor_SelectShape_System_Int32_) method of SfImageEditor, you can select the particular annotation programmatically.

The following code sample demonstrates this.

{% highlight c# %}

public partial class ViewController : UIViewController
{
    SfImageEditor imageEditor;
    UITextField UniqueID;
    ...
    public override void ViewDidLoad()
    {
        base.ViewDidLoad();
        imageEditor = new SfImageEditor();
        imageEditor.Frame = new CGRect(0, 50, this.View.Frame.Width, this.View.Frame.Height - 150);
        imageEditor.Image = UIImage.FromBundle("EditorBuilding1.png");
        imageEditor.ItemSelected += ImageEditor_ItemSelected;
        View.AddSubview(imageEditor);
        
        UniqueID = new UITextField();
        UniqueID.KeyboardType = UIKeyboardType.NumberPad;
        UniqueID.Frame = new CGRect(0, this.View.Frame.Height - 100, this.View.Frame.Width, 50);
        View.AddSubview(UniqueID);

        UIButton SelectShape = new UIButton();
        SelectShape.SetTitle("Select Shape", UIControlState.Normal);
        SelectShape.BackgroundColor = UIColor.LightGray;
        SelectShape.TouchDown += SelectShape_TouchDown;
        SelectShape.Frame = new CGRect(0, this.View.Frame.Height - 50, this.View.Frame.Width, 50);
        View.AddSubview(SelectShape);
    }

    private void ImageEditor_ItemSelected(object sender, ItemSelectedEventArgs e)
    {
        int uniqueID;
        PenSettings penSettings = e.Settings as PenSettings;
        TextSettings textSettings = e.Settings as TextSettings;
        CustomViewSettings customViewSettings = e.Settings as CustomViewSettings;
        if (penSettings != null)
        {
            uniqueID = penSettings.ShapeID;
        }
        else if (textSettings != null)
        {
            uniqueID = textSettings.ShapeID;
        }
        else
        {
            uniqueID = customViewSettings.ShapeID;
        }
    }

    private void SelectShape_TouchDown(object sender, EventArgs e)
    {
        int shapeId;
        if (int.TryParse(this.UniqueID.Text, out shapeId))
        {
            this.imageEditor.SelectShape(shapeId);
        }
    }
    
    public override void DidReceiveMemoryWarning()
    {
        base.DidReceiveMemoryWarning();
        // Release any cached data, images, etc that aren't in use.
    }
}

{% endhighlight %}

![Shape selection support in Xamarin.iOS ImageEditor](images/UniqueID.gif)