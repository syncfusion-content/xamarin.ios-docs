---
layout : post
title : serialization in Syncfusion SfImageEditor control in Xamarin.iOS
description : Learn how to serialize and deserialize edited shapes  in ImageEditor for Xamarin.iOS
platform : xamarin.ios
control : ImageEditor
documentation : ug
---

# Serialization and Deserialization

The image editor control provides support to serialize and deserialize the shapes (circle, arrow, and rectangle), free hand drawing, text and toolbar settings. You can save the current state of the image editor and load it back when it is needed.

## Serialization

The SaveEdits() method is used to serialize the current edits of shapes. The serialized object will be returned in the form of JSON stream.

{% tabs %}

{% highlight C# %}
    
        public override void ViewDidLoad()
        {
            editor = new SfImageEditor();
            UIButton saveEdits = new UIButton();
            saveEdits.Frame = new CoreGraphics.CGRect(0, 10, View.Frame.Width, 100);
            saveEdits.SetTitle("Serialize", UIControlState.Normal);
            saveEdits.SetTitleColor(UIColor.Black, UIControlState.Normal);
            saveEdits.TouchUpInside += SaveEdits_TouchUpInside;
            editor.Frame = new CoreGraphics.CGRect(0, 110, View.Frame.Width, View.Frame.Height - 100);
            this.Add(editor);
            this.Add(saveEdits);
            base.ViewDidLoad();
        }

        private void SaveEdits_TouchUpInside(object sender, EventArgs e)
        {
            Stream stream = editor.SaveEdits();
        }
	
{% endhighlight %}

{% endtabs %}

you can save stream into .txt format file. if you saved as .txt format file to deserialize the shapes then set as `BundleResource` in project.

Sample text file: [Chart.txt](http://www.syncfusion.com/downloads/support/directtrac/general/txt/Chart677841499.txt)
       
## Deserialization

LoadEdits() method used to deserialize the shapes.

{% tabs %}

{% highlight C# %}
      
            Stream stream = this.GetType().GetTypeInfo().Assembly.GetManifestResourceStream("namespace_name.Resources.Chart.txt");
            if (stream != null)
                editor.LoadEdits(stream);
            this.Add(editor);

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/Serialization.png)