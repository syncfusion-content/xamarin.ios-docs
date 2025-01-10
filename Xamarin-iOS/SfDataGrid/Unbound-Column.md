---
layout: post
title: UnboundColumn | SfDataGrid | Xamarin.iOS | Syncfusion
description: How to create and use Unbound column in SfDataGrid?
platform: xamarin.ios
control: SfDataGrid
documentation: ug
---

# Unbound Column

SfDataGrid allows you to add **additional columns** which are **not bound with data object** from underlying data source. You can add unbound column using [SfDataGrid.GridUnboundColumn](http://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.GridUnboundColumn.html) class.

{% highlight c# %}
SfDataGrid dataGrid = new SfDataGrid ();
UnboundViewModel viewModel = new UnboundViewModel();
dataGrid.ItemsSource = viewModel.Products;

GridUnboundColumn AmountColumn = new GridUnboundColumn();
AmountColumn.MappingName = "Amount";
AmountColumn.HeaderText = "Amount";
AmountColumn.Expression = "UnitPrice * Quantity";
AmountColumn.Format = "C";
AmountColumn.HeaderTextAlignment = UITextAlignment.Center;
AmountColumn.TextAlignment = UITextAlignment.Center;
dataGrid.Columns.Add(AmountColumn);

GridUnboundColumn TotalColumn = new GridUnboundColumn();
TotalColumn.MappingName = "Total";
TotalColumn.HeaderText = "Discounted Total";
TotalColumn.Expression = "(Quantity * UnitPrice) - ((Quantity * UnitPrice)/100 * Quantity)";
TotalColumn.Format = "C";
TotalColumn.HeaderTextAlignment = UITextAlignment.Center;
TotalColumn.TextAlignment = UITextAlignment.Center ;
dataGrid.Columns.Add(TotalColumn);
{% endhighlight %}

![](SfDataGrid_images/UnboundColumn.png)

N> It is mandatory to specify the [GridColumn.MappingName](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.GridColumn.html#Syncfusion_SfDataGrid_GridColumn_MappingName) for `SfDataGrid.GridUnboundColumn` with some name to identify the column. It is not necessary to define name of field in the data object.

## Populating data for unbound column

You can populate the data for unbound column by setting [Expression](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.GridUnboundColumn.html#Syncfusion_SfDataGrid_GridUnboundColumn_Expression) or [Format](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.GridColumn.html#Syncfusion_SfDataGrid_GridColumn_Format) property.

### Using Expression

You can specify the arithmetic or logic expression using `Expression` property to compute the display value. By default `GridUnboundColumn` evaluates the expression with casing. You can disable the casing while evaluate the expression by setting [CaseSensitive](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.GridUnboundColumn.html#Syncfusion_SfDataGrid_GridUnboundColumn_CaseSensitive) property to `false`.
Below are the list of Arithmetic and logical operations supported.

<table>
<tr>
<th>
Arithmetic operations
</th>
<th>
Operator
</th>
</tr>
<tr>
<td>
Add
</td>
<td>
+
</td>
</tr>
<tr>
<td>
Subtract
</td>
<td>
-
</td>
</tr>
<tr>
<td>
Multiply
</td>
<td>
*
</td>
</tr>
<tr>
<td>
Divide
</td>
<td>
/
</td>
</tr>
<tr>
<td>
Power
</td>
<td>
^
</td>
</tr>
<tr>
<td>
Mod
</td>
<td>
%
</td>
</tr>
<tr>
<td>
Greater Than
</td>
<td>
>
</td>
</tr>
<tr>
<td>
Less Than
</td>
<td>
<
</td>
</tr>
<tr>
<td>
Equal
</td>
<td>
=
</td>
</tr>
<tr>
<td>
GreaterThanOrEqual
</td>
<td>
>=
</td>
</tr>
<tr>
<td>
LessThanOrEqual
</td>
<td>
<=
</td>
</tr>
</table>

*Logical Operations*

<table>
<tr>
<th>
Logical operations
</th>
<th>
Operators
</th>
</tr>
<tr>
<td>
AND
</td>
<td>
(char)135
</td>
</tr>
<tr>
<td>
OR
</td>
<td>
(char)136
</td>
</tr>
<tr>
<td>
NOT
</td>
<td>
(char)137
</td>
</tr>
</table>


{% highlight c# %}
SfDataGrid dataGrid = new SfDataGrid ();
UnboundViewModel viewModel = new UnboundViewModel();
dataGrid.ItemsSource = viewModel.Products;

GridUnboundColumn TotalColumn = new GridUnboundColumn();
TotalColumn.MappingName = "Total";
TotalColumn.HeaderText = "Discounted Total";
TotalColumn.Expression = "(Quantity * UnitPrice) - ((Quantity * UnitPrice)/100 * Quantity)";
dataGrid.Columns.Add(TotalColumn);
{% endhighlight %}

### Using Format

You can format the values of other columns and display the formatted value in unbound column using `Format` property.

{% highlight c# %}
SfDataGrid dataGrid = new SfDataGrid ();
UnboundViewModel viewModel = new UnboundViewModel();
dataGrid.ItemsSource = viewModel.Products;

GridUnboundColumn TotalColumn = new GridUnboundColumn();
TotalColumn.MappingName = "Total";
TotalColumn.HeaderText = "Discounted Total";
TotalColumn.Format = "C";
dataGrid.Columns.Add(TotalColumn);
{% endhighlight %}

### Using QueryUnboundColumnValue event

[QueryUnboundColumnValue](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.SfDataGrid.html) event is fired when value for the unbound column is queried. It provides the information about the cell that triggered this event and hence you can set the desired value for the grid cells of the unbound column. This event is triggered with [GridUnboundColumnEventsArgs](http://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.GridUnboundColumnEventsArgs.html).

`GridUnboundColumnEventsArgs` provides the following properties:

* [Column](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.GridUnboundColumnEventsArgs.html#Syncfusion_SfDataGrid_GridUnboundColumnEventsArgs_Column) - Gets the GridColumn of the cell that triggers this event.  
* [OriginalSender](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.GridEventArgs.html#Syncfusion_SfDataGrid_GridEventArgs_OriginalSender) - Gets the dataGrid raising this event.
* [Record](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.GridUnboundColumnEventsArgs.html#Syncfusion_SfDataGrid_GridUnboundColumnEventsArgs_Record) - Gets the underlying row data. 
* [UnboundAction](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.GridUnboundColumnEventsArgs.html#Syncfusion_SfDataGrid_GridUnboundColumnEventsArgs_UnboundAction) - Defines the action for triggering this event.
* [Value](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.GridUnboundColumnEventsArgs.html#Syncfusion_SfDataGrid_GridUnboundColumnEventsArgs_Value) - Gets or sets the value for GridUnboundColumn cell based on UnboundAction.

N> `UnboundActions.CommitData` and `UnboundActions.PasteData` are currently not supported and likely to be supported in future.    

You can populate data for the Unbound column by handling `QueryUnboundColumnValue` event, which allows you to customize the value of the `GridUnboundColumn`. `GridUnboundColumnEventsArgs` exposes `Value` property by which you can set the value for the grid cells of the unbound column based on the `UnboundAction`.

Refer the below code example in which data for the unbound column is populated by handling the `QueryUnboundColumnValue` event.

{% highlight c# %}
dataGrid.QueryUnboundColumnValue += DataGrid_QueryUnboundColumnValue;

private void DataGrid_QueryUnboundColumnValue(object sender, GridUnboundColumnEventsArgs e)
{
    if (e.UnboundAction == UnboundActions.QueryData)
    {
        var quantity = Convert.ToInt16(e.Record.GetType().GetProperty("Quantity").GetValue(e.Record));
        var unitPrice = Convert.ToInt16(e.Record.GetType().GetProperty("UnitPrice").GetValue(e.Record));
        var amount = quantity * unitPrice;
        e.Value = amount;
    }
}
{% endhighlight %}
