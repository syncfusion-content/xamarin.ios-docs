---
layout: post
title: Styles | SfDataGrid | Xamarin | Syncfusion
description: How to apply styles for the elements in a SfDataGrid.
platform: xamarin.iOS
control: SfDataGrid
documentation: UG
---

# Styles

SfDataGrid allows you to apply style to all of its elements by writing a Style class overriding from `DataGridStyle` and assigning it to the [SfDataGrid.GridStyle](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~GridStyle.html) property.
  
The following example explains you how to apply custom style to SfDataGrid.

{% highlight c# %}
//Apply custom style to SfDataGrid from code
dataGrid.GridStyle = new Dark ();
{% endhighlight %}

{% highlight c# %}
//Custom style class
public class Dark : DataGridStyle
{
    public Dark ()
    {
    }

    public override Color GetHeaderBackgroundColor()
    {
        return Color.FromRgb (15, 15, 15);
    }

    public override Color GetHeaderForegroundColor()
    {
        return Color.FromRgb (255, 255, 255);
    }

    public override Color GetRecordBackgroundColor ()
    {
        return Color.FromRgb (43, 43, 43);
    }

    public override Color GetRecordForegroundColor ()
    {
        return Color.FromRgb (255, 255, 255);
    }

    public override Color GetSelectionBackgroundColor ()
    {
        return Color.FromRgb (42, 159, 214);
    }

    public override Color GetSelectionForegroundColor ()
    {
        return Color.FromRgb (255, 255, 255);
    }

    public override Color GetCaptionSummaryRowBackgroundColor ()
    {
        return Color.FromRgb (02, 02, 02);
    }

    public override Color GetCaptionSummaryRowForeGroundColor ()
    {
        return Color.FromRgb (255, 255, 255);
    }

    public override Color GetBordercolor ()
    {
        return Color.FromRgb (81, 83, 82);
    }

    public override Color GetLoadMoreViewBackgroundColor ()
    {
        return Color.FromRgb(242, 242, 242);
    }

    public override Color GetLoadMoreViewForegroundColor ()
    {
        return Color.FromRgb(34, 31, 31);
    }
    
    public override Color GetAlternatingRowBackgroundColor()
    {
      return UIColor.Cyan;
    }
} 
{% endhighlight %}

The following picture shows the grid loaded in different styles.

![](SfDataGrid_images/Styles.png)
![](SfDataGrid_images/AlternatingStyle1.png)