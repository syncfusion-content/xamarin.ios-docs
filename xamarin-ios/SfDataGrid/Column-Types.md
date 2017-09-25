---
layout: post
title: Column Types | SfDataGrid | Xamarin.iOS | Syncfusion
description: What are all the different types of column and it's properties and customizations in a SfDataGrid.
platform: xamarin.ios
control: SfDataGrid
documentation: UG
---

# Column Types

SfDataGrid contains two types of column each with its own functionalities. You can use any column based on your requirements.
 
The below table describes you the types of column and its purpose of usage in SfDataGrid.

<table>
<tr>
<th>Column Type</th>
<th>Description</th>
</tr>
<tr>
<td>GridColumn</td>
<td>Abstract class. Base column type of all the columns in the SfDataGrid.</td>
</tr>
<tr>
<td>GridTextColumn</td>
<td>To be used to display string or numbers in each row.</td>
</tr>
<tr>
<td>TemplateColumn (i.e. GridTextColumn with UserCellType)</td>
<td>To be used when you want to customize your column based on your requirements.</td>
</tr>
<tr>
<td>GridSwitchColumn</td>
<td>To be used when you want to display switch in each row.</td>
</tr>
<tr>
<td>GridImageColumn</td>
<td>To be used when you want to display an image in each row.</td>
</tr>
<tr>
<td>GridNumericColumn</td>
<td>To be used when you want to display a numeric data.</td>
</tr>
<tr>
<td>GridDateTimeColumn</td>
<td>To be used when you want to display the date time value.</td>
</tr>
<tr>
<td>GridPickerColumn</td>
<td>To be used when you want to display the IEnumerable data using Picker.</td>
</tr>
</table>


## GridColumn

[GridColumn](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn.html) is the base column type of all the columns in the SfDataGrid, hence `GridColumn` properties are used by all the columns. The following sub-sections explains you about the properties in the `GridColumn` and the customizations that can be done using those properties.

### MappingName

[GridColumn.MappingName](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~MappingName.html) associates the GridColumn with a property available in the underlying data source. While setting `MappingName` alone to the SfDataGrid, `GridColumn.DisplayBinding` will be automatically generated based on the `MappingName`. Data Manipulation operations like sorting, filtering, grouping will be done based on the `MappingName` property.

### Header customizations

#### HeaderCellTextSize

The FontSize for the content of header cell in the `GridColumn` can be customized by using the [GridColumn.HeaderCellTextSize](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~HeaderCellTextSize.html) property. The default font size of the header cells in SfDataGrid is 14.

#### HeaderFont

The FontFamily for the content of header cell in the `GridColumn` can be customized by using the [GridColumn.HeaderFont](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~HeaderFont.html) property. The default value font used in SfDataGrid is `Helvetica-Bold`.

#### HeaderText

[GridColumn.HeaderText](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~HeaderText.html) specifies the text displayed in the column header. If `HeaderText` is not defined, the `GridColumn.MappingName` will be assigned to the `HeaderText` and will be displayed as column header.

#### HeaderTextAlignment
You can get or set the TextAlignment of the header cell in the `GridColumn` by using the [GridColumn.HeaderTextAlignment](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~HeaderTextAlignment.html) property. The default alignment for the header cells in SfDataGrid is `Center`.

#### HeaderTemplate

SfDataGrid allows you to customize the header cell based on your requirement by using the [GridColumn.HeaderTemplate](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~HeaderTemplate.html) property.

The following code example shows you how to customize the header cell by loading a template in the header cell.

{% highlight c# %}

UILabel label = new UILabel();
label.Text = "Order ID";
label.TextAlignment = UITextAlignment.Center;

GridTextColumn column = new GridTextColumn()
{
    MappingName = "OrderID",
    HeaderTemplate = label
};

{% endhighlight %}

#### HeaderTextMargin

SfDataGrid allows you to get or set the padding for the header cell by using [GridColumn.HeaderTextMargin](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~HeaderTextMargin.html) property. 

The following code example shows you how to set the`HeaderTextMargin` property.

{% highlight c# %}

GridTextColumn orderId = new GridTextColumn();
orderId.MappingName = "OrderID";
orderId.HeaderTextMargin = 15;

GridTextColumn employeeId = new GridTextColumn();
employeeId.MappingName = "EmployeeID";
employeeId.HeaderTextMargin = new Thickness(15, 0, 0, 0);

{% endhighlight %}


### Column Width

SfDataGrid allows you to customize the width of each `GridColumn` in the [SfDataGrid.Columns](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.Columns.html) collection. You can customize the column width by using the [GridColumn.Width](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~Width.html) property. By default this property will not be assigned any value and the `GridColumn` renders in view based on the value of [DefaultColumnWidth](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~DefaultColumnWidth.html) property in SfDataGrid.

N> You can set the `IsHidden` property as `True` instead of setting column width as `0` to hide a column.

Customizing the width for auto generated columns as shown below.

{% highlight c# %}
// AutoGenerateColumn

dataGrid.AutoGeneratingColumn += DataGrid_AutoGeneratingColumn;

void dataGrid_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e){
if (e.Column.MappingName == "OrderID") {
    e.Column.Width = 100;
    }
}

// Manually generated column

dataGrid.Columns.Add(new GridTextColumn() { MappingName = "OrderID" ,Width = 100 });

{% endhighlight %}

### IsHidden 
SfDataGrid allows you to hide a particular column using [GridColumn.IsHidden](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~IsHidden.html) property. The default value of the `IsHidden` property is `False`. 

N> You can set the `IsHidden` property as `True` instead of setting column width as `0` to hide a column.

The following code example shows you how to hide the column using `IsHidden` property.

{% highlight c# %}
// AutoGenerate Column

dataGrid.AutoGeneratingColumn += DataGrid_AutoGeneratingColumn;

void dataGrid_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e){
if (e.Column.MappingName == "OrderID") {
    e.Column.IsHidden = true;
    }
}

// Manually generated column

dataGrid.Columns.Add(new GridTextColumn() { MappingName = "OrderID", IsHidden = true});
{% endhighlight %}

### TextMargin

SfDataGrid allows you to get or set the padding for the [GridCell](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridCell.html) by using [GridColumn.TextMargin](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~TextMargin.html) property. 

The following code example shows you how to set the`TextMargin` property.

{% highlight c# %}

GridTextColumn orderId = new GridTextColumn();
orderId.MappingName = "OrderID";
orderId.TextMargin = 15;

GridTextColumn employeeId = new GridTextColumn();
employeeId.MappingName = "EmployeeID";
employeeId.TextMargin = new Thickness(0, 0, 25, 0);

{% endhighlight %}


## GridTextColumn

[GridTextColumn](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridTextColumn.html) is derived from `GridColumn` and hence it inherits all the properties of `GridColumn`. Each of the record cells in `GridTextColumn` displays text based on the `MappingName` which associates the column with a property in the data source.

The following code example creates `GridTextColumn`.

{% highlight c# %}
dataGrid.Columns.Add(new GridTextColumn() { MappingName = "OrderID" });
{% endhighlight %}

The below topics explain you about the customizations that can be done in the `GridTextColumn` in SfDataGrid.

### Formatting

SfDataGrid allows you to format the value displayed in the `GridColumn` by using the [GridColumn.Format](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~Format.html) property. Assign the FormatString to this property based on the type of the property the `GridColumn` is associated with to format the value. You can use different [StringFormats](http://msdn.microsoft.com/en-us/library/fbxft59x(v=vs.90).aspx) to customize the value displayed in the record cells.

The following code example shows you how to apply formatting for a `GridTextColumn`.

{% highlight c# %}
dataGrid.Columns.Add (new GridTextColumn () { 
    MappingName = "Freight",
    Format = "C"
});

dataGrid.Columns.Add (new GridTextColumn () { 
    MappingName = "ShippingDate",
    Format = "dd/MM/yyyy"
});
{% endhighlight %}

N> For AutoGenerated columns the Formatting can be applied by handling the [SfDataGrid.AutoGeneratingColumn](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~AutoGenerateColumns.html) event.

#### Formatting GridTextColumn with different Culture

SfDataGrid allows you to apply different [CultureInfo](https://developer.xamarin.com/api/type/System.Globalization.CultureInfo/) for the `GridColumns` by using the [GridColumn.CultureInfo](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~CultureInfo.html) property. Assign the FormatString to this property based on the type of the property the GridColumn is associated with to format the value. You can use different `StringFormats` to customize the value displayed in the record cells.

The following code example shows you how to apply different cultures for a `GridColumns`.

{% highlight c# %}
dataGrid.Columns.Add (new GridTextColumn () { 
    MappingName = "Freight",
    Format = "C",
    CultureInfo = new CultureInfo("en-US")
});

dataGrid.Columns.Add (new GridTextColumn () { 
    MappingName = "OrderID",
    Format = "C",
    CultureInfo = new CultureInfo("en-GB")
}); 
{% endhighlight %}

For auto generated columns this is achievable by handling the `SfDataGrid.AutoGeneratingColumn` event. The following code example shows you how to apply different cultures for auto generated `GridColumns`.

{% highlight c# %}
void GridAutoGeneratingColumns(object sender, AutoGeneratingColumnArgs e)
{
    if (e.Column.MappingName == "Freight") {
        e.Column.Format = "C";
        e.Column.CultureInfo = new CultureInfo ("en-US");
    } else if (e.Column.MappingName == "OrderID") {
        e.Column.Format = "C";
        e.Column.CultureInfo = new CultureInfo ("en-GB");
    }
} 
{% endhighlight %}

### Font and Alignment options

#### CellTextSize

The FontSize for the content of record cells in `GridColumn` can be customized by using the [GridColumn.CellTextSize](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~CellTextSize.html) property. The default font size of the record cells in SfDataGrid is 14.

#### RecordFont

The FontFamily for the content of header cell in the `GridColumn` can be customized by using the [GridColumn.RecordFont](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~RecordFont.html) property. The default value font used in SfDataGrid is `HelveticaNeue`.

#### TextAlignment

You can get or set the TextAlignment of the header cell in the GridColumn by using the [GridColumn.TextAlignment](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~TextAlignment.html) property. The default alignment for the record cells in SfDataGrid is `Center`.

#### LineBreakMode

You can wrap the record cell value when the text for the record cells exceeds the content area by setting [GridColumn.LineBreakMode](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~LineBreakMode.html) as `LineBreakMode.WordWrap`

The following code example shows how to use `GridSwitchColumn`.
 
{% tabs %}
{% highlight c# %}
dataGrid.Columns[0].LineBreakMode = LineBreakMode.WordWrap; 
{% endhighlight %}
{% endtabs %} 


## TemplateColumn

TemplateColumn is actually the GridTextColumn with `UserCellType` specified and hence it inherits all the properties of GridColumn. It allows you to extend the functionality of GridColumns with your own view by creating custom GridCell to render in the column.

The following code example shows how to create a TemplateColumn.

{% highlight c# %}
GridTextColumn customerIdColumn = new GridTextColumn ();
customerIdColumn.UserCellType = typeof(CustomCell);
customerIdColumn.MappingName = "CustomerID";
customerIdColumn.HeaderText = "Customer ID";
dataGrid.Columns.Add(customerIdColumn);
{% endhighlight %}

In order to create a template column in SfDataGrid, you need to specify the [UserCellType](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~UserCellType.html) of the column. `UserCellType` is the type of the view to be used in the `GridColumn` and it must be derived from the `GridCell`. (i.e. a custom GridCell which hosts the view of your own requirement).
 
The following code example shows you how to create a custom GridCell and use it in a template column.

{% highlight c# %}
//Creating a Template Column 
GridTextColumn customerIdColumn = new GridTextColumn ();
customerIdColumn.UserCellType = typeof(CustomCell);
customerIdColumn.MappingName = "CustomerID";
customerIdColumn.HeaderText = "Customer ID";
dataGrid.Columns.Add(customerIdColumn);

//Creating Custom GridCell
public class CustomCell : GridCell
{
    UILabel label;

    public CustomCell ()
    {
        label = new UILabel ();
        this.AddSubview (label);
        this.CanRenderUnLoad = false;
    }

    protected override void UnLoad ()
    {
        this.RemoveFromSuperview ();
    }

    public override void LayoutSubviews ()
    {
        base.LayoutSubviews ();
        this.label.Frame = new CGRect(Bounds.Left, Bounds.Top, Bounds.Width, Bounds.Height);
        this.label.Text = DataColumn.CellValue.ToString ();
    }
}
{% endhighlight %}

The following screenshot shows how template columns are used in SfDataGrid

![](SfDataGrid_images/TemplateColumns.png)

## Row Header 

RowHeader is a special column which is placed as first cell of each row and it will always be frozen. To enable the RowHeader in SfDataGrid, you need to set the [SfDataGrid.ShowRowHeader](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~ShowRowHeader.html) property as `true`.

Further, SfDataGrid allows you to customize the row header width using the [SfDataGrid.RowHeaderWidth](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~RowHeaderWidth.html) property. The default value of `SfDataGrid.RowHeaderWidth` is 20.

The below code example illustrates how to enable and customize the row header in SfDataGrid.

{% highlight c# %}

dataGrid.ShowRowHeader = true;
dataGrid.RowHeaderWidth = 50;

{% endhighlight %}

## GridSwitchColumn

The [GridSwitchColumn](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridSwitchColumn.html) is derived from [GridColumn](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn.html), and hence it inherits all the properties of `GridColumn`. It loads a [UISwitch](https://developer.xamarin.com/api/type/MonoTouch.UIKit.UISwitch/) as the content of record cells in the column and responds to value changes in it. You can change the underlying data source by toggling the values shown in the `UISwitch`. To create `GridSwitchColumn` in SfDataGrid the property corresponding to the column in the underlying collection must be of type [bool](https://msdn.microsoft.com/en-us/library/system.boolean(v=vs.110).aspx).

The following code example shows how to use `GridSwitchColumn`.
 
{% highlight c# %}
dataGrid = new SfDataGrid();
GridSwitchColumn switchColumn = new GridSwitchColumn()
{
    HeaderText = "Is Closed",
    MappingName = "IsClosed"
};
data.Column.Add(switchColumn);
{% endhighlight %}

{% highlight c# %}
// Model class
public class OrderInfo
{
    private bool _isClosed;

    public bool IsClosed
    {
        get { return _isClosed; }
        set
        {
            this._isClosed = value;
        }
    }
}

// ViewModel class
public class ViewModel
{
    public ViewModel()
    {
        GetOrderDetails(50);
    }

    #region ItemsSource

    private ObservableCollection<OrderInfo> ordersInfo;

    public ObservableCollection<OrderInfo> OrdersInfo
    {
        get { return ordersInfo; }
        set { this.ordersInfo = value; }
    }

    #endregion

    #region ItemSource Generator

    public void GetOrderDetails(int count)
    {
        var orderDetails = new ObservableCollection<OrderInfo>();
        for (int i = 1; i <= count; i++)
        {
            var order = new OrderInfo()
            {
                IsClosed = (i % 2) == 0 ? true : false
            };
            orderDetails.Add(order);
        }
        ordersInfo = orderDetails;
    }

    #endregion
} 
{% endhighlight %}
![](SfDataGrid_images/SwitchColumn.jpg)

## GridImageColumn

[GridImageColumn](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridImageColumn.html) is derived from [GridColumn](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn.html), and hence it inherits all the properties of `GridColumn`. It displays images as cell content of a column. To create `GridImageColumn` in SfDataGrid the property corresponding to the column in the underlying collection must be of type [UIImage](https://developer.xamarin.com/api/type/MonoTouch.UIKit.UIImage/).

The [ImageMapStream](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.ImageMapStream.html) converts the memory stream to image data, which in turn is converted to `UIImage` by the [ToUIImage](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.Imagehelper~ToUIImage.html) extension method of the [ImageHelper](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.Imagehelper.html) static class.  

The following code example shows how to create a memory stream and use it to load images(embedded resource) in GridImageColumn using the above mentioned methods.
 
{% highlight c# %}
GridImageColumn imageColumn = new GridImageColumn();
imageColumn.MappingName = "Image";
imageColumn.HeaderText = "Image";
{% endhighlight %}

{% highlight c# %}
// Model class
public class OrderInfo
{
    private UIImage image;

    public UIImage Image
    {
        get { return this.=image; }
        set
        {
            this.image = value;
            RaisePropertyChanged("Image");
        }
    }
}

// ViewModel class
public class ViewModel
{
    public ViewModel()
    {
        GetOrderDetails(50);
    }

    #region ItemsSource

    private ObservableCollection<OrderInfo> ordersInfo;

    public ObservableCollection<OrderInfo> OrdersInfo
    {
        get { return ordersInfo; }
        set { this.ordersInfo = value; }
    }

    #endregion

    #region ItemSource Generator

    public void GetOrderDetails(int count)
    {
        var orderDetails = new ObservableCollection<OrderInfo>();
        for (int i = 1; i <= count; i++)
        {
            var order = new OrderInfo()
            {
                Image = ImageHelper.ToUIImage(new ImageMapStream(LoadResource("Image" + (i % 29) + ".png").ToArray())),// Need to give the image path properly
            };
            orderDetails.Add(order);
        }
        ordersInfo = orderDetails;
    }
    
    // Create memory stream
    public MemoryStream LoadResource (String Name)
	{
		MemoryStream memory = new MemoryStream ();

		var assembly = Assembly.GetExecutingAssembly ();

		var path = String.Format ("GettingStarted.Resources.{0}", Name);

		var aStream = assembly.GetManifestResourceStream (path);

		aStream.CopyTo (memory);

		return memory;
	}
    #endregion
}
{% endhighlight %}

![](SfDataGrid_images/ImageColumn.jpg)

N> The images should have its BuildAction set as EmbeddedResource since we are getting the image as stream from an [Assembly.GetManifestResourceStream](https://developer.xamarin.com/api/member/System.Reflection.Assembly.GetManifestResourceStream/p/System.Type/System.String/) in the LoadResource method.

## GridDateTimeColumn

The [GridDateTimeColumn](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridDateTimeColumn.html) is derived from [GridColumn](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn.html) thereby inheriting all the properties of `GridColumn`. It displays the date information as the content of a column. To create `SfDataGrid.GridDateTimeColumn` in SfDataGrid, the property corresponding to the column in the underlying collection must be of type [DateTime](https://msdn.microsoft.com/en-us/library/system.datetime(v=vs.110).aspx). You can enable or disable editing for the particular column by setting the [GridColumn.AllowEditing](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~AllowEditing.html) property to true or false. In the editing mode it displays [SfDatePicker](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.Renderers.SfDatePicker.html) element which is a custom view that enables you to scroll through a list of dates between the [GridDateTimeColumn.MinimumDate](https://help.syncfusion.com/cr/cref_files/xamarin-iOS/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridDateTimeColumn~MinimumDate.html) and [GridDateTimeColumn.MaximumDate](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridDateTimeColumn~MaximumDate.html) and select one from it. 

{% highlight c# %}
dataGrid = new SfDataGrid();
GridDateTimeColumn dateColumn = new GridDateTimeColumn()
{
    MappingName = "ShippedDate",
    HeaderText = "Shipped Date",
    Format = "d"
};
dataGrid.Columns.Add(dateColumn);
{% endhighlight %}

{% highlight c# %}
// Model class
public class OrderInfo
{
    private DateTime shippedDate;

    public DateTime ShippedDate
    {
        get { return shippedDate; }
        set
        {
            shippedDate = value;
            RaisePropertyChanged("ShippedDate");
        }
    }
}

// ViewModel class
public class ViewModel
{
    private List<DateTime> OrderedDates;

    public ViewModel()
    {
        GetOrderDetails(50);
    }

    #region ItemsSource

    private ObservableCollection<OrderInfo> ordersInfo;

    public ObservableCollection<OrderInfo> OrdersInfo
    {
        get { return ordersInfo; }
        set { this.ordersInfo = value; }
    }

    #endregion

    #region ItemSource Generator

    private List<DateTime> GetDateBetween(int startYear, int endYear, int count)
    {
        List<DateTime> date = new List<DateTime>();
        Random d = new Random(1);
        Random m = new Random(2);
        Random y = new Random(startYear);
        for (int i = 0; i < count; i++)
        {
            int year = y.Next(startYear, endYear);
            int month = m.Next(3, 13);
            int day = d.Next(1, 31);
            date.Add(new DateTime(year, month, day));
        }
        return date;
    }

    public void GetOrderDetails(int count)
    {
        var orderDetails = new ObservableCollection<OrderInfo>();
        this.OrderedDates = GetDateBetween(2000, 2014, count);
        for (int i = 1; i <= count; i++)
        {
            var order = new OrderInfo()
            {
                ShippedDate = this.OrderedDates[i - 1],
            };
            orderDetails.Add(order);
        }
        ordersInfo = orderDetails;
    }

    #endregion
}
{% endhighlight %}

![](SfDataGrid_images/DateTimeColumn.jpg)

## GridPickerColumn

The [GridPickerColumn](https://help.syncfusion.com/cr/cref_files/xamarin-iOS/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridPickerColumn.html) is derived from [GridColumn](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn.html) thereby inheriting all the properties of `GridColumn`. It displays a list of items in the form of a picker as the content of a column. You can enable or disable editing for the particular column by setting the [GridColumn.AllowEditing](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~AllowEditing.html) property to true or false. In the editing mode it displays [GridPicker](https://help.syncfusion.com/cr/cref_files/xamarin-iOS/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.Renderers.GridPicker.html) element which is a custom view that enables you to scroll through a list of values from the underlying collection and select one from it. The data source to Picker can be set by using [GridPickerColumn.ItemsSource](https://help.syncfusion.com/cr/cref_files/xamarin-iOS/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridPickerColumn~ItemsSource.html) property. The picker column can be populated with data by the following ways.

* Collection of primitive types
* Collection of user defined types (Custom objects)

![](SfDataGrid_images/PickerColumn.jpg)

### Collection of primitive types

You can create a `GridPickerColumn` and set its `ItemsSource` property to a simple collection to display the collection items in the picker drop down.
The following code example shows you how to load the `GridPickerColumn` with a simple string collection.

{% highlight c# %}
dataGrid = new SfDataGrid();
GridPickerColumn pickerColumn = new GridPickerColumn()
{
    BindingContext = viewModel,
    ItemsSource = viewModel.CustomerNames,
    MappingName = "DealerName",    
    HeaderText = "Dealer Name"

};
dataGrid.Columns.Add(pickerColumn);
{% endhighlight %}

{% highlight c# %}
// ViewModel class
public class ViewModel
{
    public ObservableCollection<string> CustomerNames { get; set; }

    public ViewModel()
    {
        this.CustomerNames = Customers.ToObservableCollection();
    }

    internal string[] Customers = new string[] {
			"Adams",
			"Crowley",
			"Ellis",
			"Gable",
			"Irvine",
			"Keefe",
			"Mendoza",
			"Owens",
			"Rooney",
			"Waddle",
		};
}
{% endhighlight %}

### Collection of User Defined Types

You can create a `GridPickerColumn` and set its ItemsSource property to a user-typed collection to display a list of user defined items in the picker drop down. Initially the picker column will be displayed with the values from the [GridColumn.MappingName](https://help.syncfusion.com/cr/cref_files/xamarin-iOS/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~MappingName.html) property of the column if the [DisplayMemberPath](https://help.syncfusion.com/cr/cref_files/xamarin-iOS/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridPickerColumn~DisplayMemberPath.html) and [ValueMemberPath](https://help.syncfusion.com/cr/cref_files/xamarin-iOS/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridPickerColumn~ValueMemberPath.html) are not set.

#### DisplayMemberPath
 
 Displays a value by comparing the values of the properties set as `GridColumn.MappingName` and `ValueMemberPath` in their respective underlying collections. If the `ValueMemberPath` property's values contains the `MappingName` property's current value, then its corresponding `DisplayMemberPath` property's value is displayed in the `GridCell`. Else the `GridCell` appears blank. However in the edit mode the values of the `DisplayMemberPath` property are displayed as the picker items.
 
#### ValueMemberPath
 
 Once editing is ended the column having the `MappingName` equal to the `ValueMemberPath` has its data changed to the corresponding `ValueMemberPath` value for the selected `DisplayMemberPath` value in the picker. 

### Customization of picker dropdown values
The following code example shows you how to customize the picker data using `DisplayMemberPath` and `ValueMemberPath`

{% highlight c# %}
sfGrid = new SfDataGrid();
viewModel = new ViewModel();
sfGrid.ItemsSource = viewModel.OrdersInfo;

GridTextColumn orderIDColumn = new GridTextColumn();
orderIDColumn.MappingName = "OrderID";
orderIDColumn.HeaderText = "Order ID";

GridPickerColumn pickerColumn = new GridPickerColumn();
pickerColumn.MappingName = "OrderID";
pickerColumn.HeaderText = "Picker Column";
pickerColumn.DisplayMemberPath = "EmployeeID";
pickerColumn.ValueMemberPath = "OrderID";
pickerColumn.ItemsSource = viewModel.PickerInfo;

sfGrid.Columns.Add(orderIDColumn);
sfGrid.Columns.Add(pickerColumn);

// ViewModel class
public class ViewModel
{
    public class ViewModel :INotifyPropertyChanged
	{
		public ViewModel ()
		{
			SetRowsToGenerate (100);
            this.PickerInfo = OrdersInfo.ToList();
		}

		#region ItemsSource

        private OrderInfoRepository order;

		private ObservableCollection<OrderInfo> ordersInfo;

		public ObservableCollection<OrderInfo> OrdersInfo 
        {
			get { return ordersInfo; }
			set { this.ordersInfo = value; RaisePropertyChanged("OrdersInfo"); }
		}

        public List<OrderInfo> PickerInfo 
        {
			get;
			set;
		}

		#endregion

		#region ItemSource Generator

		public void SetRowsToGenerate (int count)
		{
			order = new OrderInfoRepository ();
			ordersInfo = order.GetOrderDetails (count);
		}

		#endregion

        public ObservableCollection<OrderInfo> GetOrderDetails(int count)
		{
            ObservableCollection<OrderInfo> orderDetails = new ObservableCollection<OrderInfo> ();

			for (int i = 1; i <= count; i++) {

				var order = new OrderInfo () {
					OrderID = i,
                    EmployeeID = i+5,
				};
				orderDetails.Add (order);
			}
			return orderDetails;
		}

        #region INotifyPropertyChanged implementation

        public event PropertyChangedEventHandler PropertyChanged;

        private void RaisePropertyChanged(String name)
        {
            if (PropertyChanged != null)
                this.PropertyChanged(this, new PropertyChangedEventArgs(name));
        }

        #endregion
    }
}
{% endhighlight %}

The following screenshots explains the above code and shows the working of the `PickerColumn` with `ValueMemberPath` and `DisplayMemberPath` properties set.

Here in the above code example underlying collection has 2 properties (OrderID,EmployeeID). We have created a `GridPickerColumn` with MappingName = OrderID, DisplayMemberPath = EmployeeID, ValueMemberPath = OrderID. EmployeeId has the values 6,7,8,9,10.... and OrderID has the values 1,2,3,4,5.... Initially the GridCells of the `PickerColumn` will be displayed with the values 6,7,8,9,10.... in row wise order based on the `DisplayMemberPath`.

![](SfDataGrid_images/PickerColumn_DisplayMemberPath.png)

Upon entering the edit mode at RowColumnIndex(1,1) , the Picker pop up opens and with the picker items as 6,7,8,9,10.... again based on the `DisplayMemberPath`.

![](SfDataGrid_images/PickerColumn_PickerPopUp.png)

When edit mode is exited by selecting a value(9) from the Picker pop up, the `GridCell` at RowColumn index (0,1) displays the corresponding OrderID value for the selected EmployeeID value which is 4. Note that the PickerColumn's `GridCell` data is not changed and only the OrderID columns data is changed to 4. 

![](SfDataGrid_images/PickerColumn_Customization.png)

## GridNumericColumn

The [GridNumericColumn](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridNumericColumn.html) is derived from [GridColumn](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn.html) thereby inheriting all the properties of `GridColumn`. It is used to display numeric data. To create `GridNumericColumn` in SfDataGrid, the property corresponding to the column in the underlying collection must be a numeric type (int, double, float etc). You can enable or disable editing for the particular column by setting the [GridColumn.AllowEditing](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~AllowEditing.html) property to true or false. In the editing mode it displays the [SfNumericTextBox](https://help.syncfusion.com/cr/xamarin-ios/sfnumerictextbox) element. The below code example shows how to create a `GridNumericColumn` in SfDataGrid.

{% highlight c# %}
dataGrid = new SfDataGrid();
            
GridNumericColumn numericColumn = new GridNumericColumn()
{
    MappingName = "ProductNo",
    HeaderText = "Product No",
    NumberDecimalDigits =0
};
dataGrid.Columns.Add(numericColumn);
{% endhighlight %}

### Number Formatting

`GridNumericColumn` allows you to format the numeric data with culture-specific information.

* [NumberDecimalDigits](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridNumericColumn~NumberDecimalDigits.html) - You can change the number of decimal digits to be displayed after the decimal point using `GridNumericColumn.NumberDecimalDigits` property.

* [NumberDecimalSeparator](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridNumericColumn~NumberDecimalSeparator.html) - By default, the dot (.) operator separates the decimal part of numeric value .You can use any operator as decimal separator using `GridNumericColumn.NumberDecimalSeparator` property.

* [NumberGroupSeparator](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridNumericColumn~NumberGroupSeparator.html) - By default, the comma (,) separates group of digits before the decimal point. You can use any operator as group separator using `GridNumericColumn.NumberGroupSeparator` property.

* [NumberGroupSizes](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridNumericColumn~NumberGroupSizes.html) - You can change the number of digits in each group before the decimal point on numeric values using `GridNumericColumn.NumberGroupSizes` property.

* [NumberNegativePattern](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridNumericColumn~NumberNegativePattern.html) - You can format the pattern of negative numeric values using `GridNumericColumn.NumberNegativePattern`.

![](SfDataGrid_images/NumericColumn.jpg)