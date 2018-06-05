---
layout : post
title : ToolbarCustomization in Syncfusion SfImageEditor control in Xamarin.iOS
description : Learn how to customize toolbar in ImageEditor for Xamarin.iOS
platform : xamarin.ios
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

## ToolbarHeight Customization

You can customize `height of the toolbar` and also toolbar items `icon` and `text`.

### Customize Toolbar Height 

SfImageEditor control supports to customize the default height of `Header`, `Footer` and `Sub item` Toolbar by using following properties,
1.	HeaderToolbarHeight
2.	FooterToolbarHeight 
3.	SubItemToolbarHeight

Header toolbar items will be resize based on the header toolbar height. To change Height of the Header Toolbar by using property HeaderToolbarHeight as like below,

{% tabs %}

{% highlight C# %}

    editor.ToolbarSettings.HeaderToolbarHeight = 70;

{% endhighlight %}

{% endtabs %}

Footer toolbar items will be resized based on the footer toolbar height. To change Height of the Footer Toolbar by using property FooterToolbarHeight as like below,

{% tabs %}

{% highlight C# %}

    editor.ToolbarSettings.FooterToolbarHeight = 70;

{% endhighlight %}

{% endtabs %}

Sub toolbar items will be resized based on the SubItem toolbar height. To change Height of the sub toolbar by using property SubItemToolbarHeight as like below,

{% tabs %}

{% highlight C# %}

    editor.ToolbarSettings.SubItemToolbarHeight = 70;

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/ToolbarHeight.png)

### Individual Toolbar Item Height Customization

To arrange toolbar items aspect fit based on the toolbar height by using following properties  

1.  TextHeight
2.  IconHeight

•	To change the toolbar item Text and Icon height as like below,

{% tabs %}

{% highlight C# %}

    editor.ToolbarSettings.ToolbarItems.Add(new FooterToolbarItem() {Icon=UIImage.FromBundle("share.png"),Text="Share",IconHeight=40,TextHeight=20});

{% endhighlight %}

{% endtabs %}




