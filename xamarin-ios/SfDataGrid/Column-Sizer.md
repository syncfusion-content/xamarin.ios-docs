---
layout: post
title: Column Sizer | SfDataGrid | Xamarin.iOS | Syncfusion
description: What are all the different ColumnSizer and how it works in a SfDataGrid.
platform: xamarin.ios
control: SfDataGrid
documentation: ug
---

# Column Sizer

[SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) allows you to apply ColumnSizer for the GridColumns by setting the [SfDataGrid.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ColumnSizer.html) property. 

The following code example illustrates how to apply `ColumnSizer` in `SfDataGrid`.

{% highlight c# %}
dataGrid.ColumnSizer = ColumnSizer.None;  
{% endhighlight %}

`SfDataGrid` applies width for all the GridColumns in the [SfDataGrid.Columns](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~Columns.html) collection based on the [SfDataGrid.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ColumnSizer.html) property. Following are the lists of options available to set width of the Columns.

* None
* LastColumnFill
* Star
* Auto


## ColumnSizer.None

No Column sizing is applied when the [SfDataGrid.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ColumnSizer.html) is set to “None”. Columns are arranged in view based on the [SfDataGrid.DefaultColumnWidth](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~DefaultColumnWidth.html) property. This is the default value of the [SfDataGrid.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ColumnSizer.html) property.

{% highlight c# %}
dataGrid.ColumnSizer = ColumnSizer.None;  
{% endhighlight %}

![](SfDataGrid_images/ColumnSizer_img1.png)

## ColumnSizer.LastColumnFill

When the [SfDataGrid.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~ColumnSizer.html) is “LastColumnFill”, the column width of the GridColumns are adjusted with respect to [SfDataGrid.DefaultColumnWidth](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~DefaultColumnWidth.html) property. In case if the columns does not fill the entire view space, then the last column’s width fills the unoccupied space in the view.

{% highlight c# %}
dataGrid.ColumnSizer = ColumnSizer.LastColumnFill;  
{% endhighlight %}

![](SfDataGrid_images/ColumnSizer_img2.png)

## ColumnSizer.Star

When the [SfDataGrid.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~ColumnSizer.html) is “Star”, all the GridColumns are adjusted an equal column width to fit within the view. Setting ColumnSizer to “Star” will disable the HorizontalScrolling in `SfDataGrid`.

{% highlight c# %}
dataGrid.ColumnSizer = ColumnSizer.Star;  
{% endhighlight %}

![](SfDataGrid_images/ColumnSizer_img3.png)

## ColumnSizer.Auto

When the `SfDataGrid.ColumnSizer` is `Auto`, the width of the `GridColumns` are adjusted based on the header text or cell contents.

{% highlight c# %}
dataGrid.ColumnSizer = ColumnSizer.Auto;  
{% endhighlight %}

![](SfDataGrid_images/ColumnSizer_img4.png)

N> If any column is specified a width explicitly using the [GridColumn.Width](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~DefaultColumnWidth.html) property then that column is not considered ColumnSizing width and skipped while applying the ColumnSizer for grid columns.

## How to 

### Apply ColumnSizer for a particular column

You can apply ColumnSizer to individual columns using the [GridColumn.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~ColumnSizer.html) property. The `GridColumn.ColumnSizer` property takes the same values as the `SfDataGrid.ColumnSizer` and applies width to that particular column based on the ColumnSizer value. The following code example illustrates how to apply `ColumnSizer` for a particular column.

{% highlight c# %}
GridTextColumn textColumn = new GridTextColumn();
textColumn.MappingName = "CustomerID";
textColumn.HeaderText = "Full Name";
textColumn.ColumnSizer = ColumnSizer.Auto;  
{% endhighlight %}