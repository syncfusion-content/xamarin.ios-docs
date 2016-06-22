---
layout: post
title: Summary | SfDataGrid | Xamarin.iOS | Syncfusion
description: How to apply summaries for the elements in a SfDataGrid.
platform: xamarin.ios
control: SfDataGrid
documentation: UG
---

# Summary

SfDataGrid displays the summaries for each Group using the [CaptionSummaryRowControl](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.CaptionSummaryRowControl.html# “”) 
which carries the information about a particular Group like the Group name, number of items (records) in the Group, etc.

SfDataGrid control allows you to display summaries for each Group. You can derive additional information from your data like Sum, Average, Maximum, Minimum and Count using Caption Summary. These summary values are computed for Groups using [SfDatagrid.GridSummaryRow](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryRow.html# “”) and [SfDatagrid.GridSummaryColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn.html# “”) that implements [ISummaryRow](http://help.syncfusion.com/cr/cref_files/xamarin/data/Syncfusion.Data.Portable~Syncfusion.Data.ISummaryRow.html# “”) and `IsummaryColumn` interface.

SfDataGrid provides below caption summary rows.

Caption Summary – used to display summary information in the caption of the group.

Caption Summaries

SfDataGrid provides built-in support for caption summaries. The caption summary value calculated based on the records in a group and the summary information will be displayed in the caption of group.

###  Formatting built-in caption summary

SfDataGrid also supports setting custom Group Caption Text Format for [CaptionSummaryRows](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.CaptionSummaryRowControl.html# “”). By default the group caption text will be in the format “{ColumnName} : {Key} - {ItemsCount} Items”.
 
 * ColumnName : Displays the grouped column name.
 * Key : Displays the group key value.
 * ItemsCount : Displays the number of items in group.

You can customize this group caption text format by setting the [SfDataGrid.GroupCaptionTextFormat](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~GroupCaptionTextFormat.html# “”) property. The following code example illustrates how to customize group caption text in SfDataGrid.

{% highlight c# %}
//Customized group caption text in German 
dataGrid.GroupCaptionTextFormat = "{ColumnName} : {Key} - {ItemsCount}";

{% endhighlight %}

Below screen shot shows the final outcome of the above code.

![](SfDataGrid_images/CaptureSummary.png)

## Defining the summary row

You can display summary information in row by setting `GridSummaryRow.ShowSummaryInRow` to `true` and defining summary columns. 

The following code example illustrates how to declare the summaries in SfDataGrid for Xamarin.iOS

{% highlight c# %}
GridSummaryRow summaryRow = new GridSummaryRow();
summaryRow.Title = "Total Items:{CaptionSummary}";
summaryRow.ShowSummaryInRow = true;
summaryRow.SummaryColumns.Add{new GridSummaryColumn()
{
    Name="CaptionSummary",
    MappingName="Percentage",
    Format="Count-({Sum:c})",
    SummaryType=SummaryType.DoubleAggregate
});
sfgrid.CaptionSummaryRow= summaryRow;
{% endhighlight %}

The following screenshot shows the final outcome for both values of `ShowSummaryInRow` to `True`.

![](SfDataGrid_images/CaptureRow1.png)

## Defing summary for column 

`SfDataGrid.GridSummaryColumn` is the object of `GridSummaryRow.SummaryColumns` collection that contains the following important properties:

* [Name](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn~Name.html# “”) : Defines name of the `GridSummaryColumn` that helps to denote the `GridSummaryColumn` in `GridSummaryRow` with Title.
* [MappingName](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn~MappingName.html# “”): The corresponding column name that is used for the summary calculation.
* [SummaryType](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn~SummaryType.html# “”): It is the SummaryType (enum) property that helps to define the aggregate type for the summary calculation. DataGrid control provides the following predefined aggregates.

  * CountAggregate.
  * Int32Aggregate.
  * DoubleAggregate.
* [CustomAggregate](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn~CustomAggregate.html# “”): Defines the CustomAggregate class object when the summary type is set as Custom that calculates the custom summaries.
* [Format](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn~Format.html# “”): String property that formats the summary value and displays it. Format property contains two parts that is separated by a colon (:). First part denotes the aggregate function name and second part denotes display format of the summary value.

For example when you declare the format as “{Sum:c}”, the keyword “Sum” denotes the aggregate function name. Every aggregate type has some built-in aggregate function. The aggregate function names in built-in aggregate types are as follows:

1. CountAggregate: Count
2. Int32Aggregate: Count, Max, Min, Average and Sum
3. DoubleAggregate: Count, Max, Min, Average and Sum

You can use these function names only when you define the Format property.
Second part denotes the format. The key word “c” denotes the string format that defines how the summary value is displayed.
To know more about the string format values click [here](http://msdn.microsoft.com/en-us/library/dwhawy9k.aspx# “”).

The following code example illustrates how to declare the summaries in SfDataGrid for Xamarin.iOS

{% highlight c# %}
GridSummaryRow summaryRow = new GridSummaryRow();
summaryRow.Title = "Total Items:{CaptionSummary}";
summaryRow.ShowSummaryInRow = false;
summaryRow.SummaryColumns.Add{new GridSummaryColumn()
{
    Name="CaptionSummary",
    MappingName="Percentage",
    Format="Count-({Sum:c})",
    SummaryType=SummaryType.DoubleAggregate
});
sfgrid.CaptionSummaryRow= summaryRow;
{% endhighlight %}

The [GridSummaryRow.ShowSummaryInRow](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryRow~ShowSummaryInRow.html# “”) property can be set to true or false for displaying the Summary in the entire row or for displaying the summary within the column bounds it is mapped to. 

The following screenshot shows the final outcome for both values of `ShowSummaryInRow` to `False`.

![](SfDataGrid_images/Capturecolum.png)


SfDataGrid also supports setting custom GroupCaptionTextFormat for [CaptionSummaryRows](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.CaptionSummaryRowControl.html# “”). By default the group caption text will be in the format “{ColumnName} : {Key} - {ItemsCount} Items”.
 
 * ColumnName : Displays the grouped column name.
 * Key : Displays the group key value.
 * ItemsCount : Displays the number of items in group.

You can customize this group caption text format by setting the [SfDataGrid.GroupCaptionTextFormat](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~GroupCaptionTextFormat.html# “”) property. The following code example illustrates how to customize groupcaptiontext in SfDataGrid.

{% highlight c# %}
//Customized group caption text in German 
dataGrid.GroupCaptionTextFormat = "{ColumnName} : {Key} - {ItemsCount} Produkte";

{% endhighlight %}

