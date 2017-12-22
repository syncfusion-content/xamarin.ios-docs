---
layout : post
title : ToolbarCustomization in Syncfusion SfImageEditor control in Xamarin.iOS
description : Learn how to customize toolbar in ImageEditor for Xamarin.iOS
platform : Xamarin.iOS
control : ImageEditor
documentation : ug
---

# ToolbarCustomization

You can customize color palette and visibility of the toolbar.

## To customize the ColorPalette

You can change default colors of the ColorPalette in toolbar.

{% tabs %}

{% highlight C# %}

    	ObservableCollection<UIColor> CustomColorPalette = new ObservableCollection<UIColor>()
	{
				UIColor.Yellow,
				UIColor.Blue,
				UIColor.DarkGray
	};

			editor.ColorPalette = CustomColorPalette;
{% endhighlight %}

{% endtabs %}


## To Hide/Show toolbar

To show or hide toolbar by setting toolbar IsVisible property to either true or false. By default toolbar IsVisible property is set to true.

{% tabs %}

{% highlight C# %}

     
     editor.ToolbarSettings.IsVisible = false;
     

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/toolbarvisibility.png)


## To Hide/Visible the toolbar Item

You can hide or show the toolbar items by specifying its icon name and set boolean value to false or true. 

 N> You can customize icon  by specifying its names  like  text, path, shapes, transform, rectangle, circle, arrow, flip, crop, rotate, reset, undo, Redo and save.

{% tabs %}

{% highlight C# %}

    editor.SetToolbarItemVisibility("text,save", false);

{% endhighlight %}

{% endtabs %}


![SfImageEditor](ImageEditor_images/toolbaritemvisibility.png)




