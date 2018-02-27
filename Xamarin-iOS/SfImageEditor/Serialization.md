---
layout : post
title : serialization in Syncfusion SfImageEditor control in Xamarin.iOS
description : Learn how to serialize and deserialize edited shapes  in ImageEditor for Xamarin.iOS
platform : Xamarin.iOS
control : ImageEditor
documentation : ug
---

# Serialization And Deserialization
 ImageEditor provides support to serialize and deserialize the shapes(Circle,Arrow,Rectangle), free hand drawing,Text and Toolbarsettings. Save the current state of the Image Editor and Load it back when its needed.

## Serialization
  To serialize the shapes like circle,arrow,rectangle,text ,freehand drawing and toolbarsettings by calling SaveEdits() method.Serialized object will be return in the form of Json stream.

{% tabs %}

{% highlight C# %}
    
	 SfImageEditor editor = new SfImageEditor();
            editor.Frame = View.Frame;
			Stream stream=editor.SaveEdits();
			this.Add(editor);
	
{% endhighlight %}

{% endtabs %}

   convert the stream into string and save as .txt format file and set as Embedded  resource in Xamarin.iOS.
   Text file like this
   [Chart.txt](http://www.syncfusion.com/downloads/support/directtrac/general/txt/Chart677841499.txt)
       


## Deserialization
   To deserialize serialized objects by calling LoadEdits(stream) method .Deserialize the object by using loaded Json stream.

{% tabs %}

{% highlight C# %}
      
      SfImageEditor editor = new SfImageEditor();
            editor.Frame = View.Frame;
            Stream stream = this.GetType().GetTypeInfo().Assembly.GetManifestResourceStream("serialization.Resources.Chart.txt");
            if (stream != null)
                editor.LoadEdits(stream);
            this.Add(editor);
	  

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/Serialization.png)





