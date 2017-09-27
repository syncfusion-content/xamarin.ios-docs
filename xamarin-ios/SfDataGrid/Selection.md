---
layout: post
title: Selection | SfDataGrid | Xamarin.iOS | Syncfusion
description: How to enable selection, about the selection modes, properties, events and customizations available for selection in a SfDataGrid.
platform: xamarin.ios
control: SfDataGrid
documentation: UG
---

# Selection

This section explains you about how to enable selection in SfDataGrid and about the selection modes, properties, events that involve in selection and customizations available for Selection in SfDataGrid.

SfDataGrid lets you to select a specific row or group of rows either programmatically or by touch interactions. To enable Selection in SfDataGrid, you need to set the [SfDataGrid.SelectionMode](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~SelectionMode.html) property to value other than `None`. SfDataGrid has different selection modes to perform selection operation as listed below.

## Selection Modes 

<table>
<tr>
<th> Modes </th>
<th> Description </th>
</tr>
<tr>
<td> {{'[None](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SelectionMode.html)'| markdownify }} </td>
<td>Disables selection and no rows can be selected. This is the default value.</td>
</tr>
<tr>
<td> {{'[Single](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SelectionMode.html)'| markdownify }} </td>
<td> Allows you to select a single row only. Upon selecting the next row the selection in the previous row is cleared. </td>
</tr>
<tr>
<td> {{'[Multiple](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SelectionMode.html)'| markdownify }}  </td>
<td> Allows you to select more than one row. Selection is not cleared when selecting more than one records. When you click on a selected row for the second time, selection is cleared. </td>
</tr>
<tr>
<td>  {{'[SingleDeselect](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SelectionMode.html)'| markdownify }}  </td>
<td> Allows you to select only a single row, however upon tapping the row again the Selection is cleared. Similar to Single mode, upon selecting the next row the selection in the previous row is cleared. </td>
</tr>
</table>

The following code example illustrates how to set the selection mode in SfDataGrid.

{% highlight c# %}
dataGrid.SelectionMode = SelectionMode.Multiple; 
{% endhighlight %}

The following screenshot shows the selection functionality in SfDataGrid.

![](SfDataGrid_images/Selection.png)

## Programmatic Selection

When `SfDataGrid.SelectionMode` is set a value other than `None`, you can also select the row / rows in SfDataGrid from the code by setting the [SfDataGrid.SelectedIndex](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~SelectedIndex.html), [SfDataGrid.SelectedItem](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~SelectedItem.html) or [SfDataGrid.SelectedItems](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~SelectedItems.html) property based on the selection mode. The following code example illustrates how to enable selection from code in SfDataGrid.

When the selection mode is `Single` you can programmatically select a row in two ways, either by setting the row index to the `SfDataGrid.SelectedIndex` property or by setting the underlying object to be selected to the `SfDataGrid.SelectedItem` property. 

The following code example illustrates how to programmatically select a row from the code.

{% highlight c# %}
//Perform selection using selected index
dataGrid.SelectedIndex = 3;
 
//Perform selection using selected item
dataGrid.SelectedItem = viewModel.OrdersInfo [5];
{% endhighlight %}

When the selection mode is Multiple you can programmatically select more than one row by adding the underlying object to be selected to the `SfDataGrid.SelectedItems` property. 

The following code example illustrates how to programmatically select more than one row from the code.

{% highlight c# %} 
//Perform multiple selection using selected item
dataGrid.SelectedItems.Add (viewModel.OrdersInfo [4]);
dataGrid.SelectedItems.Add (viewModel.OrdersInfo [5]);
{% endhighlight %}

## Selection Events

The SfDataGrid provides you the following events for Selection:

* [SfDataGrid.SelectionChanging](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~SelectionChanging_EV.html) – This event is raised while selecting a row at the execution time before the row is selected. Hence it allows you to cancel the selection action by setting the Cancel property of [GridSelectionChangingEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSelectionChangingEventArgs.html).
* [SelectionChanged](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~SelectionChanged_EV.html) – This event is raised after the column is selected.

These two events are triggered with `GridSelectionChangingEventArgs` and [GridSelectionChangedEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSelectionChangedEventArgs.html) that contain the following properties.

* [AddedItems](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSelectionChangedEventArgs~AddedItems.html) – Gets the collection of underlying data objects that are added for selection.
* [RemovedItems](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSelectionChangedEventArgs~RemovedItems.html) – Gets the collection of underlying data objects that are removed selection.

The following code example illustrates how to hook the `SfDataGrid.SelectionChanging` event and cancel the selection of a column.

{% highlight c# %}
dataGrid.SelectionChanging += DataGrid_SelectionChanging;  

void DataGrid_SelectionChanging (object sender, GridSelectionChangingEventArgs e)
{
    e.Cancel = true;
}
{% endhighlight %}

The following code explains how to get the selected item in code-behind, by making use of the `SfDataGrid.SelectionChanged` event.

{% highlight c# %}
dataGrid.SelectionChanged += DataGrid_SelectionChanged;

private void DataGrid_SelectionChanged (object sender, GridSelectionChangedEventArgs e)
{
    // Gets the selected item.
    var selectedItems = e.AddedItems[0];
}
{% endhighlight %}

### CurrentItem

[SfDataGrid.CurrentItem](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~CurrentItem.html) property which hold the last selected row data of the SfDataGrid. You can get the current item in the `SfDataGrid.SelectionChanged` event, by setting the `SfDataGrid.SelectionMode` as `Multiple` or `SingleDeselect`. 

The below code example illustrates how to setting the selection mode for SfDataGrid and hooking the SelectionChanged event.

{% highlight c# %}
dataGrid.SelectionMode = SelectionMode.Multiple; 
 
dataGrid.SelectionChanged += DataGrid_SelectionChanged; 
 
void DataGrid_SelectionChanged (object sender, GridSelectionChangedEventArgs e) 
{ 
 var currentItem = dataGrid.CurrentItem; 
} 
{% endhighlight %}

## Row Header Selection

SfDataGrid lets you to select the grid row(s) upon tapping them over the grid cells. It also allows you select the grid rows when you tap the row header cells. To enable Selection in SfDataGrid, you need to set the `SfDataGrid.SelectionMode` property to value other than `None`.

### Select records in SfDataGrid when tapping only on the row header cells

SfDataGrid allows you to select a specific row or group of rows by touching the grid cells. However, if your requirement is to select the record only when tapping on the row header cells, then you can achieve the requirement by handling the `SfDataGrid.SelectionChanging` event. 
 
The below code example illustrates how to select records in SfDataGrid when tapping only on the row header cells.

{% highlight c# %}

dataGrid.SelectionMode = SelectionMode.Single;

private void DataGrid_SelectionChanging(object sender, GridSelectionChangingEventArgs e)
{
    e.Cancel = true;
}

private void DataGrid_GridTapped(object sender, GridTappedEventsArgs e)
{
    if(e.RowColumnIndex.ColumnIndex == 0)
    {
        dataGrid.SelectedIndex = e.RowColumnIndex.RowIndex;
    }
}
 
{% endhighlight %}

N> To enable the row header in SfDataGrid, you need to set the `SfDataGrid.ShowRowHeader` as `true`.

## Clear Selection

SfDataGrid allows you to clear the selection applied in the grid rows in two ways, either by setting the `SfDataGrid.SelectionMode` to `None` or by calling the [SfDataGrid.SelectionController.ClearSelection ()](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSelectionController~ClearSelection.html) method.

The following code example illustrates how to clear selection in SfDataGrid.

{% highlight c# %}
//Clear selection using selection mode
dataGrid.SelectionMode = SelectionMode.None;

//Clear selection using selection controller
dataGrid.SelectionController.ClearSelection (); 
{% endhighlight %}

N> Selected items and the selections will be cleared whenever the ItemsSource is changed in runtime.

## Multiple Selection Colors

SfDataGrid provides support to select one or more rows either programmatically or by touch interactions. By default SfDataGrid applies a common background color for the selected rows based on the current theme. However it also provides extensibility to have multiple selection colors when touching the rows by writing a custom SelectionController derived from [GridSelectionController](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSelectionController.html) and assigning it to the [SfDataGrid.SelectionController](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~SelectionController.html) property. You need to override the GetSelectionColor () method to apply different colors for selection in runtime based on your requirement.
The following code example illustrates how to set different colors for the selected rows in SfDataGrid.

{% highlight c# %}
sfGrid.SelectionController = new CustomSelectionController(sfGrid);
sfGrid.SelectionMode = SelectionMode.Multiple;
{% endhighlight %}

{% highlight c# %}
public class CustomSelectionController : GridSelectionController
{
    public Color[] SelectionColors { get; set; }

    public CustomSelectionController(SfDataGrid datagrid)
    {
        this.DataGrid = datagrid;
        SelectionColors = new Color[11] 
        { 
           UIColor.Orange,
           UIColor.FromRGB(201,93,55),
           UIColor.FromRGB(123,149,52),
           UIColor.Red,
           UIColor.Black,
           UIColor.Brown,
           UIColor.FromRGB(42,159,214),
           UIColor.Gray,UIColor.FromRGB(24,123,67),
           UIColor.Purple,UIColor.FromRGB(72,173,170)
        };   
    }
    //Code to set multiple selection colors
    public override Color GetSelectionColor(int rowIndex, object rowData)
    {
        if (SelectionColors != null)
            return SelectionColors[rowIndex % 11];
        else
            return Color.Blue;
    }
}
{% endhighlight %}

The following screenshot shows the final outcome upon execution of the above code.

![](SfDataGrid_images/MultipleSelectionColors_img1.png)

## Selection Animation

SfDataGrid provides support to select one or more rows programmatically or by touch interactions. In addition, SfDataGrid also provides extensibility to animate the selected rows. 
It can be done by extending the [GridSelectionController](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSelectionController.html ).

Refer the below example in which a CustomSelectionController derived from `GridSelectionController` and an instance of it is assigned to [SfDataGrid.SelectionController](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~SelectionController.html ) property to achieve selection animation.

{% highlight c# %}
dataGrid.SelectionController = new CustomSelectionController(dataGrid);
dataGrid.SelectionMode = SelectionMode.Multiple;
{% endhighlight %}

{% highlight c# %}
public class CustomSelectionController : GridSelectionController
{
    public CustomSelectionController(SfDataGrid dataGrid)
    {
        this.SelectedRows = new GridSelectedRowsCollection();
        this.DataGrid = dataGrid;
    }
    protected override void SetSelectionAnimation(VirtualizingCellsControl rowElement)
    {
        rowElement.Alpha = 0.75f;
        UIView.Animate(1, 1, UIViewAnimationOptions.CurveLinear, () =>
        {
            rowElement.Alpha = 1f;
        }, null);
    }
}
{% endhighlight %}

The following screenshot shows the selection animation in SfDataGrid.

![](SfDataGrid_images/SelectionAnimation.gif)