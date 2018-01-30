---
layout: post
title: Summary | SfDataGrid | Xamarin.iOS | Syncfusion
description: How to apply summaries for the elements in a SfDataGrid.
platform: xamarin.ios
control: SfDataGrid
documentation: UG
---

# Summary

The data grid supports to display the concise information about the bound data objects using summaries. The control provides the following summary types:

* **Caption Summary**: Used to display the summary information in the caption of the group.
* **Table Summary**: Used to display the summary information at top and/or bottom in the data grid.

![](SfDataGrid_images/Summary1.PNG)

Summary rows are represented by using the [GridSummaryRow](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryRow.html). Each `GridSummaryRow` hold summary information of columns in the [SummaryColumns](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryRow~SummaryColumns.html) property . The `SummaryColumns` contains the collection of [GridSummaryColumn](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryColumn.html) which carries name, format, and summary aggregate type of the column.

Additional information can be derived from the data like sum, average, maximum, minimum, and count using summaries in the data grid. These summary values can be computed for groups or for the entire control using `GridSummaryRow` and `GridSummaryColumn` that implements [ISummaryRow](http://help.syncfusion.com/cr/cref_files/xamarin-ios/linq/Syncfusion.Linq.iOS~Syncfusion.Data.ISummaryRow.html) and [ISummaryColumn](http://help.syncfusion.com/cr/cref_files/xamarin-ios/linq/Syncfusion.Linq.iOS~Syncfusion.Data.ISummaryColumn.html) interfaces.

N> The Summary does not refresh with data. To update summary for the newly added row or if any values in the summary column is modified, set the [SfDataGrid.View.LiveDataUpdateMode](https://help.syncfusion.com/cr/cref_files/xamarin-ios/linq/Syncfusion.Linq.iOS~Syncfusion.Data.CollectionViewAdv~LiveDataUpdateMode.html) to `LiveDataUpdateMode.AllowDataShaping` or `LiveDataUpdateMode.AllowSummaryUpdate`.

## Caption summaries

The data grid provides built-in support for caption summaries. The caption summary value is calculated based on the records in a group and the summary information will be displayed in the caption of a group.

The following screenshot shows the built-in caption summary of a group:

![](SfDataGrid_images/Summary2.PNG)

### Formatting built-in caption summary

By default, the summary value displayed in caption summary rows are based on the [SfDataGrid.GroupCaptionTextFormat](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~GroupCaptionTextFormat.html) property.

Default group caption format is `{ColumnName}: {Key} - {ItemsCount} Items`.

* **ColumnName**: Displays the name of the currently grouped column.
* **Key**: Displays the key value of the group.
* **ItemsCount**: Displays the number of items in a group.

![](SfDataGrid_images/Summary3.PNG)

The group caption text format can be customized by setting the `SfDataGrid.GroupCaptionTextFormat` property. The following code example illustrates how to customize group caption text in the data grid:

{% highlight c# %}
//Customized group caption text
dataGrid.GroupCaptionTextFormat = "{ColumnName} : {Key}";
{% endhighlight %}

The following screenshot shows the outcome of the previous code:

![](SfDataGrid_images/Summary4.PNG)


### Displaying summary in the row

The summary information can be displayed in a row by setting the [GridSummaryRow.ShowSummaryInRow](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryRow~ShowSummaryInRow.html) to `true` and by defining summary columns. You have to define the [GridSummaryRow.Title](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryRow~Title.html) based on the [GridSummaryColumn.Name](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryColumn~Name.html) property to format summary columns value in a row.

{% highlight c# %}
GridSummaryRow summaryRow = new GridSummaryRow();
summaryRow.Title = "Total Salary:{TotalSalary} for {ProductCount} items";
summaryRow.ShowSummaryInRow = true;
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "TotalSalary",
    MappingName = "Salary",
    Format = "{Sum:c}",
    SummaryType = SummaryType.DoubleAggregate
});
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "ProductCount",
    MappingName = "Salary",
    Format = "{Count}",
    SummaryType = SummaryType.CountAggregate
});
dataGrid.CaptionSummaryRow= summaryRow;
{% endhighlight %}

The following screenshot shows the outcome for both values of `ShowSummaryInRow` to `true`:

![](SfDataGrid_images/Summary5.PNG)


### Displaying summary in the column

The summary information can be displayed in the column by setting the `GridSummaryRow.ShowSummaryInRow` to `false` and by defining summary columns. The `SfDataGrid.GridSummaryColumn` is the object of [GridSummaryRow.SummaryColumns](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryRow~SummaryColumns.html) collection that contains the following important properties:

* [Name](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryColumn~Name.html): Defines name of the `GridSummaryColumn` to denote the `GridSummaryColumn` in `GridSummaryRow` with the Title.
* [MappingName](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryColumn~MappingName.html): Defines the corresponding column name that is used for the summary calculation.
* [SummaryType](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryColumn~SummaryType.html): Defines the `SummaryType` (enum) property to define the aggregate type for the summary calculation. 

The `data grid` control provides the following predefined aggregates:

  * CountAggregate
  * Int32Aggregate
  * DoubleAggregate

The [CustomAggregate](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryColumn~CustomAggregate.html) defines the `CustomAggregate` class object when the summary type is set as `custom` that calculates custom summaries.

The [Format](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryColumn~Format.html) `string` property formats the summary value and displays it. It may contain two parts separated by a colon (:). First part denotes the aggregate function name, and second part denotes display format of the summary value.

Refer to [Formatting Summary](#_Formatting_Summary) section to know more about how to format summary and [Aggregate Types](#_Aggregate_Types) section to know about different summary types.

In the following code snippet, the summary is defined for the `Salary` column:

{% highlight c# %}
GridSummaryRow summaryRow = new GridSummaryRow();
summaryRow.ShowSummaryInRow = false;
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "CaptionSummary",
    MappingName = "Salary",
    Format = "{Sum:c}",
    SummaryType = SummaryType.DoubleAggregate
});
dataGrid.CaptionSummaryRow= summaryRow;
{% endhighlight %}

![](SfDataGrid_images/Summary6.PNG)

## Table summaries

The data grid provides built-in support for table summaries. The table summary value is calculated based on all records in the control.

Add table summary row in the data grid by adding the [GridTableSummaryRow](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridTableSummaryRow.html) to the [SfDataGrid.TableSummaryRows](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~TableSummaryRows.html) collection.

The following screenshot illustrates table summary rows in the data grid:

![](SfDataGrid_images/Summary7.PNG)

{% highlight c#%}
GridTableSummaryRow summaryRow1 = new GridTableSummaryRow();
summaryRow1.Title = "Total Salary:{TotalSalary} for {ProductCount} members";
summaryRow1.ShowSummaryInRow = true;
summaryRow1.Position = Position.Top;
summaryRow1.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "TotalSalary",
    MappingName = "Salary",
    Format = "{Sum:c}",
    SummaryType = SummaryType.DoubleAggregate
});
summaryRow1.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "ProductCount",
    MappingName = "Salary",
    Format = "{Count}",
    SummaryType = SummaryType.CountAggregate
});
sfGrid.TableSummaryRows.Add(summaryRow1);

GridTableSummaryRow summaryRow2 = new GridTableSummaryRow();
summaryRow2.ShowSummaryInRow = false;
summaryRow2.Position = Position.Top;
summaryRow2.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "TotalSalary",
    MappingName = "Salary",
    Format = "{Sum}",
    SummaryType = SummaryType.DoubleAggregate
});
sfGrid.TableSummaryRows.Add(summaryRow2);
{% endhighlight %}

![](SfDataGrid_images/Summary8.PNG)

### Displaying summary in the row

The summary information can be displayed in the row by setting the [GridTableSummaryRow.ShowSummaryInRow](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryRow~ShowSummaryInRow.html) to `true` and by defining summary columns. You have to define the [GridTableSummaryRow.Title](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryRow~Title.html) based on the [GridSummaryColumn.Name](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryRow~Name.html) property to format summary columns value in a row.

{% highlight c#%}
GridTableSummaryRow summaryRow = new GridTableSummaryRow();
summaryRow.Title = "Total Salary:{TotalSalary} for {ProductCount} members";
summaryRow.ShowSummaryInRow = true;
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "TotalSalary",
    MappingName = "Salary",
    Format = "{Sum:c}",
    SummaryType = SummaryType.DoubleAggregate
});
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "ProductCount",
    MappingName = "Salary",
    Format = "{Count}",
    SummaryType = SummaryType.CountAggregate
});
sfGrid.TableSummaryRows.Add(summaryRow);
{% endhighlight %}

The following screenshot shows the table summary row if `ShowSummaryInRow` is `true`:

![](SfDataGrid_images/Summary9.PNG)

### Displaying summary in the column

The summary information can be displayed in the column by setting the `GridTableSummaryRow.ShowSummaryInRow` to `false` and by defining summary columns. The `GridSummaryColumn` is the object of [GridTableSummaryRow.SummaryColumns](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryRow~SummaryColumns.html) collection that contains the following important properties:

* [Name](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryColumn~Name.html): Defines name of the `GridSummaryColumn` to denote the `GridSummaryColumn` in `GridTableSummaryRow` with the Title.
* [MappingName](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryColumn~MappingName.html): Defines the corresponding column name that is used for the summary calculation.
* [SummaryType](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryColumn~SummaryType.html): Defines the `SummaryType` (enum) property to define the aggregate type for the summary calculation. 

The data grid control provides the following predefined aggregates:

  * CountAggregate
  * Int32Aggregate
  * DoubleAggregate

The [CustomAggregate](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryColumn~CustomAggregate.html) defines the `CustomAggregate` class object when the summary type is set as `custom` that calculates custom summaries.

The [Format](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryColumn~Format.html) `string` property formats the summary value and displays it. It may contain two parts separated by a colon (:). First part denotes the aggregate function name, and second part denotes display format of the summary value.

Refer to [Formatting Summary](#_Formatting_Summary) section to know more about how to format summary and [Aggregate Types](#_Aggregate_Types) section to know about different summary types.

In the following code snippet, summary is defined for the `Salary` column:

{% highlight c#%}
GridTableSummaryRow summaryRow = new GridTableSummaryRow();
summaryRow.ShowSummaryInRow = false;
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "TableSummary",
    MappingName = "Salary",
    Format = "{Sum}",
    SummaryType = SummaryType.DoubleAggregate
});
sfGrid.TableSummaryRows.Add(summaryRow);
{% endhighlight c#%}

The following screenshot shows the table summary row if `ShowSummaryInRow` is `false`:

![](SfDataGrid_images/Summary10.PNG)

### Positioning TableSummaryRows

The data grid add table summary rows either at top or bottom positions using the [GridTableSummaryRow.Position](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridTableSummaryRow~Position.html) property.

{% highlight c#%}
GridTableSummaryRow topSummaryRow = new GridTableSummaryRow();
topSummaryRow.Position = Position.Top;
topSummaryRow.ShowSummaryInRow = false;
topSummaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "TotalSalary",
    MappingName = "Salary",
    Format = "{Sum}",
    SummaryType = SummaryType.DoubleAggregate
});
sfGrid.TableSummaryRows.Add(topSummaryRow);

GridTableSummaryRow bottomSummaryRow = new GridTableSummaryRow();
bottomSummaryRow.Position = Position.Bottom;
bottomSummaryRow.Title = "Total Salary:{TotalSalary} for {ProductCount} members";
bottomSummaryRow.ShowSummaryInRow = true;
bottomSummaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "TotalSalary",
    MappingName = "Salary",
    Format = "{Sum:c}",
    SummaryType = SummaryType.DoubleAggregate
});
bottomSummaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "ProductCount",
    MappingName = "Salary",
    Format = "{Count}",
    SummaryType = SummaryType.CountAggregate
});
sfGrid.TableSummaryRows.Add(bottomSummaryRow);
{% endhighlight %}

The following screenshot illustrates the positioning of table summary rows in the data grid:

![](SfDataGrid_images/Summary11.PNG)


## Formatting summary

In the following sections, formatting is explained using the `CaptionSummary`:

### Defining summary function

In the following code snippet, the `Format` property is defined to display the sum of `Salary` by specifying the function name inside curly braces:

N> `DoubleAggregate` is used as `SummaryType` which has the count, max, min, average, and sum functions.

{% highlight c# %}
GridSummaryRow summaryRow = new GridSummaryRow();
summaryRow.ShowSummaryInRow = false;
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "CaptionSummary",
    MappingName = "Salary",
    Format = "{Sum}",
    SummaryType = SummaryType.DoubleAggregate
});
dataGrid.CaptionSummaryRow= summaryRow;
{% endhighlight %}

![](SfDataGrid_images/Summary12.PNG)


### Formatting summary value

Format the summary value by setting the appropriate format after the aggregate function followed by colon(:) in the [GridSummaryColumn.Format](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryColumn~Format.html) property.

In the following code snippet, the `Salary` column summary is formatted using `c` format specifier. Refer to [here](https://msdn.microsoft.com/en-us/library/dwhawy9k.aspx?f=255&MSPPError=-2147217396) to know about how to set different format.

{% highlight c# %}
GridSummaryRow summaryRow = new GridSummaryRow();
summaryRow.ShowSummaryInRow = false;
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "CaptionSummary",
    MappingName = "Salary",
    Format = "{Sum:c}",
    SummaryType = SummaryType.DoubleAggregate
});
dataGrid.CaptionSummaryRow= summaryRow;
{% endhighlight %}

![](SfDataGrid_images/Summary13.PNG)


### Displaying additional content in the summary

You can append additional content with summary value using `GridSummaryColumn.Format` property.

In the following code snippet, `Total:` text is appended before the summary value:

{% highlight c# %}
GridSummaryRow summaryRow = new GridSummaryRow();
summaryRow.ShowSummaryInRow = false;
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "CaptionSummary",
    MappingName = "Salary",
    Format = "Total:{Sum:c}",
    SummaryType = SummaryType.DoubleAggregate
});
dataGrid.CaptionSummaryRow= summaryRow;
{% endhighlight %}

![](SfDataGrid_images/Summary14.PNG)


### Formatting summary for row using the Title property

Format the summary value for the row using the [GridSummaryRow.Title](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryRow~Title.html) when `ShowSummaryInRow` set to `true`.

{% highlight c# %}
GridSummaryRow summaryRow = new GridSummaryRow();
summaryRow.Title = "Total Salary:{TotalSalary} for {ProductCount} items";
summaryRow.ShowSummaryInRow = true;
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "TotalSalary",
    MappingName = "Salary",
    Format = "{Sum:c}",
    SummaryType = SummaryType.DoubleAggregate
});
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "ProductCount",
    MappingName = "Salary",
    Format = "{Count}",
    SummaryType = SummaryType.DoubleAggregate
});
dataGrid.CaptionSummaryRow= summaryRow;
{% endhighlight %}

![](SfDataGrid_images/Summary15.PNG)

N> The above formatting section is explained using the `caption summary` but the formatting can also be applied for `TableSummaries`.

## Aggregate types

Specify different summary aggregate types by using the [GridSummaryColumn.SummaryType](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryColumn~SummaryType.html) property and use the built-in function in `GridSummaryColumn.Format`.

List of predefined aggregate types and its built-in functions are as follows:

<table>
<tr>
<th>
Aggregate Type
</th>
<th>
Built-in function
</th>
</tr>
<tr>
<td>
CountAggregate
</td>
<td>
Count
</td>
</tr>
<tr>
<td>
Int32Aggregate
</td>
<td>
Count, max, min, average, and sum.
</td>
</tr>
<tr>
<td>
DoubleAggregate
</td>
<td>
Count, max, min, average, and sum.
</td>
</tr>
<tr>
<td>
Custom
</td>
<td>
Used for custom summaries
</td>
</tr>
</table>

N> The above aggregate types can be applied for both `CaptionSummaries` and `TableSummaries`.

## Custom summaries

The data grid implements your own aggregate functions when the built-in aggregate functions do not meet your requirement.

Calculate the summary values based on custom logic using the [GridSummaryColumn.CustomAggregate](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSummaryColumn~CustomAggregate.html) property.

### Implementing custom aggregate

1. Create custom aggregate class by deriving from [ISummaryAggregate](https://help.syncfusion.com/cr/cref_files/xamarin-ios/linq/Syncfusion.Linq.iOS~Syncfusion.Data.ISummaryAggregate.html) interface.
2. In the `CalculateAggregateFunc` method, you have to calculate the summary and assign it to the property.

In the follwoing code snippet, the `Standard Deviation` is calculated for the quantity of products:

{% highlight c# %}
public class CustomAggregate : ISummaryAggregate
{
    public CustomAggregate()
    {
        
    }
    
    public double StdDev { get; set; }
    
    public Action<System.Collections.IEnumerable, string, System.ComponentModel.PropertyDescriptor> CalculateAggregateFunc()
    {
        return (items, property, pd) =>
        {
            var enumerableItems = items as IEnumerable<OrderInfo>;
            if (pd.Name == "StdDev")
            {
                this.StdDev = enumerableItems.StdDev<OrderInfo>(q => q.OrderID);
            }
        };
    }
}

public static class LinqExtensions
{
    public static double StdDev<T>(this IEnumerable<T> values, Func<T, double?> selector)
    {
        double value = 0;
        var count = values.Count();
        if (count > 0)
        {
            double? avg = values.Average(selector);
            double sum = values.Select(selector).Sum(d =>
            {
                if (d.HasValue)
                {
                    return Math.Pow(d.Value - avg.Value, 2);
                }
                return 0.0;
            });
            value = Math.Sqrt((sum) / (count - 1));
        }
        return value;
    }
}
{% endhighlight %}

Assign the custom aggregate to `GridSummaryColumn.CustomAggregate` property and set the `SummaryType` as `Custom`. The `GridSummaryColumn.Format` property is defined based on property name in custom aggregate `StdDev`.

{% highlight c# %}
GridSummaryRow summaryRow = new GridSummaryRow();
summaryRow.Title = "Standard Deviation:{CaptionSummary}";
summaryRow.ShowSummaryInRow = true;
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "CaptionSummary",
    CustomAggregate  = new CustomAggregate(),
    MappingName = "OrderID",
    Format = "{StdDev}",
    SummaryType = Syncfusion.Data.SummaryType.Custom
});
dataGrid.CaptionSummaryRow = summaryRow;
{% endhighlight %}

![](SfDataGrid_images/Summary16.PNG)

N> The above custom summaries section is explained using `CaptionSummary` but the custom summaries can also be applied for `TableSummaries`.


## Overriding summary renderer

Each summary cell in the data grid is associated with its own renderer and it can be customized by overriding the available virtual methods in the corresponding renderer.

Each summary has a specific key using which you can register the custom summary renderer to the [SfDataGrid.CellRenderers](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~CellRenderers.html) collection. Remove the key from collection and add a new entry with the same key along with the instance of custom renderer to register.

<table>

<tr>
<th>Types of summary</th>
<th>Renderer</th>
<th>Key</th>
</tr>

<tr>
<td>Table summary</td>
<td><a href="https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridTableSummaryCellRenderer.html">GridTableSummaryCellRenderer</a> </td>
<td>TableSummary</td>
</tr>

<tr>
<td>Caption summary</td>
<td><a href="https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridCaptionSummaryCellRenderer.html">GridCaptionSummaryCellRenderer</a> </td>
<td>CaptionSummary</td>
</tr>

<tr>
<td>Group summary</td>
<td><a href="">GridSummaryCellRenderer</a> </td>
<td>GroupSummary</td>
</tr>

</table>

### Customizing table summary

The data grid customizes the table summary by overriding [GridTableSummaryCellRenderer](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridTableSummaryCellRenderer.html).

To customize the table summary, follow the code example:

{% highlight c#%}

// To remove default summary and Add custom summary.

public class Summary : ContentPage
{
    public Summary()
    {
        InitializeComponent();
        dataGrid.CellRenderers.Remove("TableSummary");
        dataGrid.CellRenderers.Add("TableSummary", new GridTableSummaryCellRendererExt());
    }
}

 public class GridTableSummaryCellRendererExt : GridTableSummaryCellRenderer
    {
        public GridTableSummaryCellRendererExt()
        {
        }

        public override void OnInitializeDisplayView(DataColumnBase dataColumn, UILabel view)
        {
            base.OnInitializeDisplayView(dataColumn, view);
            view.BackgroundColor = UIColor.DarkGray;
            view.TextAlignment = UITextAlignment.Center;
            view.AdjustsFontSizeToFitWidth = true;
            view.TextColor = UIColor.White;
            view.Font = UIFont.FromName("Baskerville-SemiBoldItalic", 20);


        }
    }
{% endhighlight %}

The following screenshot shows the outcome upon execution of the previous code:

![](SfDataGrid_images/Summary17.PNG)

### Customizing caption summary

The data grid customizes the caption summary by overriding [GridCaptionSummaryCellRenderer](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridCaptionSummaryCellRenderer.html).


{% highlight c#%}

// To remove default summary and Add custom summary.

public class Summary : ContentPage
{
    public Summary()
    {
        InitializeComponent();
        dataGrid.CellRenderers.Remove("CaptionSummary");
        dataGrid.CellRenderers.Add("CaptionSummary", new GridCaptionSummaryCellRendererExt());
    }
}

public class GridCaptionSummaryCellRendererExt : GridCaptionSummaryCellRenderer
    {
        public GridCaptionSummaryCellRendererExt()
        {
        }

        public override void OnInitializeDisplayView(DataColumnBase dataColumn, UILabel view)
        {
            base.OnInitializeDisplayView(dataColumn, view);
            view.BackgroundColor = UIColor.DarkGray;
            view.TextAlignment = UITextAlignment.Center;
            view.AdjustsFontSizeToFitWidth = true;
            view.TextColor = UIColor.White;
            view.Font = UIFont.FromName("Baskerville-SemiBoldItalic", 20);
        }
    }
{% endhighlight %}

![](SfDataGrid_images/Summary18.PNG)

You can download the sample demo [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/SummaryDemo707626479).