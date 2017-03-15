---
layout: post
title: Columns | SfDataGrid | Xamarin.iOS | Syncfusion
description: How to create and add columns, different ways to create columns and its customizations in a SfDataGrid.
platform: xamarin.ios
control: SfDataGrid
documentation: UG
---

# Columns 

SfDataGrid allows you to create and add Columns in two ways:

* Automatic Columns generation based on the underlying collection.
* Manually defining columns in C#.


## Automatic Columns Generation

The SfDataGrid creates columns automatically based on the property [SfDataGrid.AutoGenerateColumns](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~AutoGenerateColumns.html). It is a bindable property and it decides columns generation for SfDataGrid based on the [SfDataGrid.AutoGenerateColumnsMode](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~AutoGenerateColumnsMode.html) property. 

`SfDataGrid.AutoGenerateColumnsMode` decides a way to create columns when `SfDataGrid.AutoGenerateColumns` is set to `true`. It also decides whether to retain the grouping and sorting when ItemsSource is changed. 

The `SfDataGrid.AutoGenerateColumnsMode` is of type [AutoGenerateColumnsMode](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~AutoGenerateColumnsMode.html) which has the following five options.

* None: Stores only the columns that are defined in [SfDataGrid.Columns](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~Columns.html) collection. When changing the ItemsSource, the grouping and sorting for explicitly defined `SfDataGrid.Columns` alone will be retained.
* Reset: Retains the columns defined explicitly in the application level and creates columns newly for all the other properties in a data source. When changing the ItemsSource, the grouping and sorting for explicitly defined `SfDataGrid.Columns` alone will be retained.
* ResetAll: When changing the ItemsSource, the columns for the previous data source are cleared and the columns will be created newly for the new data source. Even when columns are explicitly defined it does not consider the defined columns and creates the column based on the underlying collection. Further, when changing the ItemsSource, the grouping and sorting for all the columns will be cleared.
* RetainOld: When changing the ItemsSource, creates columns for all fields in a data source when the Grid does not have any explicit definition for columns. When columns are defined explicitly, then the defined columns alone are retained and new columns are not created. Similarly, when changing the ItemsSource and when the Grid have any explicit definition for columns, the grouping and sorting are retained as it is.
* SmartReset: Retains the columns defined explicitly in application level and the columns with `MappingName` identical to the properties in the new data source. Creates columns newly for all the other properties in the data source. Similarly, it retains the grouping and sorting of the columns that are defined explicitly in application level and the columns with `MappingName` identical to the properties in new data source.


The default value of `SfDataGrid.AutoGenerateColumns` property is `true` and `SfDataGrid.AutoGenerateColumnsMode` is `Reset`. Hence by default SfDataGrid creates columns automatically for every non-explicitly defined public property in the underlying collection bound to its `ItemsSource` property.

N> When you change items source for SfDataGrid during run time, then the columns are generated on the basis of option set for `SfDataGrid.AutoGenerateColumnsMode`.

### Customize Automatically Generated Columns

When `SfDataGrid.AutoGenerateColumns` is `true`, then [SfDataGrid.AutoGeneratingColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~AutoGeneratingColumn_EV.html) event is raised for each GridColumn. This event receives two arguments namely sender which is the SfDataGrid and [AutoGeneratingColumnArgs](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.AutoGeneratingColumnArgs.html).
The `AutoGeneratingColumnArgs` object contains the following property:

* Column: This property returns the created column using which you can customize the column.
* Cancel: This property cancels the column creation.

You can skip generating a column by handling the `SfDataGrid.AutoGeneratingColumn` event as shown below.

{% highlight c# %}
dataGrid.AutoGeneratingColumn += GridAutoGeneratingColumns; 

void GridAutoGeneratingColumns(object sender, AutoGeneratingColumnArgs e)
{
    if (e.Column.MappingName == "EmployeeID")
        e.Cancel = true;
}
{% endhighlight %}

Customizing the width for auto generated columns as shown below.

{% highlight c# %}
void dataGrid_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e){
if (e.Column.MappingName == "OrderID") {
    e.Column.Width = 100;
    }
}
{% endhighlight %}

You can also apply formatting for auto generated columns as shown below.

{% highlight c# %}
void GridAutoGeneratingColumns(object sender, AutoGeneratingColumnArgs e)
{
    if (e.Column.MappingName == "Freight") {
        e.Column.Format = "C";
        e.Column.CultureInfo = new CultureInfo ("en-US");
    } else if (e.Column.MappingName == "ShippingDate")
        e.Column.Format = "dd/MM/yyyy";
} 
{% endhighlight %}

You can also customize a column’s header text, sorting, alignment, padding, etc. by handling the `SfDataGrid.AutoGeneratingEvent`.


## Manually generate Columns

SfDataGrid also allows you to define the columns manually by adding the GridColumn objects to the `SfDataGrid.Columns` collection. In case if you want only the manually defined columns to be in view, then you can achieve it by setting the `SfDataGrid.AutoGenerateColumns` property to `false`. There are different types of columns available in SfDataGrid and you can create any column based on your requirements through code.
 
The following code example illustrates about creating columns manually in SfDataGrid.

{% highlight c# %}
dataGrid.AutoGenerateColumns = false;

GridTextColumn orderIdColumn = new GridTextColumn ();
orderIdColumn.MappingName = "OrderID";
orderIdColumn.HeaderText = "Order ID";

GridTextColumn customerIdColumn = new GridTextColumn ();
customerIdColumn.MappingName = "CustomerID";
customerIdColumn.HeaderText = "Customer ID";

GridTextColumn customerColumn = new GridTextColumn ();
customerColumn.MappingName = "Customer";

GridTextColumn countryColumn = new GridTextColumn ();
countryColumn.MappingName = "ShipCountry";
countryColumn.HeaderText = "Ship Country";

dataGrid.Columns.Add (orderIdColumn);
dataGrid.Columns.Add (customerIdColumn);
dataGrid.Columns.Add (customerColumn);
dataGrid.Columns.Add (countryColumn); 
{% endhighlight %}
