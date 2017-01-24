---
layout: post
title: Grouping | SfDataGrid | Xamarin.iOS | Syncfusion
description: How to use different events exposed in SfDataGrid.
platform: xamarin.ios
control: SfDataGrid
documentation: UG
---

# Grid Events

## GridTapped event

The event will be triggered whenever you tap the SfDataGrid with [GridTappedEventsArgs](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridTappedEventsArgs.html) that contains following properties.

* **RowIndex** - Gets the row index of the row on which you tapped
* **ColumnIndex** - Gets the column index of the column on which you tapped
* **RowData** - Gets the row data of the row on which you tapped

The following code illustrates how to hook the `GridTapped` event and get the row and column details based on where you tapped on SfDataGrid. 

{% highlight c# %}
dataGrid.GridTapped += DataGrid_GridTapped;

private void DataGrid_GridTapped(object sender, GridTappedEventsArgs e)
{
    var rowIndex = e.RowColumnindex.RowIndex;
    var rowData = e.RowData;
    var columnIndex = e.RowColumnindex.ColumnIndex;
}
{% endhighlight %}

## GridDoubleTapped event

The event will be triggered whenever you double tap the SfDataGrid with [GridDoubleTappedEventsArgs](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridDoubleTappedEventsArgs.html) that contains the following properties. 

* **RowIndex** - Gets the row index of the row on which you double tapped
* **ColumnIndex** - Gets the column index of the column on which you double tapped
* **RowData** - Gets the row data of the row on which you double tapped

The following code illustrates how to hook the `GridDoubleTapped` event and get the row and column details based on where you double tapped on SfDataGrid.  

{% highlight c# %}
dataGrid.GridDoubleTapped += DataGrid_GridDoubleTapped;

private void DataGrid_GridDoubleTapped(object sender, GridDoubleTappedEventsArgs e)
{
    var rowIndex = e.RowColumnIndex.RowIndex;
    var rowData = e.RowData;
    var columnIndex = e.RowColumnIndex.ColumnIndex;
}
{% endhighlight %}

## GridLongPressed event

The event will be triggered whenever you long press the SfDataGrid with [GridLongPressedEventsArgs](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridLongPressedEventsArgs.html) that contains the following properties.

* **RowIndex** - Gets the row index of the row on which you long pressed
* **ColumnIndex** - Gets the column index of the column on which you long pressed
* **RowData** - Gets the row data of the row on which you long pressed

The following code illustrates how to hook the `GridLongPressed` event and get the row and column details based on where you long pressed on SfDataGrid. 

{% highlight c# %}
dataGrid.GridLongPressed += DataGrid_GridLongPressed;

private void DataGrid_GridLongPressed(object sender, GridLongPressedEventsArgs e)
{
    var rowIndex = e.RowColumnindex.RowIndex;
    var rowData = e.RowData;
    var columnIndex = e.RowColumnindex.ColumnIndex;
}
{% endhighlight %}

## GridViewCreated event

The event will be triggered once the [SfDataGrid.View](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~View.html) is created. You can give any operation in this event if it needs to happen once the `SfDataGrid.View` is created by handling [GridViewCreatedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridViewCreatedEventArgs.html).

The following code illustrates how to hook the `GridViewCreated` event and how to set alternate row colors in SfDataGrid.

{% highlight c# %}
dataGrid.GridViewCreated += DataGrid_GridViewCreated;

private void DataGrid_GridViewCreated(object sender, GridViewCreatedEventArgs e)
{
    (sender as SfDataGrid).GridStyle = new CustomGridStyle();   
}

internal class CustomGridStyle : DataGridStyle
{
    public override UIColor GetAlternatingRowBackgroundColor()
    {
        return UIColor.Purple;
    }
}
{% endhighlight %}

## GridLoaded event

The event will be triggered once the components in the SfDataGrid are initialized and rendered. You can give any operation in this event if it needs to happen once the grid is loaded by handling [GridLoadedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridLoadedEventArgs.html).

The following code illustrates how to hook the `GridLoaded` event and how to show the `UIActivityIndicatorView` until the grid comes to view.

{% highlight c# %}
dataGrid.GridLoaded += DataGrid_GridLoaded;

private void DataGrid_GridLoaded(object sender, GridLoadedEventArgs e)
{
    UIActivityIndicatorView indicator = new UIActivityIndicatorView();
    this.View.AddSubview(indicator);
    indicator.Frame = new CoreGraphics.CGRect(0,0,this.View.Frame.Width, this.View.Frame.Height);
    indicator.StartAnimating();
    await Task.Delay(2000);
    indicator.StopAnimating();      
}
{% endhighlight %}
