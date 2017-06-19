---
layout: post
title: Styles | SfDataGrid | Xamarin.iOS | Syncfusion
description: How to apply styles for the elements in a SfDataGrid.
platform: xamarin.ios
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

## Border Customization

* SfDatagrid allows you to customize the grid borders to vertical, horizontal or both based on requirements. you have override the `DataGridStyle.GetGridLinesVisibility`
method. 

{% highlight c# %}
//Apply custom style to SfDataGrid from code
dataGrid.GridStyle = new CustomStyle ();
{% endhighlight %}
 
{% highlight c# %}
//Custom Style class
public class CustomStyle : DataGridStyle
{
    public CustomStyle ()
    {
    }
    public virtual GridLinesVisibility GetGridLinesVisibility()
    {
        return GridLinesVisibility;
    }
}
{% endhighlight %}

Following are the lists of options available to customize the grid borders.

* Both
* Horizontal
* Vertical
* None

### Both

*  `GridLinesVisibility.Both` allows you to display the DataGrid with both Horizontal and Vertical borders.
{% highlight c# %}
public virtual GridLinesVisibility GetGridLinesVisibility()
{
    return GridLinesVisibility.Both;
}
{% endhighlight %}

### Horizontal

* `GridLinesVisibility.Horizontal` allows you to display the DataGrid with Horizontal border only
{% highlight c# %}
public virtual GridLinesVisibility GetGridLinesVisibility()
{
    return GridLinesVisibility.Horizontal;
}
{% endhighlight %}

### Vertical

* `GridLinesVisibility.Vertical` allows you to display the DataGrid with Vertical border only
{% highlight c# %}
public virtual GridLinesVisibility GetGridLinesVisibility()
{
    return GridLinesVisibility.Vertical;
}
{% endhighlight %}

### None

* `GridLinesVisibility.None` allows you to display the DataGrid without borders
{% highlight c# %}
public virtual GridLinesVisibility GetGridLinesVisibility()
{
    return GridLinesVisibility.None;
}
{% endhighlight %}

## How to

### Change the Sorting Icon in column headers

You can load any desired image as the sort icon in the `SfDataGrid` using the GetHeaderSortIndicatorDown and GetHeaderSortIndicatorUp overrides of the `DataGridStyle` class. The following code example illustrates how to change the SortIcon in `SfDataGrid`.

{% highlight c# %}

//Apply custom style to SfDataGrid from code
dataGrid.GridStyle = new Custom();

public class Custom : DataGridStyle
{

    public override UIImage GetHeaderSortIndicatorUp()
    {
        return UIImage.FromFile("SortDown.png");
    }

    public override UIImage GetHeaderSortIndicatorDown()
    {
        return UIImage.FromFile("SortUp.png");
    }

}
{% endhighlight %}

The following screenshots shows the final outcome of the above code
![](SfDataGrid_images/SortIconCustomization.png)

N> The image's BuildAction must be set to BundleResource so that we can access the image via its name.

### Change the color of the resizing indicator

You can change the color of the resizing indicator using the GetResizingIndicatorColor override of the `DataGridStyle` class. The following code example illustrates how to change the color of the ResizingIndicator in `SfDataGrid`. 

{% highlight c# %}

//Apply custom style to SfDataGrid from code
dataGrid.GridStyle = new Custom();

public class Custom : DataGridStyle
{
    public override UIColor GetResizingIndicatorColor()
    {
        return UIColor.Blue;
    }
}
{% endhighlight %}