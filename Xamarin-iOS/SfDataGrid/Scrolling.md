---
layout: post
title: Scrolling | SfDataGrid | Xamarin | Syncfusion
description: How to scroll the SfDataGrid.
platform: xamarin.iOS
control: SfDataGrid
documentation: ug
---

# Scrolling 

## ScrollingMode

SfDataGrid provides three types of scrolling mode which can be customized using the [SfDataGrid.ScrollingMode](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ScrollingMode.html) property. By default, the SfDataGrid will scroll its content based on pixel values.

* PixelLine
* Line
* Pixel

### PixelLine

`ScrollingMode.PixelLine`, will allow to scroll its contents like an excel sheet. i.e., whenever a row or a column is clipped on the top, the particular row or column will be auto scrolled to display fully in view.

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.PixelLine; 
{% endhighlight %}

### Line

`ScrollingMode.Line`, will allow to scroll its contents based on lines. i.e., the view will be updated only when the offset values reaches the origin of a row or column in the bound collection

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.Line; 
{% endhighlight %}

### Pixel

`ScrollingMode.Pixel`, will allow to scroll its contents based on pixel values. i.e., the view will be updated each pixel change of the offsets and rows or columns will appear clipped when offset exceeds the origin of the row or column.

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.Pixel; 
{% endhighlight %}

## Programmatic Scrolling

SfDataGrid allow you to scroll to particular Row and Column index from programmatically

### Scroll to Row and Column Index

* You can scroll programmatically to particular Row and Column using `SfDataGrid.ScrollToRowColumnIndex` method by passing row and column index.

{% highlight C# %}

dataGrid.ScrollToRowColumnIndex(int rowIndex, int columnIndex);

{% endhighlight %}

### Scroll to Row Index

* You can scroll programmatically to particular Row `SfDataGrid.ScrollToRowIndex` method by passing row index.

{% highlight C# %}

dataGrid.ScrollToRowIndex(int rowIndex);

{% endhighlight %}

### Scroll to Column Index

* You can scroll programmatically to particular Column `SfDataGrid.ScrollToColumnIndex` method by passing column index.

{% highlight C# %}

dataGrid.ScrollToColumnIndex(int columnIndex);

{% endhighlight %}




