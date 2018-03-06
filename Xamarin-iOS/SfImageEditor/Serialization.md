---
layout : post
title : serialization in Syncfusion SfImageEditor control in Xamarin.iOS
description : Learn how to serialize and deserialize edited shapes  in ImageEditor for Xamarin.iOS
platform : Xamarin.iOS
control : ImageEditor
documentation : ug
---

# Serialization And Deserialization
 ImageEditor provides support to serialize and deserialize the shapes(Circle, Arrow, Rectangle), free hand drawing, Text and Toolbar settings. Save the current state of the Image Editor and Load it back when its needed.

## Serialization
  SaveEdits() method used to serialize the current edits of shapes. Serialized object will be return in the form of JSON stream.

{% tabs %}

{% highlight C# %}
    
	 SfImageEditor editor;
        public override void ViewDidLoad()
        {
           
            editor = new SfImageEditor();
            UIButton saveEdits = new UIButton();
            saveEdits.Frame = new CoreGraphics.CGRect(0, 10, View.Frame.Width, 100);
            saveEdits.SetTitle("Serialize",UIControlState.Normal);
            saveEdits.SetTitleColor(UIColor.Black,UIControlState.Normal);
            saveEdits.TouchUpInside+= SaveEdits_TouchUpInside;
            editor.Frame = new CoreGraphics.CGRect(0, 110, View.Frame.Width, View.Frame.Height-100);
            this.Add(editor);
            this.Add(saveEdits);
            base.ViewDidLoad();
           
        }

        void SaveEdits_TouchUpInside(object sender, EventArgs e)
        {
            Stream stream = editor.SaveEdits();
        }
	
{% endhighlight %}

{% endtabs %}

   you can save stream into .txt format file. if you saved as .txt format file to deserialize the shapes then set as Embedded resource in project.

   Please find sample text file shown below

   [Chart.txt](http://www.syncfusion.com/downloads/support/directtrac/general/txt/Chart677841499.txt)
       


## Deserialization
   LoadEdits() method used to deserialize the shapes.

{% tabs %}

{% highlight C# %}
      
      SfImageEditor editor = new SfImageEditor();
            editor.Frame = View.Frame;
            Stream stream = this.GetType().GetTypeInfo().Assembly.GetManifestResourceStream("namespacename.Resources.Chart.txt");
            if (stream != null)
                editor.LoadEdits(stream);
            this.Add(editor);
	  

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/Serialization.png)





