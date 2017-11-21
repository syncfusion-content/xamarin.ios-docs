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

SfDataGrid allows to fill the remaining width for any column by using [GridColumn.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~ColumnSizer.html) property.
The `GridColumn.ColumnSizer` property is also type of [ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.ColumnSizer.html) and If we want to fill any columns accordingly in the view, then follow the below code example to acheive it.

The following example shows how to fill the remaining width for any column in `SfDataGrid`

{% highlight c# %} 
GridTextColumn orderIDColumn = new GridTextColumn();
orderIDColumn.MappingName = "OrderID";
orderIDColumn.HeaderText = "OrderID";

GridTextColumn customerIDColumn = new GridTextColumn();
customerIDColumn.MappingName = "CustomerID";
customerIDColumn.HeaderText = "CustomerID";
customerIDColumn.ColumnSizer = ColumnSizer.LastColumnFill;

GridTextColumn freightColumn = new GridTextColumn();
freightColumn.MappingName = "Freight";
freightColumn.HeaderText = "Freight";

GridTextColumn countryColumn = new GridTextColumn();
countryColumn.MappingName = "Country";
countryColumn.HeaderText = "Country";

dataGrid.Columns.Add(orderIDColumn);
dataGrid.Columns.Add(customerIDColumn);
dataGrid.Columns.Add(freightColumn);
dataGrid.Columns.Add(countryColumn);

View.AddSubviews(dataGrid);
{% endhighlight %}

### Refreshing ColumnSizer for SfDataGrid at runtime

You can refresh the column sizing for SfDataGrid columns by using [GridColumn.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~ColumnSizer.html) property.

The following code example guides how to refresh `ColumnSizer` at runtime in SfDataGrid.

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
    dataGrid.ColumnSizer = ColumnSizer.LastColumnFill;

    View.AddSubviews(dataGrid);
}

private void ColumnSizerChanged(object sender, EventArgs e)
{
    dataGrid.GridColumnSizer.Refresh(true);
}
{% endhighlight %}

### Resetting column width to apply ColumnSizer   

You can reset and apply the `ColumnSizer` for any column by using the below way.

{% highlight c# %}
GridTextColumn orderIDColumn = new GridTextColumn();
orderIDColumn.MappingName = "OrderID";
orderIDColumn.HeaderText = "OrderID";
orderIDColumn.Width = 20;

GridTextColumn customerIDColumn = new GridTextColumn();
customerIDColumn.MappingName = "CustomerID";
customerIDColumn.HeaderText = "CustomerID";

GridTextColumn freightColumn = new GridTextColumn();
freightColumn.MappingName = "Freight";
freightColumn.HeaderText = "Freight";

GridTextColumn countryColumn = new GridTextColumn();
countryColumn.MappingName = "Country";
countryColumn.HeaderText = "Country";

dataGrid.Columns.Add(orderIDColumn);
dataGrid.Columns.Add(customerIDColumn);
dataGrid.Columns.Add(freightColumn);
dataGrid.Columns.Add(countryColumn);

View.AddSubviews(dataGrid);
RetsetColumns(dataGrid.Columns);
{% endhighlight %}

{% highlight c# %}
private void RetsetColumns(IEnumerable<GridColumn>columns)
{
    foreach(var column in columns)
    {
        if(column.MappingName =="OrderID")
        {
            dataGrid.Columns[0].Width = dataGrid.Columns[1].Width;
            dataGrid.Columns[0].ColumnSizer = ColumnSizer.LastColumnFill;
        }
    }
}
{% endhighlight %}

## Star column sizer ratio support

You can customize the ColumnSizer.Star width calculation by setting the [SfDataGrid.ColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~ColumnSizer.html) property which is processed in [GridColumnSizer](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumnSizer.html) class. If you want to divide the columns width in different ratio,you need to override the [SetStarWidthForColumns](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumnSizer~SetStarWidthForColumns.html) method in `GridColumnSizer` class.  

The following code example shows how to add column sizer ratio for columns.

{% highlight c# %}
GridTextColumn orderIDColumn = new GridTextColumn();
orderIDColumn.MappingName = "OrderID";
orderIDColumn.HeaderText = "OrderID";
viewModel.Columns.Add(orderIDColumn,3);

GridTextColumn customerIDColumn = new GridTextColumn();
customerIDColumn.MappingName = "CustomerID";
customerIDColumn.HeaderText = "CustomerID";
viewModel.Columns.Add(customerIDColumn, 2);

GridTextColumn freightColumn = new GridTextColumn();
freightColumn.MappingName = "Freight";
freightColumn.HeaderText = "Freight";

GridTextColumn countryColumn = new GridTextColumn();
countryColumn.MappingName = "Country";
countryColumn.HeaderText = "Country";

dataGrid.Columns.Add(orderIDColumn);
dataGrid.Columns.Add(customerIDColumn);
dataGrid.Columns.Add(freightColumn);
dataGrid.Columns.Add(countryColumn);

SetContentView(dataGrid);
{% endhighlight %}

The following code example illustrates how the width is calculated for `SfDataGrid` columns.

{% highlight c# %} 
public class ColumnSizerExt : GridColumnSizer
{
    SfDataGrid dataGrid;
    ViewModel viewModel;
    public ColumnSizerExt(SfDataGrid grid, ViewModel view) : base(grid)
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
                columnsCount += viewModel.GetColumnSizer(data);
            }
            double starWidth = Math.Floor((totalRemainingStarValue / columnsCount));
            var getColumn = column.First();

            starWidth *= viewModel.GetColumnSizer(getColumn);
            var columnSizer = DataGrid.GridColumnSizer;
            var method = columnSizer.GetType().GetRuntimeMethods().FirstOrDefault(x => x.Name == "SetColumnWidth");
            var width = method.Invoke(columnSizer, new object[] { getColumn, starWidth });
            double computeWidth = (double)width;

            if (starWidth != computeWidth && starWidth > 0)
            {
                isremoved = true;
                column.Remove(getColumn);
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
                column.Remove(getColumn);
                if (!removedColumn.Contains(getColumn))
                    removedColumn.Add(getColumn);
            }
        }
    }
}
{% endhighlight %} 

{% highlight c# %} 
public class ViewModel : INotifyPropertyChanged
{
    public Dictionary<GridColumn, Int16> Columns;
    public ViewModel()
    {
        SetRowstoGenerate(50);
        Columns = new Dictionary<GridColumn, Int16>();
    }

    #region ItemsSource

    private ObservableCollection<OrderInfo> ordersInfo;

    public ObservableCollection<OrderInfo> OrdersInfo
    {
        get { return ordersInfo; }
        set { this.ordersInfo = value; }
    }

    public int GetColumnSizer(GridColumn column)
    {
        if (Columns.ContainsKey(column))
            return Columns[column];
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
