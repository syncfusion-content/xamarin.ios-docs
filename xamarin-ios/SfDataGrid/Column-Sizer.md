---
layout: post
title: Column Sizer | SfDataGrid | Xamarin.iOS | Syncfusion
description: What are all the different ColumnSizer and how it works in a SfDataGrid.
platform: xamarin.ios
control: SfDataGrid
documentation: ug
---

# Column Sizer

SfDataGrid allows you to apply ColumnSizer for the GridColumns by setting the [SfDataGrid.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~ColumnSizer.html) property. 

The following code example illustrates how to apply `ColumnSizer` in SfDataGrid.

{% highlight c# %}
dataGrid.ColumnSizer = ColumnSizer.None;  
{% endhighlight %}

SfDataGrid applies width for all the GridColumns in the [SfDataGrid.Columns](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~Columns.html) collection based on the `SfDataGrid.ColumnSizer` property. Following are the lists of options available to set width of the Columns.

* None
* LastColumnFill
* Star
* Auto


## ColumnSizer.None

No Column sizing is applied when the [SfDataGrid.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~ColumnSizer.html) is set to [None](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.ColumnSizer.html). Columns are arranged in view based on the [SfDataGrid.DefaultColumnWidth](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~DefaultColumnWidth.html) property. This is the default value of the `SfDataGrid.ColumnSizer` property.

{% highlight c# %}
dataGrid.ColumnSizer = ColumnSizer.None;  
{% endhighlight %}

![](SfDataGrid_images/CoumnSizer_img1.png)

## ColumnSizer.LastColumnFill

When the [SfDataGrid.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~ColumnSizer.html) is [LastColumnFill](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.ColumnSizer.html), the column width of the GridColumns are adjusted with respect to [SfDataGrid.DefaultColumnWidth](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~DefaultColumnWidth.html) property. In case if the columns does not fill the entire view space, then the last column’s width fills the unoccupied space in the view.

{% highlight c# %}
dataGrid.ColumnSizer = ColumnSizer.LastColumnFill;  
{% endhighlight %}

![](SfDataGrid_images/CoumnSizer_img2.png)

## ColumnSizer.Star

When the [SfDataGrid.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~ColumnSizer.html) is [Star](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.ColumnSizer.html), all the GridColumns are adjusted an equal column width to fit within the view. Setting ColumnSizer to `Star` will disable the horizontal scrolling in SfDataGrid.

{% highlight c# %}
dataGrid.ColumnSizer = ColumnSizer.Star;  
{% endhighlight %}

![](SfDataGrid_images/CoumnSizer_img3.png)

## ColumnSizer.Auto

When the [SfDataGrid.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~ColumnSizer.html) is [Auto](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.ColumnSizer.html), the width of the `GridColumns` are adjusted based on the header text or cell contents.

{% highlight c# %}
dataGrid.ColumnSizer = ColumnSizer.Auto;  
{% endhighlight %}

![](SfDataGrid_images/CoumnSizer_Img4.png)

N> If any column is specified a width explicitly using the [GridColumn.Width](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~DefaultColumnWidth.html) property then that column is not considered for Column sizing the width and skipped while applying the ColumnSizer for grid columns.

## How to 

### Apply ColumnSizer for a particular column

You can apply column sizing to individual columns by using the [GridColumn.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~ColumnSizer.html) property. The `GridColumn.ColumnSizer` property is also type of [ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.ColumnSizer.html) . If the `GridColumn.ColumnSizer` is not explicitly set to a value, then it takes the value of the [SfDataGrid.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~ColumnSizer.html) and applies the width to the columns accordingly.

The following code example illustrates how to apply `ColumnSizer` for a particular column.

{% highlight c# %}
GridTextColumn textColumn = new GridTextColumn();
textColumn.MappingName = "CustomerID";
textColumn.HeaderText = "Full Name";
textColumn.ColumnSizer = ColumnSizer.Auto;  
{% endhighlight %}

### Apply ColumnSizer based on device orientation

You can apply different ColumnSizer based on orientation of the device and the SfDataGrid will rearrange the view accordingly.

Refer the below code example in which the `SfDataGrid.ColumnSizer` is customized based on orientation by checking the orientation of the device in the `ViewLayoutSubViews` override method of the `ViewController` which will be fired when the view changes.

{% highlight c# %}
public override void ViewDidLayoutSubviews()
{
    base.ViewDidLayoutSubviews();
    if (UIDevice.CurrentDevice.Orientation == UIDeviceOrientation.LandscapeLeft || UIDevice.CurrentDevice.Orientation == UIDeviceOrientation.LandscapeRight)
        this.datagrid.ColumnSizer = ColumnSizer.Star;
    else
        this.datagrid.ColumnSizer = ColumnSizer.Auto;
    datagrid.Frame = new CoreGraphics.CGRect(0, 0, View.Frame.Width, View.Frame.Height );           
}  
{% endhighlight %}

![](SfDataGrid_images/ColumnSizer_Orientation.png)

![](SfDataGrid_images/ColumnSizer_Orientation1.png)

### Fill Remaining width for any column

SfDataGrid allows to fill the remaining width in view for any column by using [GridColumn.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~ColumnSizer.html) property.
The `GridColumn.ColumnSizer` has higher priority than the [SfDataGrid.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~ColumnSizer.html) property. Hence the individual columns having the `GridColumn.ColumnSizer` property set will not be included in the column sizer calculations of the `SfDataGrid`. Set the `GridColumn.ColumnSizer` property as [ColumnSizer.LastColumnFill](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.ColumnSizer.html) for the column you want to fill with the remaining width in the view. Please refer the below code example to acheive the same.

In the below code snippet, the SfDataGrid is applied `ColumnSizer.Star` and the second column is applied ColumnSizer.LastColumnFill.
Hence the second column will take up the remaining space, after the other columns are rendered with star sizer.

{% highlight c# %} 
GridTextColumn orderIDColumn = new GridTextColumn();
orderIDColumn.MappingName = "OrderID";

GridTextColumn customerIDColumn = new GridTextColumn();
customerIDColumn.MappingName = "CustomerID";
customerIDColumn.ColumnSizer = ColumnSizer.LastColumnFill;

GridTextColumn freightColumn = new GridTextColumn();
freightColumn.MappingName = "Freight";

GridTextColumn countryColumn = new GridTextColumn();
countryColumn.MappingName = "Country";

dataGrid.Columns.Add(orderIDColumn);
dataGrid.Columns.Add(customerIDColumn);
dataGrid.Columns.Add(freightColumn);
dataGrid.Columns.Add(countryColumn);

View.AddSubviews(dataGrid);
{% endhighlight %}

### Refreshing ColumnSizer for SfDataGrid at runtime

You can refresh the column sizing for `SfDataGrid.Columns` by using [GridColumn.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~ColumnSizer.html) property.
Consider that `ColumnSizer.Auto` is applied to the SfDataGrid. If in case the underlying values are changed in run time, you can refresh the ColumnSizer as shown below.

{% highlight c# %} 
SfDataGrid dataGrid;
ViewModel viewModel;
UIButton button;
public MyViewController()
{
    dataGrid = new SfDataGrid();
    viewModel = new ViewModel();
    button = new UIButton();
    button.SetTitle("ColumnSizer",UIControlState.Normal);
    button.TouchDown += ColumnSizerChanged;
    dataGrid.AutoGenerateColumns = true;
    dataGrid.ItemsSource = viewModel.OrdersInfo;
    dataGrid.AllowEditing = true;
    dataGrid.ColumnSizer = ColumnSizer.Auto;

    View.AddSubviews(button);
    View.AddSubviews(dataGrid);
}
private void ColumnSizerChanged(object sender, EventArgs e)
{
    //Refreshes the column sizer of the SfDataGrid
    dataGrid.GridColumnSizer.Refresh(true);
}
{% endhighlight %}

### Resetting column width to apply ColumnSizer   

By default, the columns having the [GridColumn.Width](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~Width.html) property set, will not be included for the SfDataGrid's column sizer calculations. If in case you want to include the width columns and refresh the column sizer in runtime, please set the `GridColumn.Width` property to double.NaN before calling the [GridColumnSizer.Refresh()](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumnSizer~Refresh(Boolean).html) method. Please refer the below code example to achieve the same.

{% highlight c# %}
SfDataGrid dataGrid;
ViewModel viewModel;
UIButton button;
protected override void OnCreate(Bundle savedInstanceState)
{
    base.OnCreate(savedInstanceState);
    layout = new LinearLayout(this.BaseContext);
    layout.Orientation = Orientation.Vertical;
    button = new Button(this.BaseContext);
    button.Text = "ColumnSizer";
    button.Click += ColumnSizerChanged;
    dataGrid = new SfDataGrid(this.BaseContext);
    viewModel = new ViewModel();
    dataGrid.AutoGenerateColumns = false;
    dataGrid.ItemsSource = viewModel.OrdersInfo;

    GridTextColumn orderIDColumn = new GridTextColumn();
    orderIDColumn.MappingName = "OrderID";
    orderIDColumn.Width = 20;

    GridTextColumn customerIDColumn = new GridTextColumn();
    customerIDColumn.MappingName = "CustomerID";

    GridTextColumn freightColumn = new GridTextColumn();
    freightColumn.MappingName = "Freight";

    GridTextColumn countryColumn = new GridTextColumn();
    countryColumn.MappingName = "Country";

    dataGrid.Columns.Add(orderIDColumn);
    dataGrid.Columns.Add(customerIDColumn);
    dataGrid.Columns.Add(freightColumn);
    dataGrid.Columns.Add(countryColumn);

    View.AddSubviews(button);
    View.AddSubviews(dataGrid);
}
{% endhighlight %}
{% highlight c# %}
private void ColumnSizerChanged(object sender, EventArgs e)
{
    //Refreshes the column sizer calculation of the SfDataGrid
    ResetColumns();
    dataGrid.GridColumnSizer.Refresh(true);
}
private void ResetColumns()
{
    foreach (var column in dataGrid.Columns)
    {
        // Setting NaN values to columns for which width is applied
        if (!double.IsNaN(column.Width))
        {
            column.Width = double.NaN;
        }
    }
}
{% endhighlight %}

## Star column sizer ratio support

You can customize the `ColumnSizer.Star` width calculation by writing a custom GridColumnSizer class derived from [GridColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumnSizer.html) and assign it to the `SfDataGrid.ColumnSizer` property. You can implement your own logic to divide the column widths in different ratios,by overriding the [SetStarWidthForColumns](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumnSizer~SetStarWidthForColumns.html) method in your custom GridColumnSizer class.

The following code example shows how to set star sizer ratio for individual columns.

{% highlight c# %}
SfDataGrid dataGrid;
ViewModel viewModel;
protected override void OnCreate(Bundle savedInstanceState)
{
    base.OnCreate(savedInstanceState);
    dataGrid = new SfDataGrid(this.BaseContext);
    viewModel = new ViewModel();
    dataGrid.AutoGenerateColumns = false;
    dataGrid.ItemsSource = viewModel.OrdersInfo;
    dataGrid.ColumnSizer = ColumnSizer.Star;
    dataGrid.GridColumnSizer = new CustomColumnSizer(this.dataGrid, viewModel);

    GridTextColumn orderIDColumn = new GridTextColumn();
    orderIDColumn.MappingName = "OrderID";
    //Assigns the ratio for OrderID column
    viewModel.ColumnRatio.Add(orderIDColumn.MappingName, 3);

    GridTextColumn customerIDColumn = new GridTextColumn();
    customerIDColumn.MappingName = "CustomerID";
    //Assigns the ratio for CustomerID column
    viewModel.ColumnRatio.Add(customerIDColumn.MappingName, 2);

    GridTextColumn freightColumn = new GridTextColumn();
    freightColumn.MappingName = "Freight";

    GridTextColumn countryColumn = new GridTextColumn();
    countryColumn.MappingName = "Country";

    dataGrid.Columns.Add(orderIDColumn);
    dataGrid.Columns.Add(customerIDColumn);
    dataGrid.Columns.Add(freightColumn);
    dataGrid.Columns.Add(countryColumn);

    View.AddSubviews(dataGrid);
}
{% endhighlight %}

The following code example demonstrates how the width is calculated for column, based on the `GetRatio` property in `SetStarWidthForColumns` method.

{% highlight c# %} 
public class CustomColumnSizer : GridColumnSizer
{
    SfDataGrid dataGrid;
    ViewModel viewModel;
    public CustomColumnSizer(SfDataGrid grid, ViewModel view) : base(grid)
    {
        dataGrid = grid;
        viewModel = view;
    }
    protected override void SetStarWidthForColumns(double columnsWidth, IEnumerable<GridColumn> columns)
    {
        var removedColumn = new List<GridColumn>();
        var column = columns.ToList();
        var totalRemainingStarValue = columnsWidth;
        double removedWidth = 0;
        bool isremoved;
        while (column.Count > 0)
        {
            isremoved = false;
            removedWidth = 0;
            var columnsCount = 0;
            foreach (var data in column)
            {
                columnsCount += viewModel.GetRatio(data.MappingName);
            }
            double starWidth = Math.Floor((totalRemainingStarValue / columnsCount));
            var col = column.First();

            //Calculate the ColumnSizer ratio for every column  
            starWidth *= viewModel.GetRatio(col.MappingName);
            var columnSizer = DataGrid.GridColumnSizer;
            var method = columnSizer.GetType().GetRuntimeMethods().FirstOrDefault(x => x.Name == "SetColumnWidth");
            var width = method.Invoke(columnSizer, new object[] { col, starWidth });
            double computeWidth = (double)width;

            if (starWidth != computeWidth && starWidth > 0)
            {
                isremoved = true;
                column.Remove(col);
                foreach (var remColumn in removedColumn)
                {
                    if (!column.Contains(remColumn))
                    {
                        removedWidth += remColumn.ActualWidth;
                        column.Add(remColumn);
                    }
                }
                removedColumn.Clear();
                totalRemainingStarValue += removedWidth;
            }
            totalRemainingStarValue = totalRemainingStarValue - computeWidth;
            if (!isremoved)
            {
                column.Remove(col);
                if (!removedColumn.Contains(col))
                    removedColumn.Add(col);
            }
        }
    }
}
{% endhighlight %} 

The following code example explains the `GetRatio` property. 

{% highlight c# %} 
public class ViewModel : INotifyPropertyChanged
{
    public Dictionary<string, int> ColumnRatio;
    public ViewModel()
    {
        SetRowstoGenerate(50);
        ColumnRatio = new Dictionary<string, int>();
    }

    #region ItemsSource

    private ObservableCollection<OrderInfo> ordersInfo;

    public ObservableCollection<OrderInfo> OrdersInfo
    {
        get { return ordersInfo; }
        set { this.ordersInfo = value; }
    }

    internal int GetRatio(string mappingName)
    {
        if (ColumnRatio.ContainsKey(mappingName))
            return ColumnRatio.GetValueOrDefault(mappingName);
        else
            return 1;
    }

    #endregion

    #region ItemSource Generator

    public void SetRowstoGenerate(int count)
    {
        OrderInfoRepository order = new OrderInfoRepository();
        ordersInfo = order.GetOrderDetails(count);
    }

    #endregion

    #region INotifyPropertyChanged implementation

    public event PropertyChangedEventHandler PropertyChanged;

    public void RaisePropertyChanged(string propertyName)
    {
        if (PropertyChanged != null)
            this.PropertyChanged(this, new PropertyChangedEventArgs(propertyName));
    }

    #endregion
}
{% endhighlight %} 