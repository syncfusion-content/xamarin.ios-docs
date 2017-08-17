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

SfDataGrid allows you to customize the height of the header row by setting the [SfDataGrid.HeaderRowHeight](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~HeaderRowHeight.html) property. The default value of this property is 40. This property responds to runtime changes and hence you can customize it based on your requirement. Setting `SfDataGrid.HeaderRowHeight` to zero will collapse the header row in view.

The following code example illustrates how to customize header row height in SfDataGrid.

{% highlight c# %}

//Customizing header row height in SfDataGrid
dataGrid.HeaderRowHeight = 50;  
{% endhighlight %}


## Customize RowHeight for all rows

SfDataGrid allows you to customize the height of the grid rows in the scrolling region by setting the [SfDataGrid.RowHeight](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~RowHeight.html) property. The default value of this property is 50. This property responds to runtime changes and hence you can customize it based on your requirement. Setting this property will change the height of all the rows in the body region with the common value. Setting `SfDataGrid.RowHeight` to zero will collapse all the rows in the grid.

The following code example illustrates how to customize header row height in SfDataGrid.

{% highlight c# %}
//Customizing row height in SfDataGrid
dataGrid.RowHeight = 60;
{% endhighlight %}


## Customize RowHeight of a particular row on demand

SfDataGrid allows you to customize the height of a grid row on demand by handling the [SfDataGrid.QueryRowHeight](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~QueryRowHeight_EV.html) event. This event is raised for the grid rows whenever they come to view and hence you can customize the height of a particular row on demand by using the row index. Setting height to zero will collapse all the row in the grid. 

### QueryRowHeight

`SfDataGrid.QueryRowHeight` is the event that returns row heights on demand. This event receives two arguments namely the sender that handles the SfDataGrid and the [QueryRowHeightEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.QueryRowHeightEventArgs.html). The `QueryRowHeightEventRgs` has the following properties.

* [RowIndex](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.QueryRowHeightEventArgs~RowIndex.html): The property RowIndex helps you to identify a particular row in the grid.
* [Height](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.QueryRowHeightEventArgs~Height.html): This property sets and returns the height for a grid row on demand. Default line size for the rows is 50.
* [Handled](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridHandledEventArgs~Handled.html): This property decides whether the specified height can be set to row or not. The default value is `false`. When this property is not set, the decided height is not set to the row.

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

## Auto fit the grid rows based on content

SfDataGrid provides support for AutoRowHeight feature by which you can customize the row's height based on the content. This can be achieved by using the `SfDatagrid.QueryRowHeight` event and [SfDatagrid.GetRowHeight](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGridHelpers~GetRowHeight(SfDataGrid,Int32,GridRowSizingOptions).html) method. `SfDatagrid.QueryRowHeight` event returns the row height on demand and `SfDatagrid.GetRowHeight` method returns the height of the row based on the content.

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
