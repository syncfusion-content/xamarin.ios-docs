---
layout: post
title: Exporting | SfDataGrid | Xamarin.iOS | Syncfusion
description: How to export a SfDataGrid to excel and PDF and it's customizations.
platform: xamarin.ios
control: SfDataGrid
documentation: ug
---

# Exporting

SfDataGrid provides support for exporting the data to excel and PDF with several customization options like custom appearance, excluding specific columns, excluding headers, setting custom row height, setting custom column width, etc. It also provides support for `Grouping`, `Filtering` and `Sorting` when exporting.

In order to use export to excel and export to PDF functionalities of SfDataGrid, add the required assembly references to your application as discussed in the [Assembly deployment](/xamarin-ios/sfdatagrid/getting-started#assembly-deployment) section.

The below code explains how to create and display a SfDataGrid in view.

{% highlight c# %}
// In MyViewController.cs

SfDataGrid SfGrid;
UIButton exportPdf;
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

    var column1 = new GridTextColumn()
    {
        MappingName = "OrderID"
    };
    var column2 = new GridTextColumn()
    {
        MappingName = "CustomerID"
    };
    var column3 = new GridTextColumn()
    {
        MappingName = "Customer"
    };
    var column4 = new GridTextColumn()
    {
        MappingName = "ShipCountry"
    };
         
    SfGrid.Columns.Add(column1);
    SfGrid.Columns.Add(column2);
    SfGrid.Columns.Add(column3);
    SfGrid.Columns.Add(column4);

    exportPdf = new UIButton(UIButtonType.RoundedRect);
    exportPdf.Layer.CornerRadius = 5;
    exportPdf.SetTitleColor(UIColor.Black, UIControlState.Normal);
    exportPdf.SetTitle("Export To Pdf", UIControlState.Normal);
    exportPdf.BackgroundColor = UIColor.FromRGB(212, 208, 200);
    exportPdf.TouchDown += ExportToPdf;

    exportExcel = new UIButton(UIButtonType.RoundedRect);
    exportExcel.SetTitle("Export To Excel", UIControlState.Normal);
    exportExcel.SetTitleColor(UIColor.Black, UIControlState.Normal);
    exportExcel.Layer.CornerRadius = 5;
    exportExcel.BackgroundColor = UIColor.FromRGB(212, 208, 200);
    exportExcel.TouchDown += ExportToExcel;
    this.View.AddSubviews(exportExcel);
    this.View.AddSubviews(exportPdf);
    this.View.AddSubviews(this.SfGrid);
}

public override void ViewDidLayoutSubviews()
{
    this.exportPdf.Frame = new CGRect((this.View.Frame.Left + 15), 10, ((this.View.Frame.Right / 2) - 30), 50);
    this.exportExcel.Frame = new CGRect(((this.View.Frame.Right / 2) + 15), 10, ((this.View.Frame.Right / 2) - 30), 50);
    this.SfGrid.Frame = new CGRect(0, 70, this.View.Frame.Width, this.View.Frame.Height - 70);

    base.ViewDidLayoutSubviews();
}
{% endhighlight %}

## Export to Excel

You can export data to excel by using the `ExportToExcel` method by passing the SfDataGrid as an argument. The following code example illustrates exporting data to excel using the `ExportToExcel` method.

{% highlight c# %}
private void ExportToExcel(object sender, EventArgs e)
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

![](SfDataGrid_images/Exporting_img1.png)

### Exporting Options

You can also export data to excel with various customizing options while exporting the SfDataGrid by passing the grid and [DataGridExcelExportingOption](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption.html) as arguments to the `ExportToExcel` method. The following code example illustrates this.

{% highlight c# %}
DataGridExcelExportingController excelExport = new DataGridExcelExportingController ();
DataGridExcelExportingOption exportOption = new DataGridExcelExportingOption ();
exportOption.ExportColumnWidth = false;
exportOption.DefaultColumnWidth = 150;
var excelEngine = excelExport.ExportToExcel (this.dataGrid, exportOption); 
{% endhighlight %}

SfDataGrid provides you with following properties in `DataGridExcelExportingOption` class to customize the grid while exporting it to excel. 

* [AllowOutlining](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption~AllowOutlining.html) - Specifies whether the groups should export with expand/collapse options or not.
* [AllowSortingAndFiltering](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption~AllowSortingAndFiltering.html) - Specifies whether need to apply excel filtering and sorting for the exported file.
* [ApplyGridStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption~ApplyGridStyle.html) - Specifies whether datagrid gridstyle need to be exported or not.
* [DefaultColumnWidth](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption~DefaultColumnWidth.html) - Gets or sets the default column width for exporting.
* [DefaultRowHeight](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption~DefaultRowHeight.html) - Gets or sets the default row height for exporting.
* [ExcelVersion](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption~ExcelVersion.html) - Exports data to Excel in the specificed workbook version.
* [ExcludedColumns](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption~ExcludedColumns.html) - Specifies list of columns that to be excluded from exporting.
* [ExportColumnWidth](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption~ExportColumnWidth.html) - Gets or sets whether the column widths can be exported or not, if not default column width will be assigned.
* [ExportGroups](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption~ExportGroups.html) - Specifies whether groups to be exported or not.
* [ExportHeader](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption~ExportHeader.html) - Specifies whether header to be exported or not.
* [ExportMode](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption~ExportMode.html) - Specifies whether data should exported as value or text.
* [ExportRowHeight](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption~ExportRowHeight.html) - Gets or sets whether the row heights can be exported or not,if not default row height will be assigned.
* [GroupCaptionStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption~GroupCaptionStyle.html) - Gets or sets groupcaption style for exporting.
* [HeaderStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption~HeaderStyle.html) - Gets or sets headerstyle for exporting.
* [RecordStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption~RecordStyle.html) - Gets or sets recordstyle for exporting.
* [StartColumnIndex](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption~StartColumnIndex.html) - Exports data to the specified column index in Excel.
* [StartRowIndex](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingOption~StartRowIndex.html) - Exports data to the specified column index in Excel.

Note > Grid Styles are not exported when user sets recordstyle , headerstyle , groupstyle for exporting.

### Events

The SfDataGrid provides you the following events for exporting to excel:

* [RowExporting](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingController~RowExporting_EV.html) – This event is raised while exporting a row at the execution time before the row is exported.
* [CellExporting](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridExcelExportingController~CellExporting_EV.html) – This event is raised while exporting a cell at the execution time before the cell is exported.

#### RowExporting

The [DataGridRowExcelExportingEventHandler](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridRowExcelExportingEventHandler.html) delegate allows you to customize the styles for record rows and group caption rows. The `RowExporting` event is triggered with [DataGridRowExcelExportingEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridRowExcelExportingEventArgs.html) that contains the following properties:

* **Range** – Specifies the excel range to be exported. It provides full access to the exporting cell in excel.
* **Record** – Gets the collection of underlying data objects that are exported.
* **RowType** – Specifies the row type by using `ExportRowType` `Enum`. You can use this property to check the row type and apply different styles based on the row type.
* **Worksheet** – Sets the `Worksheet` properties such as sheet protection, gridlines, and so on. 

You can use this event to customize the properties of the grid rows that are exported to excel. The following code example illustrates how to change the background color of the record rows and caption summary rows while exporting.

{% highlight c# %}
//HandlingRowExportingEvent for exporting to excel
DataGridExcelExportingController excelExport = new DataGridExcelExportingController ();
excelExport.RowExporting += excelExport_RowExporting; 

void excelExport_RowExporting (object sender, DataGridRowExcelExportingEventArgs e)
{
    if (e.RowType == ExportRowType.Record) {
        if ((e.Record.Data as OrderInfo).IsClosed)
            e.Range.CellStyle.FillBackground = Syncfusion.XlsIO.ExcelKnownColors.Yellow;
        else
            e.Range.CellStyle.FillBackground = Syncfusion.XlsIO.ExcelKnownColors.LightGreen;
    }

    if (e.RowType == ExportRowType.CaptionSummary) {
        e.Range.CellStyle.FillBackground = Syncfusion.XlsIO.ExcelKnownColors.Grey_25_percent;
    }
}
{% endhighlight %}

![](SfDataGrid_images/Exporting_img2.png)

#### CellExporting

The [DataGridCellExcelExportingEventHandler](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridCellExcelExportingEventHandler.html) delegate allows you to customize the styles for header cells, record cells and group caption cells. The `CellExporting` event is triggered with [DataGridCellExcelExportingEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridCellExcelExportingEventArgs.html) that contains the following properties:

* **CellType** – Specifies the cell type by using `ExportCellType` `Enum`. You can use this property to check the cell type and apply different cell styles based on the cell type.
* **CellValue** – Contains the actual value that is exported to the excel. You can use this value to apply formatting in excel using `Range` property.
* **ColumnName** – Specifies the column name (MappingName) of the exporting cell. You can apply formatting for a particular column by checking the `ColumnName`.
* **Handled** – Determines whether the cell is exported to excel or not.
* **Range** – Specifies the excel range to be exported. It provides full access to the exporting cell in excel.
* **Record** – Gets the collection of underlying data objects that are exported. 

You can use this event to customize the properties of the grid cells that are exported to excel. The following code example illustrates how to customize the background color, foreground color and cell value of the header cells, record cells and caption summary cells while exporting.

{% highlight c# %}
//HandlingCellExportingEvent for exporting to excel
DataGridExcelExportingController excelExport = new DataGridExcelExportingController ();
excelExport.CellExporting += excelExport_CellExporting;  

void excelExport_CellExporting(object sender, DataGridCellExcelExportingEventArgs e)
{
    if (e.CellType == ExportCellType.HeaderCell) {
        e.Range.CellStyle.FillBackground = Syncfusion.XlsIO.ExcelKnownColors.Blue;
        e.Range.CellStyle.FillForeground = Syncfusion.XlsIO.ExcelKnownColors.White;
        e.CellValue = "HeaderCell";
    }

    if (e.CellType == ExportCellType.RecordCell) {
        e.Range.CellStyle.FillBackground = Syncfusion.XlsIO.ExcelKnownColors.Yellow;
        e.Range.CellStyle.FillForeground = Syncfusion.XlsIO.ExcelKnownColors.Black;
        if (e.CellValue is string)
            e.CellValue = "RecordCell";
    }

    if (e.CellType == ExportCellType.GroupCaptionCell) {
        e.Range.CellStyle.FillBackground = Syncfusion.XlsIO.ExcelKnownColors.Grey_25_percent;
        e.Range.CellStyle.FillForeground = Syncfusion.XlsIO.ExcelKnownColors.Blue;
        e.CellValue = "CaptionSummary";
    }
}
{% endhighlight %}

![](SfDataGrid_images/Exporting_img3.png)

## Export to PDF

You can export data to PDF by using the `ExportToPdf` method by passing the SfDataGrid as an argument. The following code example illustrates exporting data to PDF using the `ExportToPdf` method.

{% highlight c# %}
private void ExportToPdf(object sender, EventArgs e)
{
    DataGridPdfExportingController pdfExport = new DataGridPdfExportingController();
    MemoryStream stream = new MemoryStream();
    var doc = pdfExport.ExportToPdf(this.SfGrid);
    doc.Save(stream);
    doc.Close(true);
    Save("DataGrid.pdf", "application/pdf", stream);
}
{% endhighlight %}

![](SfDataGrid_images/Exporting_img4.png)

### Exporting Options

You can also export data to PDF with various customizing options while exporting the SfDataGrid by passing the grid and [DataGridPdfExportingOption](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption.html) as arguments to the `ExportToPdf` method. The following code example illustrates this.

{% highlight c# %}
DataGridPdfExportingController pdfExport = new DataGridPdfExportingController ();
DataGridPdfExportOption exportOption = new DataGridPdfExportOption ();
exportOption.FitAllColumnsInOnePage = true;
var doc = pdfExport.ExportToPdf (this.dataGrid, exportOption); 
{% endhighlight %}

SfDataGrid provides you with following properties in `DataGridPdfExportingOption` class to customize the grid while exporting it to PDF. 

* [ApplyGridStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~ApplyGridStyle.html) - Specifies whether datagrid gridstyle need to be applied or not.
* [DefaultColumnWidth](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~DefaultColumnWidth.html) - Gets or sets the default column width for exporting.
* [DefaultRowHeight](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~DefaultRowHeight.html) - Gets or sets the default row height for exporting.
* [ExcludeColumns](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~ExcludeColumns.html) - Gets or sets the columns that needs to be excluded while exporting.
* [ExportColumnWidth](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~ExportColumnWidth.html) - Gets or sets whether the column widths are automatically assigned or not,if not default column width will be assigned.
* [ExportGroups](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~ExportGroups.html) - Gets or sets whether groups can be exported or not.
* [ExportHeader](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~ExportHeader.html) - Specifies whether header to be exported or not.
* [ExportRowHeight](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~ExportRowHeight.html) - Gets or sets whether the row heights can be exported or not,if not default row height will be assigned.
* [FitAllColumnsInOnePage](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~FitAllColumnsInOnePage.html) - Gets or sets whether the all columns should be fit on a page or not true.
* [GridLineType](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~GridLineType.html) - Gets or sets the type of gridLine.
* [GroupCaptionStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~GroupCaptionStyle.html) - Gets or sets groupcaption style for exporting.
* [HeaderStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~HeaderStyle.html) - Gets or sets headerstyle for exporting.
* [RecordStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~RecordStyle.html) - Gets or sets recordstyle for exporting.
* [RepeatHeaders](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~RepeatHeaders.html) - Gets or sets whether the headers can be repeated in each page or not.

Note > Grid Styles are not exported when user sets recordstyle , headerstyle , groupstyle for exporting.

### Events

The SfDataGrid provides you the following events for `Exporting`:

* [RowExporting](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportingController~RowExporting_EV.html) – This event is raised while exporting a row at the execution time before the row is exported.
* [CellExporting](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportingController~CellExporting_EV.html) – This event is raised while exporting a cell at the execution time before the cell is exported.

#### RowExporting

The [DataGridRowPdfExportingEventHandler](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridRowPdfExportingEventhandler.html) delegate allows you to customize the styles for record rows and group caption rows. The`RowExporting` event is triggered with [DataGridRowPdfExportingEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridRowPdfExportingEventArgs.html) that contains the following properties:

* **PdfGrid** – You can use this property to customize the PdfGrid’s properties such as `Background`, `CellPadding`, `CellSpacing` etc.
* **PdfRow** – Specifies the `PdfGridRow` to be exported. You can use this to customize the properties of particular row. 
* **Record** – Gets the collection of underlying data objects that are exported.
* **RowType** – Specifies the row type by using `ExportRowType` `Enum`. You can use this property to check the row type and apply different styles based on the row type.

You can use this event to customize the properties of the grid rows that are exported to PDF. The following code example illustrates how to change the background color of the record rows and caption summary rows while exporting.

{% highlight c# %}
//HandlingRowExportingEvent for exporting to PDF
DataGridPdfExportingController pdfExport = new DataGridPdfExportingController ();
pdfExport.RowExporting += pdfExport_RowExporting; 

void pdfExport_RowExporting (object sender, DataGridRowPdfExportingEventArgs e)
{
    if (e.RowType == ExportRowType.Record) {
        if ((e.Record.Data as OrderInfo).IsClosed)
            e.PdfRow.Style.BackgroundBrush = PdfBrushes.Yellow;
        else
        e.PdfRow.Style.BackgroundBrush = PdfBrushes.LightGreen;
    }

    if (e.RowType == ExportRowType.CaptionSummary) {
        e.PdfRow.Style.BackgroundBrush = PdfBrushes.LightGray;
    }
} 
{% endhighlight %}

![](SfDataGrid_images/Exporting_img5.png)

#### CellExporting

The [DataGridCellPdfExportingEventHandler](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridCellPdfExportingEventhandler.html) delegate allows you to customize the styles for header cells, record cells and group caption cells. The `CellExporting` event is triggered with [DataGridCellPdfExportingEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.IOS~Syncfusion.SfDataGrid.Exporting.DataGridCellPdfExportingEventArgs.html) that contains the following properties:

* **CellType** – Specifies the cell type by using `ExportCellType` `Enum`. You can use this property to check the cell type and apply different cell styles based on the cell type.
* **CellValue** – Contains the actual value that is exported to the PDF. You can use this value to apply formatting in PDF using `Range` property.
* **ColumnName** – Specifies the column name (MappingName) of the exporting cell. You can apply formatting for a particular column by checking the `ColumnName`.
* **Handled** – Determines whether the cell is exported to PDF or not.
* **PdfGrid** – Specifies the `PDFGridCell` to be exported. You can use this to customize the properties (Background, Foreground, Font, Alignment etc.,) of particular cell.
* **Record** – Gets the collection of underlying data objects that are exported.

You can use this event to customize the properties of the grid cells that are exported to PDF. The following code example illustrates how to customize the background color, foreground color and cell value of the header cells, record cells and caption summary cells while exporting.

{% highlight c# %}
//HandlingCellExportingEvent for exporting to PDF
DataGridPdfExportingController pdfExport = new DataGridPdfExportingController ();
pdfExport.CellExporting += pdfExport_CellExporting;  

void pdfExport_CellExporting(object sender, DataGridCellPdfExportingEventArgs e)
{
    if (e.CellType == ExportCellType.HeaderCell) {
        e.PdfGridCell.Style.BackgroundBrush = PdfBrushes.Blue;
        e.PdfGridCell.Style.TextBrush = PdfBrushes.White;
        e.CellValue = "HeaderCell";
    }

    if (e.CellType == ExportCellType.RecordCell) {
        e.PdfGridCell.Style.BackgroundBrush = PdfBrushes.Yellow;
        e.PdfGridCell.Style.TextBrush = PdfBrushes.Black;
        if (e.CellValue is string)
            e.CellValue = "RecordCell";
    }

    if (e.CellType == ExportCellType.GroupCaptionCell) {
        e.PdfGridCell.Style.BackgroundBrush = PdfBrushes.LightGray;
        e.PdfGridCell.Style.TextBrush = PdfBrushes.Blue;
        e.CellValue = "CaptionSummary";
    }
}
{% endhighlight %}

![](SfDataGrid_images/Exporting_img6.png)

#### HeaderAndFooterExporting

The [PdfHeaderFooterEventHandler](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.PdfHeaderFooterEventHandler.html) delegate allows you to customize the header and footer of the exported PDF. The `HeaderAndFooterExporting` event is triggered with [PdfHeaderFooterEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgridconverter/Syncfusion.SfGridConverter.iOS~Syncfusion.SfDataGrid.Exporting.PdfHeaderFooterEventArgs.html) that contains the following properties:

* **PdfDocumentTemplate** – Specfies the header and footer template for the exported PDF.

The following code example illustrates how to customize the header and footer of the exported PDF document.

{% highlight c#%}
private void ExportToPdf(object sender, EventArgs e)
{
    DataGridPdfExportingController pdfExport = new DataGridPdfExportingController();
    pdfExport.HeaderAndFooterExporting += pdfExport_HeaderAndFooterExporting;
}

private void pdfExport_HeaderAndFooterExporting(object sender, PdfHeaderFooterEventArgs e)
{
    var width = e.PdfPage.GetClientSize().Width;
    PdfPageTemplateElement header = new PdfPageTemplateElement(width, 60);
    var assmbely = Assembly.GetExecutingAssembly();
    var imagestream = assmbely.GetManifestResourceStream("GettingStarted.SyncfusionLogo.jpg");
    PdfImage pdfImage = PdfImage.FromStream(imagestream);
    header.Graphics.DrawImage(pdfImage, new RectangleF(0, 0, width, 50));
    e.PdfDocumentTemplate.Top = header;
}
{% endhighlight %}

## Save a file

The below code snippet explains how to save the converted PDF document and excel sheet in our local device.

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

## Exporting unbound columns

`SfDataGrid.GridUnboundColumns` will be exported as like `SfDataGrid.GridTextColumns` without any specific codes. You can customize the `SfDataGrid.GridUnboundColumns` as like `SfDataGrid.GridTextColumns` using `CellExporting` and `RowExporting` events.

The below code illustrates how to create and export unbound columns.

{% highlight c# %}
var unboundColumn = new GridUnboundColumn()
{
    MappingName = "Unbound",
    Expression = "OrderID",
};

sfGrid.Columns.Add(unboundColumn);
{% endhighlight %}

The below screenshot shows that the unbound column is exported to PDF document along with text columns.
![](SfDataGrid_images/Exporting_img7.png)

The below screenshot shows that the unbound column is exported to excel sheet along with text columns.
![](SfDataGrid_images/Exporting_img8.png)