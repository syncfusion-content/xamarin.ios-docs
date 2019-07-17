---
layout: post
title: Getting started | SfDataGrid | Xamarin.iOS | Syncfusion
description: Getting started with SfDataGrid.
platform: xamarin.ios
control: SfDataGrid
documentation: ug
---

# Getting Started

This section provides a quick overview for working with SfDataGrid for Xamarin.iOS. You will walk through the entire process of creating a real world SfDataGrid.


## Assembly deployment

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Essential Studio Installed location}\Essential Studio\{{ site.releaseversion }}\Xamarin\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\Xamarin\lib

N> Assemblies can be found in unzipped package location in Mac

## NuGet configuration

To install the required NuGet for the SfDataGrid control in the application, configure the NuGet packages of the Syncfusion components.

Refer to the following KB to configure the NuGet packages of the Syncfusion components:

[How to configure package source and install Syncfusion NuGet packages in an existing project?](https://www.syncfusion.com/kb/7441/how-to-configure-package-source-and-install-syncfusion-nuget-packages-in-an-existing-project)

The following NuGet package should be installed to use the SfDataGrid control in the application.

<table>
<tr>
<th> Project </th>
<th> Required package </th>
</tr>
<tr>
<td> Xamarin.iOS </td>
<td> Syncfusion.Xamarin.SfDataGrid.iOS</td>
</tr>
</table>

### Adding SfDataGrid Reference

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfDataGrid to your project, open the NuGet package manager in Visual Studio, and search for [Syncfusion.Xamarin.SfDataGrid.IOS](https://www.nuget.org/packages/Syncfusion.Xamarin.SfDataGrid.ios/#), and then install it.

![SfDataGrid in nuget.org](SfDataGrid_images/SfDataGrid_IOS.png)

To know more about obtaining our components, refer to this [link](https://help.syncfusion.com/xamarin-ios/introduction/download-and-installation). Also, if you prefer to manually refer the assemblies instead of NuGet, refer the list of assemblies mentioned in the table below.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>Xamarin.iOS</td>
<td>Syncfusion.Linq.iOS.dll<br/>Syncfusion.SfDataGrid.iOS.dll<br/>Syncfusion.GridCommon.Portable.dll<br/>Syncfusion.SfNumericTextBox.iOS.dll<br/></td>
</tr>
</table>

To export the SfDataGrid to Excel and PDF formats, search for [Syncfusion.Xamarin.SfGridConverter.IOS](https://www.nuget.org/packages/Syncfusion.Xamarin.SfGridConverter.ios/) in the NuGet package manager, and then install it.

![DataGridExport in Xamarin.iOS](SfDataGrid_images/SfGridConverter_iOS.png)

If you prefer to manually refer the assemblies instead of NuGet, refer the list of assemblies mentioned in the table below.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>Xamarin.iOS</td>
<td>Syncfusion.SfGridConverter.iOS.dll<br/>pcl\Syncfusion.Compression.Portable.dll<br/>pcl\Syncfusion.Pdf.Portable.dll<br/>pcl\Syncfusion.XlsIO.Portable.dll<br/></td>
</tr>
</table>

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Create a simple SfDataGrid 

This section explains how to create a SfDataGrid and configure it. The SfDataGrid control can be configured entirely in C# code or using story board. This is how the final output will look like on iOS devices.
 
![SfDataGrid in Xamarin.iOS](SfDataGrid_images/GettingStarted.png)
 
You can download the entire source code of this demo for Xamarin.iOS from [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStarted-670371090). 

In this walk through, you will create a new application that contains the SfDataGrid which includes the below topics.

* [Creating the project](#creating-the-project) 
* [Adding SfDataGrid in Xamarin.iOS](#adding-sfdatagrid-in-xamarinios)
* [Create data model](#create-datamodel-for-the-sfdatagrid)  
* [Binding data](#binding-data-to-sfdatagrid) 
* [Defining columns](#defining-columns) 
* [Sorting](#sorting) 
* [Grouping](#grouping) 
* [Selection](#selection)

## Creating the project

Create a new iOS application in Xamarin Studio or Visual Studio for Xamarin.iOS.

## Adding SfDataGrid in Xamarin.iOS using story board

1. Add a new story board inside the project.
2. Drag the SfDataGrid control from toolbox and drop it into the story board. Preview for SfDataGrid will be shown.
3. Open the properties window of SfDataGrid and set the required properties.

![SfDataGrid renderer in designer page](SfDataGrid_images/StoryBoard_SfDataGrid_ios.gif)

### Setting the SfDataGrid properties in story board

Set the identity name and required properties for SfDataGrid in story board.

![SfDataGrid properties](SfDataGrid_images/Storyboard_property_SfDataGrid_ios.png)

Set the identity name and required properties for SfDataPager in story board.

![SfDataGrid properties](SfDataGrid_images/Storyboard_property_SfDataPager_ios.png)

{% tabs %}

{% highlight c# %}
namespace Grid
{
	public partial class MyViewController : UIViewController
	{
		ViewModel viewModel;
		public MyViewController() : base("MyViewController",null)
		{
		}
		public override void ViewDidLoad()
		{
 			base.ViewDidLoad();
 			// Perform any additional setup loading the view, typically from a nib.
 			viewModel = new ViewModel();
 			sfPager.Source = viewModel.OrdersInfo;
 			sfGrid.ItemSource = sfPager.PagedSource;
		}
		public override void DidReceiveMemoryWarning()
		{
			base.DidReceiveMemoryWarning();
			// Release any cached data, images, etc that aren't in use.
		}
	}
}

{% endhighlight %}

{% endtabs %}

You can download the entire source code of this sample [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/custom_designer_sfdatagrid_ios-764618167).

Refer to this link to know the properties that can be configured using story board for SfDataGrid.

## Adding SfDataGrid in Xamarin.iOS using C# code

1. Add the required assembly references to the project as discussed in the [Assembly deployment](#assembly-deployment) section.

2. Import SfDataGrid control namespace Syncfusion.SfDataGrid.

3. Create an instance of SfDataGrid control and add as a SubView to a UIViewController.

{% tabs %}
{% highlight c# %}
using Syncfusion.SfDataGrid; 
public partial class GettingStartedViewController : UIViewController
{
    SfDataGrid dataGrid;

    static bool UserInterfaceIdiomIsPhone {
        get { return UIDevice.CurrentDevice.UserInterfaceIdiom == UIUserInterfaceIdiom.Phone; }
    }

    public GettingStartedViewController ()
        : base (UserInterfaceIdiomIsPhone ? "GettingStartedViewController_iPhone" : "GettingStartedViewController_iPad", null)
    {
        dataGrid = new SfDataGrid ();
        dataGrid.HeaderRowHeight = 45;
        dataGrid.RowHeight = 45;
    }

    public override void ViewDidLoad ()
    {
        base.ViewDidLoad ();
        dataGrid.Frame = new CGRect (0, 0, View.Frame.Width, View.Frame.Height);
        View.AddSubview (dataGrid);
    }
}
{% endhighlight %}
{% endtabs %}

You can also set HeaderRowHeight and RowHeight for SfDataGrid using story board.

![SfDataGrid properties](SfDataGrid_images/GettingStarted_HeaderRowHeight_RowHeight_ios.png)

Run the application to render the following output. 

![SfDataGrid with RowHeight and HeaderRowHeight](SfDataGrid_images/SfDataGridWithoutTopPadding.png)

The [Frame](https://developer.xamarin.com/api/property/UIKit.UIView.Frame/) is used to arrange a view in Xamarin.iOS. By default a view in Xamarin.iOS will be arranged without any padding from the title bar. Hence the content of the arranged view will overlap with the title bar if the top position of its `Frame` is set as `0`. 

To overcome the above problem, the top position of the view's `Frame` has to be customized accordingly to position the view below the title bar in iOS. Refer the below code example in which the top position of the SfDataGrid's `Frame` is set to 30 to overcome the problem.

{% tabs %}
{% highlight c# %}
public override void ViewDidLoad ()
{
      base.ViewDidLoad ();
      dataGrid.Frame = new CGRect (0, 30, View.Frame.Width, View.Frame.Height);
      View.AddSubview (dataGrid);
 }
 {% endhighlight %}
{% endtabs %}

 Run the application with the above code to render the following output. 

![SfDataGrid with top padding](SfDataGrid_images/SfDataGridWithTopPadding.png)

## Create DataModel for the SfDataGrid

SfDataGrid is a data-bound control. Hence you must create a data model to bind it to the control. 

Create a simple data source as shown in the following code example in a new class file and save it as OrderInfo.cs file. 

{% tabs %}
{% highlight c# %}
public class OrderInfo
{
    private int orderID;
    private string customerID;
    private string customer;
    private string shipCity;
    private string shipCountry;

    public int OrderID {
        get { return orderID; }
        set { this.orderID = value; }
    }

    public string CustomerID {
        get { return customerID; }
        set { this.customerID = value; }
    }

    public string ShipCountry {
        get { return shipCountry; }
        set { this.shipCountry = value; }
    }

    public string Customer {
        get { return this.customer; }
        set { this.customer = value; }
    }

    public string ShipCity {
        get { return shipCity; }
        set { this.shipCity = value; }
    }

    public OrderInfo (int orderId, string customerId, string country, string customer, string shipCity)
    {
        this.OrderID = orderId;
        this.CustomerID = customerId;
        this.Customer = customer;
        this.ShipCountry = country;
        this.ShipCity = shipCity;
    }
} 
{% endhighlight %}
{% endtabs %}

N> If you want your data model to respond to property changes, then implement `INotifyPropertyChanged` interface in your model class

Create a model repository class with OrderInfo collection property initialized with required number of data objects in a new class file as shown in the following code example and save it as OrderInfoRepository.cs file.

{% tabs %}
{% highlight c# %}
public class OrderInfoRepository
{
    private ObservableCollection<OrderInfo> orderInfo;
    public ObservableCollection<OrderInfo> OrderInfoCollection {
        get { return orderInfo; }
        set { this.orderInfo = value; }
    }

    public OrderInfoRepository ()
    {
        orderInfo = new ObservableCollection<OrderInfo> ();
        this.GenerateOrders ();
    }

    private void GenerateOrders ()
    {
        orderInfo.Add (new OrderInfo (1001, "Maria Anders", "Germany", "ALFKI", "Berlin"));
        orderInfo.Add (new OrderInfo (1002, "Ana Trujillo", "Mexico", "ANATR", "Mexico D.F."));
        orderInfo.Add (new OrderInfo (1003, "Ant Fuller", "Mexico", "ANTON", "Mexico D.F."));
        orderInfo.Add (new OrderInfo (1004, "Thomas Hardy", "UK", "AROUT", "London"));
        orderInfo.Add (new OrderInfo (1005, "Tim Adams", "Sweden", "BERGS", "Lula"));
        orderInfo.Add (new OrderInfo (1006, "Hanna Moos", "Germany", "BLAUS", "Mannheim"));
        orderInfo.Add (new OrderInfo (1007, "Andrew Fuller", "France", "BLONP", "Strasbourg"));
        orderInfo.Add (new OrderInfo (1008, "Martin King", "Spain", "BOLID", "Madrid"));
        orderInfo.Add (new OrderInfo (1009, "Lenny Lin", "France", "BONAP", "Marseilles"));
        orderInfo.Add (new OrderInfo (1010, "John Carter", "Canada", "BOTTM", "Tsawassen"));
        orderInfo.Add (new OrderInfo (1011, "Martin King", "UK", "AROUT", "London"));
        orderInfo.Add (new OrderInfo (1012, "Anne Wilson", "Germany", "BLAUS", "Mannheim"));
        orderInfo.Add (new OrderInfo (1013, "Hanna Kyle", "France", "BLONP", "Strasbourg"));
        orderInfo.Add (new OrderInfo (1014, "Gina Irene", "UK", "AROUT", "London"));
    }
}
{% endhighlight %}
{% endtabs %}

## Binding data to SfDataGrid

In order to bind the data source of the SfDataGrid, set the [SfDataGrid.ItemsSource](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~ItemsSource.html) property as shown below. You can bind the data source of the SfDataGrid as follows. 

The following code example binds the collection created in previous step to `SfDataGrid.ItemsSource` property.

{% tabs %}
{% highlight c# %}
OrderInfoRepository viewModel = new OrderInfoRepository ();
dataGrid.ItemsSource = viewModel.OrderInfoCollection; 
{% endhighlight %}
{% endtabs %}
Now run the application to render the following output.

![Data Virtualization in SfDataGrid for Xamarin.iOS](SfDataGrid_images/Overview.png)

## Defining Columns

By default, the SfDataGrid automatically creates columns for all the properties in the data source. The type of the column generated depends on the type of data in the column. When the columns are auto-generated, you can handle the [SfDataGrid.AutoGeneratingColumn](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~AutoGeneratingColumn_EV.html) event to customize or cancel the columns before they are added to the Columns collection in SfDataGrid.
 
You can also define the columns manually by setting the [SfDataGrid.AutoGenerateColumns](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~AutoGenerateColumns.html) property to false and by adding the `GridColumn` objects to the [SfDataGrid.Columns](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~AutoGenerateColumns.html) collection. The following code example illustrates how this can be done. 

{% tabs %}
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
customerColumn.HeaderText = "Customer";

GridTextColumn countryColumn = new GridTextColumn ();
countryColumn.MappingName = "ShipCountry";
countryColumn.HeaderText = "Ship Country";

dataGrid.Columns.Add (orderIdColumn);
dataGrid.Columns.Add (customerIdColumn);
dataGrid.Columns.Add (customerColumn);
dataGrid.Columns.Add (countryColumn); 
{% endhighlight %}
{% endtabs %}

## Sorting

SfDataGrid allows you to apply sorting on its data by setting the [SfDataGrid.AllowSorting](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~AllowSorting.html) property to true.
 
You can also set the sorting for SfDataGrid using story board.
 
![Sorting via story board in SfDataGrid fo Xamarin.iOS](SfDataGrid_images/GettinStarted_AllowSorting_StoryBoard_SfDataGrid.png)
 
 {% tabs %}
{% highlight c# %}
dataGrid.AllowSorting = true; 
{% endhighlight %}
{% endtabs %}
Run the application and touch the header cell to sort the data and the following output will be displayed.
 
![Sorting in SfDataGrid in Xamarin.iOS](SfDataGrid_images/Sorting.png)

You can also configure sorting by adding the column to the [SfDataGrid.SortColumnDescriptions](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~SortColumnDescriptions.html) collection as below.

{% tabs %}
{% highlight c# %}
dataGrid.SortColumnDescriptions.Add (new SortColumnDescription () { ColumnName = "CustomerID" });
{% endhighlight %}
{% endtabs %}

## Grouping

SfDataGrid allows you to group a column by adding the column to the [SfDataGrid.GroupColumnDescriptions](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~SortColumnDescriptions.html) collection as shown below.

{% tabs %}
{% highlight c# %}
dataGrid.GroupColumnDescriptions.Add (new GroupColumnDescription () { ColumnName = "ShipCountry" });
{% endhighlight %}
{% endtabs %}

Run the application to render the following output. 

![Grouping in SfDatGrid in Xamarin.iOS](SfDataGrid_images/Grouping.png)

## Selection

SfDataGrid allows you to select the row/rows by setting the [SfDataGrid.SelectionMode](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~SelectionMode.html) property. You can set the `SfDataGrid.SelectionMode` property to single, multiple, single deselect or none based on your requirements. Information about the row/rows selected can be tracked using [SfDataGrid.SelectedItem](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~SelectedItem.html) and [SfDataGrid.SelectedItems](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~SelectedItems.html) properties.


## Loading SfDataGrid with customized height and width

SfDataGrid can be loaded with specific height and width by specifying the height and width of the `SfDataGrid.Frame` property.

To load SfDataGrid with specific height and width, follow the code example:
{% tabs %}
{% highlight c# %}
public override void ViewDidLayoutSubviews()
{
    dataGrid.Frame = new CGRect(85, 130, 200, 380);
    base.ViewDidLayoutSubviews();
}
{% endhighlight %}
{% endtabs %}

You can also set the custom height and width to SfDataGrid using story board.

![Custom width and height via story board in SfDataGrid for Xamarin.iOS](SfDataGrid_images/GettingStarted_Custom_Width_and_Height_Storyboard_SfDatagrid_iOS.png)

The following screenshot shows how the SfDataGrid is loaded with specific height and width: 

![SfDataGrid with specific heigt and width](SfDataGrid_images/Loading_with specific_height_and_width.png)

## Properties configured using story board

<table>
<tr>
<th> Properties</th>
<th> Attribute Name</th>
</tr>

<tr><td>AlternatingRowColor</td><td>Alternating Row Color</td></tr>
<tr><td>AlternationCount</td><td>Alternation Count</td></tr>
<tr><td>AllowPullToRefresh</td> <td>Allow Pull To Refresh</td></tr>
<tr><td>AllowLoadMore</td><td>Allow Load More</td></tr>
<tr><td>AllowEditing</td><td>Allow Editing</td></tr>
<tr><td>AllowSorting</td><td>Allow Sorting</td></tr>
<tr><td>AllowMultiSorting</td><td>Allow Multi Sorting</td></tr>
<tr><td>AllowTriStateSorting</td><td>Allow Tri State Sorting</td></tr>
<tr><td>AllowDraggingColumn</td><td>Allow Dragging Column</td></tr>
<tr><td>AllowDraggingRow</td><td>Allow Dragging Row</td></tr>
<tr><td>AllowResizingColumn</td><td>Allow Resizing Column</td></tr>
<tr><td>AutoGenerateColumns</td><td>Auto Generate Columns</td></tr>
<tr><td>AutoGenerateColumnsMode</td><td>Auto Generate Columns Mode</td></tr>
<tr><td>AutoEllipsisMode</td><td>Auto Ellipsis Mode</td></tr>
<tr><td>CellBorderStyle</td><td>Cell Border Style</td></tr>
<tr><td>ColumnSizer</td><td>Column Sizer</td></tr>
<tr><td>DefaultColumnWidth</td><td>Default Column Width</td></tr>
<tr><td>DataFetchSize</td><td>Data Fetch Size</td></tr>
<tr><td>EditTapAction</td><td>Edit Tap Action</td></tr>
<tr><td>EditorSelectionBehavior</td><td>Editor Selection Behavior</td></tr>
<tr><td>EnableDataVirtualization</td><td>Enable Data Virtualization</td></tr>
<tr><td>FrozenRowsCount</td><td>Frozen Rows Count</td></tr>
<tr><td>FrozenColumnsCount</td><td>Frozen Columns Count</td></tr>
<tr><td>GroupCaptionTextFormat</td><td>Group Caption Text Format</td></tr>
<tr><td>GroupingMode</td><td>Grouping Mode</td></tr>
<tr><td>HeaderRowHeight</td><td>Header Row Height</td></tr>
<tr><td>IndentColumnWidth</td><td>Indent Column Width</td></tr>
<tr><td>Orientation</td><td>Orientation</td></tr>
<tr><td>NumericButtonBackground</td><td>Numeric Button Background</td></tr>
<tr><td>NumericButtonCount</td><td>Numeric Button Count</td></tr>
<tr><td>PageCount</td><td>Page Count</td></tr>
<tr><td>PageSize</td><td>Page Size</td></tr>
<tr><td>ResizingMode</td><td>Resizing Mode</td></tr>
<tr><td>RowHeight</td><td>Row Height</td></tr>
<tr><td>RowHeaderWidth</td><td>Row Header Width</td></tr>
<tr><td>ScrollingMode</td><td>Scrolling Mode</td></tr>
<tr><td>SelectionForeground</td><td>Selection Foreground</td></tr>
<tr><td>SelectionMode</td><td>Selection Mode</td></tr>
<tr><td>SelectedIndex</td><td>Selected Index</td></tr>
<tr><td>ShowRowHeader</td><td>Show Row Header</td></tr>
<tr><td>ShowColumnWhenGrouped</td><td>Show Column When Grouped</td></tr>
<tr><td>SortTapAction</td><td>Sort Tap Action</td></tr>
<tr><td>UseOnDemandPaging</td><td>Use On Demand Paging</td></tr>
</table>