---
layout: post
title: Exporting | SfDataGrid | Xamarin.iOS | Syncfusion
description: How to export a SfDataGrid to excel and it's customizations.
platform: xamarin.ios
control: SfDataGrid
documentation: ug
---

# Exporting

The SfDataGrid supports exporting the data to Excel with several customization options like custom appearance, excluding specific columns, excluding headers, setting custom row height, setting custom column width, etc. It also supports [Grouping](https://help.syncfusion.com/xamarin-ios/sfdatagrid/grouping), [Filtering](https://help.syncfusion.com/xamarin-ios/sfdatagrid/filtering), and [Sorting](https://help.syncfusion.com/xamarin-ios/sfdatagrid/sorting) when exporting.

To use export to Excel and functionalities of the SfDataGrid, add the required assembly references to your application as discussed in the [Assembly deployment](/xamarin-ios/sfdatagrid/getting-started#assembly-deployment) section.

The following code explains how to create and display a SfDataGrid in view.

{% tabs %}
{% highlight c# %}
// In MyViewController.cs

SfDataGrid SfGrid;
UIButton exportExcel;
        
public MyViewController()
{
    this.SfGrid = new SfDataGrid();
    this.SfGrid.AutoGenerateColumns = false;
    this.SfGrid.SelectionMode = SelectionMode.Single;
    this.SfGrid.ItemsSource = new OrderInfoRepository().OrderInfoCollection;
    this.SfGrid.ShowRowHeader = false;
    this.SfGrid.HeaderRowHeight = 45;
    this.SfGrid.RowHeight = 45;

    var FreightColumn = new GridTextColumn
    {
        MappingName = "Freight",
        HeaderText = "Freight"
    };
    var FirstNameColumn = new GridTextColumn
    {
        MappingName = "FirstName",
        HeaderText = "FirstName",
    };
    var OrderIdColumn = new GridTextColumn
    {
        MappingName = "OrderID",
        HeaderText = "OrderID",
    };
    var EmployeeIdColumn = new GridTextColumn
    {
        MappingName = "EmployeeID",
        HeaderText = "EmployeeID",
    };
    var IsClosedColumn = new GridTextColumn
    {
        MappingName = "IsClosed",
        HeaderText = "IsClosed",
    };
    SfGrid.Columns.Add(OrderIdColumn);
    SfGrid.Columns.Add(FirstNameColumn);
    SfGrid.Columns.Add(FreightColumn);
    SfGrid.Columns.Add(EmployeeIdColumn);
    SfGrid.Columns.Add(IsClosedColumn);

    exportExcel = new UIButton(UIButtonType.RoundedRect);
    exportExcel.SetTitle("Export To Excel", UIControlState.Normal);
    exportExcel.SetTitleColor(UIColor.Black, UIControlState.Normal);
    exportExcel.Layer.CornerRadius = 5;
    exportExcel.BackgroundColor = UIColor.FromRGB(212, 208, 200);
    exportExcel.TouchDown += ExportToExcel_Clicked;
    this.View.AddSubviews(exportExcel);
    this.View.AddSubviews(this.SfGrid);
}

public override void ViewDidLayoutSubviews()
{
    this.exportExcel.Frame = new CGRect(((this.View.Frame.Right / 2) + 15), 10, ((this.View.Frame.Right / 2) - 30), 50);
    this.SfGrid.Frame = new CGRect(0, 70, this.View.Frame.Width, this.View.Frame.Height - 70);
    base.ViewDidLayoutSubviews();
}
{% endhighlight %}
{% endtabs %}

## Export to Excel

You can export data to Excel by using the [ExportToExcel](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingController~ExportToExcel.html) method by passing the SfDataGrid as an argument. 

{% tabs %}
{% highlight c# %}
private void ExportToExcel_Clicked(object sender, EventArgs e)
{
    DataGridExcelExportingController excelExport = new DataGridExcelExportingController();
    var excelEngine = excelExport.ExportToExcel(this.SfGrid);
    var workbook = excelEngine.Excel.Workbooks[0];
    MemoryStream stream = new MemoryStream();
    workbook.SaveAs(stream);
    workbook.Close();
    excelEngine.Dispose();
    Save("DataGrid.xlsx", "application/msexcel", stream);
}
{% endhighlight %}
{% endtabs %}

![Export to Excel](SfDataGrid_images/Excel/ExcelExport.png)

## Exporting Options

You can also export data to Excel with various customizing options while exporting the SfDataGrid by passing the grid and [DataGridExcelExportingOption](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html) as arguments to the `ExportToExcel` method. .

{% tabs %}
{% highlight c# %}
DataGridExcelExportingController excelExport = new DataGridExcelExportingController ();
DataGridExcelExportingOption exportOption = new DataGridExcelExportingOption ();
exportOption.ExportColumnWidth = false;
exportOption.DefaultColumnWidth = 150;
var excelEngine = excelExport.ExportToExcel (this.dataGrid, exportOption); 
{% endhighlight %}
{% endtabs %}

The SfDataGrid provides you with several properties in `DataGridExcelExportingOption` class to customize the grid while exporting it to Excel. 

### AllowOutlining

If you export the data grid with grouping applied, you can enable the group expand or collapse option in the Excel sheet by setting the [DataGridExcelExportingOption.AllowOutlining](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_AllowOutlining) to `true`. The default value of this property is false so, you cannot expand or collapse the group in the Excel sheet by default.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.AllowOutlining = true; 
{% endhighlight %}
{% endtabs %}

### AllowSortingAndFiltering

The SfDataGrid allows exporting the data grid to Excel with sorting and filtering options enabled on the column header in the Excel sheet by setting the [DataGridExcelExportingOption.AllowSortingAndFiltering](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_AllowSortingAndFiltering) to `true`. The default value of this property is false.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.AllowSortingAndFiltering = true; 
{% endhighlight %}
{% endtabs %}

### ApplyGridStyle

The SfDataGrid allows exporting the data with the applied GridStyle by setting the [DataGridExcelExportingOption.ApplyGridStyle](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_ApplyGridStyle) to `true`. By default, the data will be exported without the GridStyle.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.ApplyGridStyle = true; 
{% endhighlight %}
{% endtabs %}

![ApplyGridStyle](SfDataGrid_images/Excel/GridStyle.png) 

### DefaultColumnWidth

The SfDataGrid allows customizing the column width in Excel file using the [DataGridExcelExportingOption.DefaultColumnWidth](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_DefaultColumnWidth) property. The `DefaultColumnWidth` value will be applied to all the columns in the Excel sheet.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.DefaultColumnWidth = 100; 
{% endhighlight %}
{% endtabs %}

### DefaultRowHeight

The SfDataGrid allows customizing the row height in Excel file by using the [DataGridExcelExportingOption.DefaultRowHeight](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_DefaultRowHeight) property. The `DefaultRowHeight` value will be applied to all the rows in the Excel sheet.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.DefaultRowHeight = 50; 
{% endhighlight %}
{% endtabs %}

### ExcludedColumns

By default, all the columns (including hidden columns) in the SfDataGrid will be exported to Excel. To exclude some particular columns while exporting to Excel, add those columns to the [DataGridExcelExportingOption.ExcludeColumns](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_ExcludedColumns) list.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
var list = new List<string>();
list.Add("OrderID");
list.Add("LastName");
option.ExcludedColumns = list;
{% endhighlight %}
{% endtabs %}

![ExcludedColumns](SfDataGrid_images/Excel/ExcludeColumns.png) 

### ExportColumnWidth

By default, the data grid columns will be exported to Excel with the value of the `DataGridExcelExportingOption.DefaultColumnWidth` but, you can also export the data grid to Excel with the exact column widths from the SfDataGrid by setting the [DataGridExcelExportingOption.ExportColumnWidth](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_ExportColumnWidth) to `true`. The default value of the `ExportColumnWidth` property is false.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.ExportColumnWidth = true;
{% endhighlight %}
{% endtabs %}

### ExportRowHeight

By default, the data grid rows will be exported to Excel with the value of the `DataGridExcelExportingOption.DefaultRowHeight` but, you can also export the data grid to Excel with the exact row heights from the SfDataGrid by setting the [DataGridExcelExportingOption.ExportRowHeight](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_ExportRowHeight) to `true`. The default value of the `ExportRowHeight` property is false.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.ExportRowHeight = true;
{% endhighlight %}
{% endtabs %}

### ExcelVersion

The SfDataGrid allows exporting the data to Excel in specific versions by using the [DataGridExcelExportingOption.ExcelVersion](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_ExcelVersion) property.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.ExcelVersion = Syncfusion.XlsIO.ExcelVersion.Excel2013;
{% endhighlight %}
{% endtabs %}

### ExportGroups

By default, all the groups in the data grid will be exported to Excel sheet. To export the data grid without Groups, set the [DataGridExcelExportingOption.ExportGroups](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_ExportGroups) property to `false`.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.ExportGroups = true;
{% endhighlight %}
{% endtabs %}

* ExportGroups is true

![ExportGroupsistrue](SfDataGrid_images/Excel/GroupingExcel.png) 

* ExportGroups is false

![ExportGroupsisfalse](SfDataGrid_images/Excel/ExcelExport.png) 

### ExportHeader

By default, the column headers will be exported to Excel sheet. To export the SfDataGrid without the column headers, set the [DataGridExcelExportingOption.ExportHeader](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_ExportHeader) to `false`.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.ExportHeader = false;
{% endhighlight %}
{% endtabs %}

![ExportHeader](SfDataGrid_images/Excel/ExcludeHeader.png) 

### ExportTableSummary

By default, table summaries in the data grid will be exported to Excel. To export the SfDataGrid without table summaries, set the [DataGridExcelExportingOption.ExportTableSummary](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_ExportTableSummary) property to `false`.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.ExportTableSummary = false;
{% endhighlight %}
{% endtabs %}

![ExportTableSummary](SfDataGrid_images/Excel/ExcludeSummary.png)  

### BottomTableSummaryStyle

The SfDataGrid supports exporting the bottom TableSummary with custom style by using the [DataGridExcelExportingOption.BottomTableSummaryStyle](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_BottomTableSummaryStyle) property.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.BottomTableSummaryStyle = new ExportCellStyle()
{
    BackgroundColor = UIColor.Purple,
    BorderColor = UIColor.White,
    ForegroundColor = UIColor.Green,
};
{% endhighlight %}
{% endtabs %}

### GroupCaptionStyle

The SfDataGrid supports exporting the GroupCaptionSummaries with custom style by using the [DataGridExcelExportingOption.GroupCaptionStyle](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_GroupCaptionStyle) property.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.GroupCaptionStyle = new ExportCellStyle()
{
    BackgroundColor = UIColor.Yellow,
    BorderColor = UIColor.Green,
    ForegroundColor = UIColor.Green,
};
{% endhighlight %}
{% endtabs %}

![GroupCaptionStyle](SfDataGrid_images/Excel/SummaryStyle.png)  

### HeaderStyle

The SfDataGrid allows exporting the column headers with custom style by using the [DataGridExcelExportingOption.HeaderStyle](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_HeaderStyle) property.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.HeaderStyle = new ExportCellStyle()
{
    BackgroundColor = UIColor.White,
    BorderColor = UIColor.Black,
    ForegroundColor = UIColor.Black,
};
{% endhighlight %}
{% endtabs %}

### RecordStyle

The SfDataGrid allows exporting the records with custom style by using the [DataGridExcelExportingOption.RecordStyle](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_RecordStyle) property.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.RecordStyle = new ExportCellStyle()
{
    BackgroundColor = UIColor.Yellow,
    BorderColor = UIColor.Black,
    ForegroundColor = UIColor.Black,
};
{% endhighlight %}
{% endtabs %}

![RecordStyle](SfDataGrid_images/Excel/RecordHeaderStyle.png) 

### TopTableSummaryStyle

The SfDataGrid supports exporting the top TableSummary with custom style by using the [DataGridExcelExportingOption.TopTableSummaryStyle](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_TopTableSummaryStyle) property.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.TopTableSummaryStyle = new ExportCellStyle()
{
    BackgroundColor = UIColor.Purple,
    BorderColor = UIColor.White,
    ForegroundColor = UIColor.White,
};
{% endhighlight %}
{% endtabs %}

![TopTableSummaryStyle](SfDataGrid_images/Excel/SummaryStyle.png)  

### ExportGroupSummary

By default, the `GroupSummary` rows in the data grid will be exported to Excel. To export the `SfDataGrid` without group summaries, set the [DataGridExcelExportingOption.ExportGroupSummary](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_ExportGroupSummary) property to `false`.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
// Set false here to export the DataGrid without GroupSummary rows. The default value is true.
//option.ExportGroupSummary = false;
{% endhighlight %}
{% endtabs %}

![ExportGroupSummary](SfDataGrid_images/Excel/GroupSummaryExcel.png) 

### GroupSummaryStyle 

`SfDataGrid` supports exporting the `GroupSummary` rows with custom style by using the [DataGridExcelExportingOption.GroupSummaryStyle](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_GroupSummaryStyle) property.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.GroupSummaryStyle = new ExportCellStyle()
{
    BackgroundColor = UIColor.Red,
    BorderColor = UIColor.Yellow,
    ForegroundColor = UIColor.White,
};
{% endhighlight %}
{% endtabs %}

![GroupSummaryStyle](SfDataGrid_images/Excel/GroupSummaryStyle.png) 

### StartColumnIndex

By default, the exported SfDataGrid will start from the 0th column in the Excel sheet but, you can specify the start column in the Excel sheet using the [DataGridExcelExportingOption.StartColumnIndex](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_StartColumnIndex) property.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.StartColumnIndex = 2;
{% endhighlight %}
{% endtabs %}

### StartRowIndex

By default, the exported SfDataGrid will start from the 0th row in the Excel sheet but, you can specify the start row in the Excel sheet using the [DataGridExcelExportingOption.StartRowIndex](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_StartRowIndex) property.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.StartRowIndex = 5;
{% endhighlight %}
{% endtabs %}

### ExportAllPages

While exporting to Excel using the SfDataPager inside the SfDataGrid, by default it will export only the current page. However, you can export all the pages by setting the [DataGridExcelExportingOption.ExportAllPages](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_ExportAllPages) to `true`. The default value for this property is false.

{% tabs %}
{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.ExportAllPages = true;
{% endhighlight %}
{% endtabs %}

![ExportAllPages is false](SfDataGrid_images/Excel/ExportAllPage.png)  

* ExportAllPages is true

![ExportAllPages is true](SfDataGrid_images/Excel/CurrentPageExport.png) 

## Events

The SfDataGrid provides you the following events for exporting to excel:

* [RowExporting](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingController~RowExporting_EV.html): Raised while exporting a row at the execution time.
* [CellExporting](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingController~CellExporting_EV.html): Raised while exporting a cell at the execution time.

### RowExporting

The [DataGridRowExcelExportingEventHandler](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridRowExcelExportingEventHandler.html) delegate allows customizing the styles for the record rows, group caption rows, and group summary rows. The `RowExporting` event is triggered with [DataGridRowExcelExportingEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridRowExcelExportingEventArgs.html) that contains the following properties:

* [Range](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridRowExcelExportingEventArgs~Range.html): Specifies the Excel range to be exported. It provides full access to the exporting cell in Excel.
* [Record](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridRowExcelExportingEventArgs~Record.html): Gets the collection of the exported underlying data objects.
* [RowType](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridRowExcelExportingEventArgs~RowType.html): Specifies the row type by using `ExportRowType` `Enum`. You can use this property to check the row type and apply different styles based on the row type.
* [Worksheet](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridRowExcelExportingEventArgs~WorkSheet.html): Sets the `Worksheet` properties such as sheet protection, gridlines, and so on. 

You can use this event to customize the properties of the grid rows exported to Excel. The following code example illustrates how to change the background color of the record rows, caption summary rows, and group summary rows when exporting.

{% tabs %}
{% highlight c# %}
//HandlingRowExportingEvent for exporting to excel
DataGridExcelExportingController excelExport = new DataGridExcelExportingController ();
excelExport.RowExporting += excelExport_RowExporting; 

void excelExport_RowExporting (object sender, DataGridRowExcelExportingEventArgs e)
{
    if (e.RowType == ExportRowType.Record) {
        if ((e.Record.Data as OrderInfo).IsClosed)
            e.Range.CellStyle.ColorIndex = Syncfusion.XlsIO.ExcelKnownColors.Yellow;
        else
            e.Range.CellStyle.ColorIndex = Syncfusion.XlsIO.ExcelKnownColors.LightGreen;
    }
    
    // You can also set the desired background colors for the CaptionSummary row and GroupSummary row as shown below
    //if (e.RowType == ExportRowType.CaptionSummary) {
        //e.Range.CellStyle.ColorIndex = Syncfusion.XlsIO.ExcelKnownColors.Grey_25_percent;
    //}

    //if (e.RowType == ExportRowType.GroupSummary) {
        //e.Range.CellStyle.ColorIndex = Syncfusion.XlsIO.ExcelKnownColors.Red;
    //}
}
{% endhighlight %}
{% endtabs %}

![RowExporting](SfDataGrid_images/Excel/RowEvent.png)  

### CellExporting

The [DataGridCellExcelExportingEventHandler](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridCellExcelExportingEventHandler.html) delegate allows customizing the styles for the header cells, record cells, group caption cells, and group summary cells. The `CellExporting` event is triggered with [DataGridCellExcelExportingEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridCellExcelExportingEventArgs.html) that contains the following properties:

* [CellType](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridCellExcelExportingEventArgs~CellType.html): Specifies the cell type by using `ExportCellType` `Enum`. You can use this property to check the cell type and apply different cell styles based on the cell type.
* [CellValue](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridCellExcelExportingEventArgs~CellValue.html): Contains the actual value exported to the Excel. You can use this value to apply formatting in Excel using the `Range` property.
* [ColumnName](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridCellExcelExportingEventArgs~ColumnName.html): Specifies the column name (MappingName) of the exporting cell. You can apply formatting for a particular column by checking the `ColumnName`.
* [Handled](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridCellExcelExportingEventArgs~Handled.html): Determines whether the cell is exported to Excel or not.
* [Range](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridCellExcelExportingEventArgs~Range.html): Specifies the Excel range to be exported. It provides full access to the exporting cell in Excel.
* [Record](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridCellExcelExportingEventArgs~Record.html): Gets the collection of the exported underlying data objects. 

You can use this event to customize the properties of the grid cells exported to Excel. The following code example illustrates how to customize the background color, foreground color, and cell value of the header cells, record cells, caption summary cells, and group summary cells when exporting.

{% tabs %}
{% highlight c# %}
//HandlingCellExportingEvent for exporting to excel
DataGridExcelExportingController excelExport = new DataGridExcelExportingController ();
excelExport.CellExporting += excelExport_CellExporting;  

void excelExport_CellExporting(object sender, DataGridCellExcelExportingEventArgs e)
{
    if (e.CellType == ExportCellType.HeaderCell) {
        e.Range.CellStyle.ColorIndex = Syncfusion.XlsIO.ExcelKnownColors.Blue;
        e.Range.CellStyle.PatternColorIndex = Syncfusion.XlsIO.ExcelKnownColors.White;
        e.Range.CellStyle.BeginUpdate();
       e.Range.CellStyle.Borders.LineStyle = Syncfusion.XlsIO.ExcelLineStyle.Dash_dot_dot;
        e.Range.CellStyle.Borders[ExcelBordersIndex.DiagonalDown].LineStyle = ExcelLineStyle.Dash_dot_dot;
        e.Range.CellStyle.Borders[ExcelBordersIndex.DiagonalUp].LineStyle = ExcelLineStyle.Dash_dot_dot;
        e.Range.CellStyle.Borders.Color = ExcelKnownColors.Black;
        e.Range.CellStyle.EndUpdate();
    }

    if (e.CellType == ExportCellType.RecordCell) {
        e.Range.CellStyle.ColorIndex = Syncfusion.XlsIO.ExcelKnownColors.Yellow;
        e.Range.CellStyle.PatternColorIndex = Syncfusion.XlsIO.ExcelKnownColors.Black;
        e.Range.CellStyle.BeginUpdate();
       e.Range.CellStyle.Borders.LineStyle = Syncfusion.XlsIO.ExcelLineStyle.Dash_dot_dot;
        e.Range.CellStyle.Borders[ExcelBordersIndex.DiagonalDown].LineStyle = ExcelLineStyle.Dash_dot_dot;
        e.Range.CellStyle.Borders[ExcelBordersIndex.DiagonalUp].LineStyle = ExcelLineStyle.Dash_dot_dot;
        e.Range.CellStyle.Borders.Color = ExcelKnownColors.Black;
        e.Range.CellStyle.EndUpdate();
    }
    
    // You can also set the desired values for the CaptionSummary rows and GroupSummary rows as shown below
    //if (e.CellType == ExportCellType.GroupCaptionCell) {
        //e.Range.CellStyle.ColorIndex = Syncfusion.XlsIO.ExcelKnownColors.Grey_25_percent;
        //e.Range.CellStyle.PatternColorIndex = Syncfusion.XlsIO.ExcelKnownColors.Blue;
        //e.Range.CellStyle.BeginUpdate();
        //e.Range.CellStyle.Borders.LineStyle = Syncfusion.XlsIO.ExcelLineStyle.Dash_dot_dot;
        //e.Range.CellStyle.Borders[ExcelBordersIndex.DiagonalDown].LineStyle = ExcelLineStyle.Dash_dot_dot;
        //e.Range.CellStyle.Borders[ExcelBordersIndex.DiagonalUp].LineStyle = ExcelLineStyle.Dash_dot_dot;
        //e.Range.CellStyle.Borders.Color = ExcelKnownColors.Black;
        //e.Range.CellStyle.EndUpdate();
    //}

    //if (e.CellType == ExportCellType.GroupSummaryCell){
        //e.Range.CellStyle.ColorIndex = Syncfusion.XlsIO.ExcelKnownColors.Light_yellow;
        //e.Range.CellStyle.PatternColorIndex = Syncfusion.XlsIO.ExcelKnownColors.Black;
        //e.Range.CellStyle.BeginUpdate();
        //e.Range.CellStyle.Borders.LineStyle = Syncfusion.XlsIO.ExcelLineStyle.Dashed;
        //e.Range.CellStyle.Borders[ExcelBordersIndex.DiagonalDown].LineStyle = ExcelLineStyle.Dashed;
        //e.Range.CellStyle.Borders[ExcelBordersIndex.DiagonalUp].LineStyle = ExcelLineStyle.Dashed;
        //e.Range.CellStyle.Borders.Color = ExcelKnownColors.Red;
        //e.Range.CellStyle.EndUpdate();
    //}
}
{% endhighlight %}
{% endtabs %}

![CellExporting](SfDataGrid_images/Excel/RecordHeaderStyle.png)


### Custom Borders

The SfDataGrid allows exporting the data to Excel with custom borders style in the Excel sheet by handling the `CellExporting` event. 

{% tabs %}
{% highlight c# %}
private void ExcelExport_CellExporting(object sender, DataGridCellExcelExportingEventArgs e)
{
    if (e.CellType == ExportCellType.RecordCell)
    {
        e.Range.CellStyle.BeginUpdate();
        e.Range.CellStyle.Borders.LineStyle = Syncfusion.XlsIO.ExcelLineStyle.Dash_dot_dot;
        e.Range.CellStyle.Borders[ExcelBordersIndex.DiagonalDown].LineStyle = ExcelLineStyle.Dash_dot_dot;
        e.Range.CellStyle.Borders[ExcelBordersIndex.DiagonalUp].LineStyle = ExcelLineStyle.Dash_dot_dot;
        e.Range.CellStyle.Borders.Color = ExcelKnownColors.Black;
        e.Range.CellStyle.EndUpdate();
    }
}
{% endhighlight %}
{% endtabs %}

![Custom Borders](SfDataGrid_images/Excel/RecordHeaderStyle.png)

## Save a File

The following code snippet explains how to save the converted Excel sheet in our local device.

{% tabs %}
{% highlight c# %}
private void Save(string filename, string contentType, MemoryStream stream)
{
    string exception = string.Empty;
    string path = Environment.GetFolderPath(Environment.SpecialFolder.Personal);
    string filePath = Path.Combine(path, filename);
    try
    {
        FileStream fileStream = File.Open(filePath, FileMode.Create);
        stream.Position = 0;
        stream.CopyTo(fileStream);
        fileStream.Flush();
        fileStream.Close();
    }
    catch (Exception e)
    {
        exception = e.ToString();
    }
    
    if (contentType == "application/html" || exception != string.Empty)
        return;
    
    UIViewController currentController = UIApplication.SharedApplication.KeyWindow.RootViewController;
    while (currentController.PresentedViewController != null)
        currentController = currentController.PresentedViewController;
    UIView currentView = currentController.View;

    QLPreviewController qlPreview = new QLPreviewController();
    QLPreviewItem item = new QLPreviewItemBundle(filename, filePath);
    qlPreview.DataSource = new PreviewControllerDS(item);

    currentController.PresentViewController((UIViewController)qlPreview, true, (Action)null);
}

public class QLPreviewItemFileSystem : QLPreviewItem
{
    string _fileName, _filePath;

    public QLPreviewItemFileSystem(string fileName, string filePath)
    {
        _fileName = fileName;
        _filePath = filePath;
    }

    public override string ItemTitle
    {
        get
        {
            return _fileName;
        }
    }
    
    public override NSUrl ItemUrl
    {
        get
        {
            return NSUrl.FromFilename(_filePath);
        }
    }
}

public class QLPreviewItemBundle : QLPreviewItem
{
    string _fileName, _filePath;
	
    public QLPreviewItemBundle(string fileName, string filePath)
    {
        _fileName = fileName;
        _filePath = filePath;
    }

    public override string ItemTitle
    {
        get
        {
            return _fileName;
        }
    }
    
    public override NSUrl ItemUrl
    {
        get
        {
            var documents = NSBundle.MainBundle.BundlePath;
	     var lib = Path.Combine(documents, _filePath);
            var url = NSUrl.FromFilename(lib);
            return url;
	 }
    }
}

public class PreviewControllerDS : QLPreviewControllerDataSource
{
    private QLPreviewItem _item;

    public PreviewControllerDS(QLPreviewItem item)
    {
        _item = item;
    }

    public override nint PreviewItemCount (QLPreviewController controller)
    {
        return (nint)1;
    }

    public override IQLPreviewItem GetPreviewItem (QLPreviewController controller, nint index)
    {
        return _item;
    }
}
{% endhighlight %}
{% endtabs %}

## Exporting Unbound rows

By default, the Unbound rows will not be exported to the excel document. However, you can export the unbound rows to excel by setting the [DataGridExcelExportingOption.ExportUnboundRows](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html#Syncfusion_SfDataGrid_Exporting_DataGridExcelExportingOption_ExportUnboundRows) property as `true`.

{% highlight c# %}
DataGridExcelExportingOption option = new DataGridExcelExportingOption();
option.ExportUnboundRows = true;
{% endhighlight %}

## Exporting Unbound Columns

The [SfDataGrid.GridUnboundColumns](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridUnboundColumn.html) will be exported as [SfDataGrid.GridTextColumns](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridTextColumn.html) without any specific codes. You can customize the `SfDataGrid.GridUnboundColumns` as `SfDataGrid.GridTextColumns` using the `CellExporting` and `RowExporting` events.

The following code illustrates how to create and export unbound columns.

{% tabs %}
{% highlight c# %}
var unboundColumn = new GridUnboundColumn()
{
    MappingName = "Unbound",
    Expression = "OrderID",
};

sfGrid.Columns.Add(unboundColumn);
{% endhighlight %}
{% endtabs %}

The following screenshot shows that the unbound column is exported to excel sheet along with text columns.

![Exporting Unbound Columns](SfDataGrid_images/Exporting_img8.png)

## Exporting the selected rows of SfDataGrid

SfDataGrid allows you to export only the currently selected rows in the grid to the worksheet using the [DataGridExcelExportingController.ExportToExcel](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfGridConverter.ios~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingController~ExportToExcel.html) method by passing the instance of the SfDataGrid and [SfDataGrid.SelectedItems](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~SelectedItems.html) collection as an argument.

Refer the below code to export the selected rows alone to Excel.

{% highlight c# %}

    private void ExPortToExcel(object sender, EventArgs e)
        {
            DataGridExcelExportingController excelExport = new DataGridExcelExportingController();
            ObservableCollection<object> selectedItems = dataGrid.SelectedItems;
            var excelEngine = excelExport.ExportToExcel(this.dataGrid, selectedItems);
            var workbook = excelEngine.Excel.Workbooks[0];
            MemoryStream stream = new MemoryStream();
            workbook.SaveAs(stream);
            workbook.Close();
            excelEngine.Dispose();
            Save("DataGrid.xlsx", "application/msexcel", stream);
        }

{% endhighlight %}

The following screenshot shows that the selected rows are exported to excel sheet.
![Exporting the selected rows of SfDataGrid](SfDataGrid_images/Excel/SelectedItems_ExportToExcel.png)
