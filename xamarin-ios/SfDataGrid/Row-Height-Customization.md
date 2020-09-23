---
layout: post
title: Row Height Customization | SfDataGrid | Xamarin.iOS | Syncfusion
description: How to customize the height of rows in a SfDataGrid.
platform: xamarin.ios
control: SfDataGrid
documentation: ug
---

# Row Height Customization

SfDataGrid provides you the options to customize the header row height and the row height of all the grid rows or particular rows based on your requirements. The following sections illustrates you about how to achieve this customization in SfDataGrid.


## Customize HeaderRowHeight 

SfDataGrid allows you to customize the height of the header row by setting the [SfDataGrid.HeaderRowHeight](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_HeaderRowHeight) property. The default value of this property is 40. This property responds to runtime changes and hence you can customize it based on your requirement. Setting `SfDataGrid.HeaderRowHeight` to zero will collapse the header row in view.

The following code example illustrates how to customize header row height in SfDataGrid.

{% highlight c# %}

//Customizing header row height in SfDataGrid
dataGrid.HeaderRowHeight = 50;  
{% endhighlight %}

## GridRowSizingOptions

SfDataGrid allows you to customize the grid row's height with various customizing options while auto calculating the row height based on content using the `GridRowSizingOptions`.

### Calculate rows height based on certain columns

SfDataGrid allows you to calculate the RowHeight with exclude certain columns using `ExcludeColumns` property.

The following code example illustrates calculating the height of the grid rows based on certain columns.
{% highlight c# %}
 
 private void DataGrid_QueryRowHeight(object sender, QueryRowHeightEventArgs e)
{
    GridRowSizingOptions options = new GridRowSizingOptions();
    options.ExcludeColumns.Add("Description");
    options.ExcludeColumns.Add("CustomerID");
    if (e.RowIndex == 0)
    {
        e.Height = 50;
    }
    else
    {
        e.Height = dataGrid.GetRowHeight(e.RowIndex, options);
    }
    e.Handled = true;
}
{% endhighlight %}

### Calculate row height including hidden column's content

SfDataGrid allows you to calculate the row height based on content by including/excluding the hidden columns using the `CanIncludeHiddenColumns` property.
The following code example illustrates how to calculate Height include with hidden columns .
{% highlight c# %}
 
 private void DataGrid_QueryRowHeight(object sender, QueryRowHeightEventArgs e)
{
    GridRowSizingOptions options = new GridRowSizingOptions();
    options.CanIncludeHiddenColumns = true;
    if (e.RowIndex == 0)
    {
        e.Height = 50;
    }
    else
    {
        e.Height = dataGrid.GetRowHeight(e.RowIndex, options);
    }
    e.Handled = true;
}
{% endhighlight %}

## Customize RowHeight for all rows

SfDataGrid allows you to customize the height of the grid rows in the scrolling region by setting the [SfDataGrid.RowHeight](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_RowHeight) property. The default value of this property is 50. This property responds to runtime changes and hence you can customize it based on your requirement. Setting this property will change the height of all the rows in the body region with the common value. Setting `SfDataGrid.RowHeight` to zero will collapse all the rows in the grid.

The following code example illustrates how to customize header row height in SfDataGrid.

{% highlight c# %}
//Customizing row height in SfDataGrid
dataGrid.RowHeight = 60;
{% endhighlight %}


## Reset row height at runtime

SfDataGrid allows you to customize the height of a grid row on demand by handling the [SfDataGrid.QueryRowHeight](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.SfDataGrid.html) event. This event is raised for the grid rows whenever they come to view and hence you can customize the height of a particular row on demand by using the row index. Setting height to zero will collapse all the row in the grid. 

### QueryRowHeight

`SfDataGrid.QueryRowHeight` is the event that returns row heights on demand. This event receives two arguments namely the sender that handles the SfDataGrid and the [QueryRowHeightEventArgs](http://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.QueryRowHeightEventArgs.html). The `QueryRowHeightEventArgs` has the following properties.

* [RowIndex](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.QueryRowHeightEventArgs.html#Syncfusion_SfDataGrid_QueryRowHeightEventArgs_RowIndex): The property RowIndex helps you to identify a particular row in the grid.
* [Height](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.QueryRowHeightEventArgs.html#Syncfusion_SfDataGrid_QueryRowHeightEventArgs_Height): This property sets and returns the height for a grid row on demand. Default line size for the rows is 50.
* [Handled](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.GridHandledEventArgs.html#Syncfusion_SfDataGrid_GridHandledEventArgs_Handled): This property decides whether the specified height can be set to row or not. The default value is `false`. When this property is not set, the decided height is not set to the row.

The following code example illustrates how to hook the `SfDataGrid.QueryRowHeight` event and customize a row‘s height in SfDataGrid.

{% highlight c# %}
//Hooks QueryRowHeight event in SfDataGrid
dataGrid.QueryRowHeight += DataGrid_QueryRowHeight;  

//Event to set the row height on demand
void DataGrid_QueryRowHeight (object sender, QueryRowHeightEventArgs e)
{
    //Sets height of the fifth row
    if (e.RowIndex == 5) {
        e.Height = 100;
        e.Handled = true;
    }
} 
{% endhighlight %}

### QueryRowHeights Customization

SfDataGrid allows you to query a range of rows programmatically by using the [SfDataGrid.QueryingRowHeights](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.SfDataGrid.html) method based on the requirement. 

QueryRowHeights has two arguments start index and end index.
* Start index: It indicates, from which row index the `SfDataGrid.QueryRowHeight` event has to fire.
* End index: It indicates the end row index for the `SfDataGrid.QueryRowHeight` event to fire.

The following code illustrates how to customize the row height for a range of rows in SfDataGrid.

{% highlight c# %}

//Customizing the QueryingRowHeights in SfDataGrid
dataGrid.QueryingRowHeights(2,5);
//Its starts to query the rows from second row to the fifth row.
{% endhighlight %}


## Auto fit the grid rows based on content

SfDataGrid provides support for AutoRowHeight feature by which you can customize the row's height based on the content. This can be achieved by using the `SfDatagrid.QueryRowHeight` event and [SfDatagrid.GetRowHeight](http://help.syncfusion.com/cr/xamarin-ios) method. `SfDatagrid.QueryRowHeight` event returns the row height on demand and `SfDatagrid.GetRowHeight` method returns the height of the row based on the content.

N> Row drag and drop operation is not supported while customizing the row height based on content.

The following code example illustrates how to hook the `SfDatagrid.QueryRowHeight` event and auto fit a row's height based on the content in SfDataGrid.

{% highlight c# %}
//Hooks QueryRowHeight event in SfDataGrid to set the row height on demand
dataGrid.QueryRowHeight += DataGrid_QueryRowHeight;  

private void DataGrid_QueryRowHeight (object sender, QueryRowHeightEventArgs e)
{
    if (e.RowIndex != 0) {
        //Calculates and sets height of the row based on its content 
        e.Height = dataGrid.GetRowHeight(e.RowIndex);
        e.Handled = true;
    }
} 
{% endhighlight %}

![](SfDataGrid_images/AutoRowHeight_iOS.png)

## Customize caption summary row height

SfDataGrid allows you to customize the height of the `CaptionSummaryRow` by setting the height of the caption rows in the `SfDataGrid.QueryRowHeight` event. By default the `CaptionSummaryRow` renders with the height of the [SfDataGrid.RowHeight](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_RowHeight) which is `50`

The following code example illustrates how to customize CaptionSummaryRow height in SfDataGrid.

{% highlight c# %}
//Hooks QueryRowHeight event in SfDataGrid to set the CaptionSummaryRow height on demand
dataGrid.QueryRowHeight += DataGrid_QueryRowHeight;

private void DataGrid_QueryRowHeight(object sender, QueryRowHeightEventArgs e)
{
    if (dataGrid.IsCaptionSummaryRow(e.RowIndex))
    {
        e.Height = 70;
         e.Handled = true;
    }
}
{% endhighlight %}

![](SfDataGrid_images/CaptionSummaryRowHeight.png)


## customize table summary row height

SfDataGrid allows you to customize the height of the `TableSummaryRow` by setting the height of the table summary rows in the `SfDataGrid.QueryRowHeight` event. By default the `TableSummaryRow` renders with the height of the [SfDataGrid.RowHeight](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_RowHeight) which is `50`.

The following code example illustrates how to customize header row height in SfDataGrid.

{% highlight c# %}
//Hooks QueryRowHeight event in SfDataGrid to set the CaptionSummaryRow height on demand
dataGrid.QueryRowHeight += DataGrid_QueryRowHeight;

private void DataGrid_QueryRowHeight(object sender, QueryRowHeightEventArgs e)
{
    if (dataGrid.IsTableSummaryRow(e.RowIndex))
    {
        e.Height = 70;
        e.Handled = true;
    }
}
{% endhighlight %}

![](SfDataGrid_images/TableSummaryRowHeight.png)

## How to ?

### Optimize performance when using QueryRowHeight event

By default the `SfDataGrid.QueryRowHeight` event will be fired each time a row comes into the view. If you want to prevent the same row from being queried again, you can check if the `Height` property in the `QueryRowHeightEventArgs` is not equal to the `SfDataGrid.RowHeight` property which prevents from the same row being queried again. The following code example illustrates how to enhance the performance by preventing the the same row from being queried again. 

{% highlight c# %}
//Hooks QueryRowHeight event in SfDataGrid to set the row height on demand
dataGrid.QueryRowHeight += DataGrid_QueryRowHeight;

private void DataGrid_QueryRowHeight (object sender, QueryRowHeightEventArgs e)
{
    // Code to skip querying of a row if already queried
    if (e.Height != dataGrid.RowHeight)
        return;
    if (e.RowIndex != 0) 
    {
        //Calculates and sets the height of the row based on its content.
        e.Height = dataGrid.GetRowHeight(e.RowIndex);
        e.Handled = true;
    }
} 
{% endhighlight %}
