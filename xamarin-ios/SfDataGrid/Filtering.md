---
layout: post
title: Filtering | SfDataGrid | Xamarin.iOS | Syncfusion
description: How to filter the records in view in a SfDataGrid.
platform: xamarin.ios
control: SfDataGrid
documentation: UG
---

# Filtering

SfDataGrid provides support for view filtering.

## View Filtering

SfDataGrid provides support to filter the records in view by setting `SfDataGrid.View.Filter` property where `Filter` is a `predicate`.

In order to filter the records in SfDataGrid, you have to assign the filtered strings to the `ViewModel.FilterText` property which will be later applied in `Filter predicate` that is assigned to `SfDataGrid.View.Filter` in OnFilterChanged() method.

N> To update the filtering for the newly added row or column, set the `SfDataGrid.View.LiveDataUpdateMode` to `LiveDataUpdateMode.AllowDataShaping`.

The following code example illustrates the delegate, properties, and methods used in the `ViewModel` class in order to perform the filtering operation.

{% highlight c# %}
// ViewModel.cs

#region Filtering

#region Fields

private string filterText = "";
private string selectedColumn = "All Columns";
private string selectedCondition = "Equals";
internal delegate void FilterChanged();
internal FilterChanged filterTextChanged;

#endregion

#region Property

public string FilterText
{
    get { return filterText; }
    set
    {
        filterText = value;
        OnFilterTextChanged();
        RaisePropertyChanged("FilterText");
    }
}

public string SelectedCondition
{
    get { return selectedCondition; }
    set { selectedCondition = value; }
}

public string SelectedColumn
{
    get { return selectedColumn; }
    set { selectedColumn = value; }
}

#endregion

#region Private Methods

private void OnFilterTextChanged()
{
    filterTextChanged();
}

private bool MakeStringFilter(OrderInfo o, string option, string condition)
{
    var value = o.GetType().GetProperty(option);
    var exactValue = value.GetValue(o, null);
    exactValue = exactValue.ToString().ToLower();
    string text = FilterText.ToLower();
    var methods = typeof(string).GetMethods();
    if (methods.Count() != 0)
    {
        if (condition == "Contains")
        {
            var methodInfo = methods.FirstOrDefault(method => method.Name == condition);
            bool result1 = (bool)methodInfo.Invoke(exactValue, new object[] { text });
            return result1;
        }
        else if (exactValue.ToString() == text.ToString())
        {
            bool result1 = String.Equals(exactValue.ToString(), text.ToString());
            if (condition == "Equals")
                return result1;
            else if (condition == "NotEquals")
                return false;
        }
        else if (condition == "NotEquals")
        {
            return true;
        }
        return false;
    }
    else
        return false;
}

private bool MakeNumericFilter(OrderInfo o, string option, string condition)
{
    var value = o.GetType().GetProperty(option);
    var exactValue = value.GetValue(o, null);
    double res;
    bool checkNumeric = double.TryParse(exactValue.ToString(), out res);
    if (checkNumeric)
    {
        switch (condition)
        {
            case "Equals":
                try
                {
                    if (exactValue.ToString() == FilterText)
                    {
                        if (Convert.ToDouble(exactValue) == (Convert.ToDouble(FilterText)))
                            return true;
                    }
                }
                catch (Exception e)
                {
                    Console.WriteLine(e);
                }
                break;
            case "NotEquals":
                try
                {
                    if (Convert.ToDouble(FilterText) != Convert.ToDouble(exactValue))
                        return true;
                }
                catch (Exception e)
                {
                    Console.WriteLine(e);
                        return true;
                }
                break;
        }
    }
    return false;
}

#endregion

#region Public Methods

public bool FilerRecords(object o)
{
    double res;
    bool checkNumeric = double.TryParse(FilterText, out res);
    var item = o as OrderInfo;
    if (item != null && FilterText.Equals(""))
    {
        return true;
    }
    else
    {
        if (item != null)
        {
            if (checkNumeric && !SelectedColumn.Equals("All Columns"))
            {
                bool result = MakeNumericFilter(item, SelectedColumn, SelectedCondition);
                    return result;
            }
            else if (SelectedColumn.Equals("All Columns"))
            {
                if (item.CustomerID.ToLower().Contains(FilterText.ToLower()) ||
                    item.Country.ToLower().Contains(FilterText.ToLower()) || item.Freight.ToString().ToLower().Contains(FilterText.ToLower()) ||                            item.OrderID.ToString().ToLower().Contains(FilterText.ToLower()))
                    return true;
                return false;
            }
            else
            {
                bool result = MakeStringFilter(item, SelectedColumn, SelectedCondition);
                return result;
            }
        }
    }
    return false;
}

#endregion

#endregion
{% endhighlight %}

The following code example illustrates how to create a `UISearchBar` and apply the filtered records to `ViewModel.FilterText` property in `SearchView.QuertTextChange` event.

{% highlight c# %}
// Code-Behind

UISearchBar filterText = new UISearchBar();
filterText.PlaceHolder = "Search in All Columns";
filterText.TextChanged += OnFilterTextChanged;
filterText.CancelButtonClicked += CancelButtonClicked;

private void OnFilterTextChanged(object sender, SearchView.QueryTextChangeEventArgs e)
{
    viewModel.FilterText = e.SearchText;
}

private void CancelButtonClicked(object sender, EventArgs e)
{
    filterText.ResignFirstResponder();
    filterText.SetShowsCancelButton(false, true);
    filterText.ResignFirstResponder();
}
{% endhighlight %}

![](SfDataGrid_images/Filtering_img1.png)

Once you create a `UISearchBar` and a view model, you can perform filtering by setting `SfDataGrid.View.Filter` property. You have to call the `SfDataGrid.View.RefreshFilter()` method after you set the filtered records to the `SfDataGrid.View.Filter` property as like in below code example.

{% highlight c# %}
// Code-Behind

viewModel.filterTextChanged = OnFilterChanged; //where ‘filtertextchanged’ is a delegate declared in ViewModel class.

private void OnFilterChanged()
{
    if (dataGrid.View != null)
    {
        this.dataGrid.View.Filter = viewModel.FilerRecords;
        this.dataGrid.View.RefreshFilter();
    }
}
{% endhighlight %}

### Column based filtering

You can filter the records in all the columns or in particular column using the codes in the below code example. 

For example, you can filter the records in `OrderID` or any other particular column alone.The following code example illustrates how to create an option view to select a column and a condition. Also, it illustrates how the records will be filtered based on the column and the condition selected.

{% highlight c# %}
// OptionView class

public partial class OptionsView : UIView
{
    private FilterViewModel filterModel;
    private UITableView table;
    private UISearchBar bar;
    private UITableView filterConditionTable;
    List<string> items;
    Filtering ParentView;
    public OptionsView ()
    {
        items = new List<string> ()
        table = new UITableView ();
        filterConditionTable = new UITableView ();
        table.SectionIndexTrackingBackgroundColor = UIColor.FromRGB (0, 121, 255);
        filterConditionTable.AllowsSelection = true;
        this.AddSubview (filterConditionTable);
        this.AddSubview (table);
    }
    
    public OptionsView (FilterViewModel model, UISearchBar bar , Filtering parentView) : this ()
    {
        this.ParentView = parentView;
        this.filterModel = model;
        var columnNames = filterModel.BookInfo.GetType ().GetGenericArguments () [0].GetProperties ();
        this.bar = bar;
        
        foreach (var property in columnNames) {
        items.Add (property.Name);
        }
        
        table.Source = new OptionsTableSource (items);
        filterConditiontable.Source = new FilterOptionsTableSource (new List<string> ()          
        {
            "Contains",
            "Equals",
            "Not Equals"
        });
        
        this.AddSubview (filterConditiontable);
        this.AddSubview (table);
    }

    public override void RemoveFromSuperview ()
    {
        base.RemoveFromSuperview ();
        filterModel.SelectedColumn = (table.Source as OptionsTableSource).SelectedItem;
        filterModel.SelectedCondition = (filterConditiontable.Source as FilterOptionsTableSource).SelectedItem;
        
        if (filterModel.SelectedColumn != null && filterModel.SelectedCondition != null)
        {
            this.bar.Placeholder = "Search " + filterModel.SelectedColumn + " with " + filterModel.SelectedCondition;
            if(this.bar.Text != "")
                this.ParentView.OnFilterChanged ();
        }
        else if((filterModel.SelectedColumn != null && filterModel.SelectedCondition == null)||(filtermodel.SelectedColumn == null && filtermodel.SelectedCondition != null))
        {
            var alert = new UIAlertView ("Error", "Should Select Both ColumnName and Condition Type", null, "Cancel", null);
            alert.Frame = new CGRect (50, this.Frame.GetMidX (), 60, this.Frame.GetMidY ());
            alert.Show ();
        }
    }
    
    public override void LayoutSubviews ()
    { 
        table.Frame = (new CGRect (0, 0, this.Frame.Width, (this.Frame.Height / 2)+13));
        filterConditiontable.Frame=(new CGRect (0, table.Bounds.Bottom + 2, this.Frame.Width, this.Frame.Height));
        base.LayoutSubviews ();
    }
}

public class OptionsTableSource : UITableViewSource
{
    public List<string> tableItems;
    string cellIdentifier = "TableCell";
    string[] keys = new string[] { };
    public string SelectedItem = null;
    
    public OptionsTableSource(List<string> items)
    {
        tableItems = items;
        keys = new string[] { "ColumnName" };
    }
    
    public override nint RowsInSection(UITableView tableView, nint section)
    {
        return tableItems.Count;
    }
    
    public override UITableViewCell GetCell(UITableView tableView, Foundation.NSIndexPath indexPath)
    {
        UITableViewCell cell = tableView.DequeueReusableCell(cellIdentifier);
        // if there are no cells to reuse, create a new one
        if (cell == null)
            cell = new UITableViewCell(UITableViewCellStyle.Default, cellIdentifier);
        cell.TextLabel.Text = tableItems[indexPath.Row];
        cell.SelectionStyle = UITableViewCellSelectionStyle.Blue;
        return cell;
    }
    
    public override nint NumberOfSections(UITableView tableView)
    {
        return keys.Length;
    }
    
    public override void RowSelected(UITableView tableView, Foundation.NSIndexPath indexPath)
    {
        SelectedItem = tableItems[indexPath.Row];
    }
    public override string TitleForHeader(UITableView tableView, nint section)
    {
        return keys[section];
    }
}

public class FilterOptionsTableSource : UITableViewSource
{
    public List<string>; tableItems;
    string cellIdentifier = "TableCell";
    string[] keys = new string[] { };
    public string SelectedItem = null;
    
    public FilterOptionsTableSource(List<string> items)
    {
        tableItems = items;
        keys = new string[] { "Filter Condition Type" };
    }
    
    public override nint RowsInSection(UITableView tableView, nint section)
    {
        return tableItems.Count;
    }
    
    public override UITableViewCell GetCell(UITableView tableView, Foundation.NSIndexPath indexPath)
    {
        UITableViewCell cell = tableView.DequeueReusableCell(cellIdentifier);
        // if there are no cells to reuse, create a new one
        if (cell == null)
           cell = new UITableViewCell(UITableViewCellStyle.Subtitle, cellIdentifier);
        cell.TextLabel.Text = tableItems[indexPath.Row];
        cell.SelectionStyle = UITableViewCellSelectionStyle.Blue;
        return cell;
    }
    
    public override void WillDisplay(UITableView tableView, UITableViewCell cell, Foundation.NSIndexPath indexPath)
    {
        if (cell.Selected)
        {
            cell.BackgroundColor = UIColor.Red;
        }
    }
    
    public override nint NumberOfSections(UITableView tableView)
    {
        return keys.Length;
    }
    
    public override void RowSelected(UITableView tableView, Foundation.NSIndexPath indexPath)
    {
        SelectedItem = tableItems[indexPath.Row];
    }
    
    public override string TitleForHeader(UITableView tableView, nint section)
    {
        return keys[section];
    }
}
{% endhighlight %}

![](SfDataGrid_images/Filtering_img2.png)

### Condition based filtering

In addition to the column based filtering, you can filter the records based on some conditions. For example, you can filter the records based on the input you given or you can filter the records contrast to your input. You can achieve the condition based filtering for all the columns or any particular column.

You can filter the records in the view based on any of the below conditions,

* Equals
* NotEquals
* Contains

The above conditions are the mostly used conditions. However, you can add any other conditions based on your requirement and alter the below code example based on your condition.

{% highlight c# %}
// ViewModel.cs

public bool FilerRecords(object o)
{
    double res;
    bool checkNumeric = double.TryParse(FilterText, out res);
    var item = o as OrderInfo;
    
    if (item != null && FilterText.Equals(""))
    {
        return true;
    }
    else
    {
        if (item != null)
        {
            if (checkNumeric && !SelectedColumn.Equals("All Columns"))
            {
                bool result = MakeNumericFilter(item, SelectedColumn, SelectedCondition);
                    return result;
            }
            else if (SelectedColumn.Equals("All Columns"))
            {
                if (item.CustomerID.ToLower().Contains(FilterText.ToLower()) ||
                    item.Country.ToLower().Contains(FilterText.ToLower()) || item.Freight.ToString().ToLower().Contains(FilterText.ToLower()) ||                            item.OrderID.ToString().ToLower().Contains(FilterText.ToLower()))
                    return true;
                return false;
            }
            else
            {
                bool result = MakeStringFilter(item, SelectedColumn, SelectedCondition);
                return result;
            }
        }
    }
    return false;
}

private bool MakeStringFilter(OrderInfo o, string option, string condition)
{
    var value = o.GetType().GetProperty(option);
    var exactValue = value.GetValue(o, null);
    exactValue = exactValue.ToString().ToLower();
    string text = FilterText.ToLower();
    var methods = typeof(string).GetMethods();
    if (methods.Count() != 0)
    {
        if (condition == "Contains")
        {
            var methodInfo = methods.FirstOrDefault(method => method.Name == condition);
            bool result1 = (bool)methodInfo.Invoke(exactValue, new object[] { text });
            return result1;
        }
        else if (exactValue.ToString() == text.ToString())
        {
            bool result1 = String.Equals(exactValue.ToString(), text.ToString());
            if (condition == "Equals")
                return result1;
            else if (condition == "NotEquals")
                return false;
        }
        else if (condition == "NotEquals")
        {
            return true;
        }
        return false;
    }
    else
        return false;
}

private bool MakeNumericFilter(OrderInfo o, string option, string condition)
{
    var value = o.GetType().GetProperty(option);
    var exactValue = value.GetValue(o, null);
    double res;
    bool checkNumeric = double.TryParse(exactValue.ToString(), out res);
    if (checkNumeric)
    {
        switch (condition)
        {
            case "Equals":
                try
                {
                    if (exactValue.ToString() == FilterText)
                    {
                        if (Convert.ToDouble(exactValue) == (Convert.ToDouble(FilterText)))
                            return true;
                    }
                }
                catch (Exception e)
                {
                    Console.WriteLine(e);
                }
                break;
            case "NotEquals":
                try
                {
                    if (Convert.ToDouble(FilterText) != Convert.ToDouble(exactValue))
                        return true;
                }
                catch (Exception e)
                {
                    Console.WriteLine(e);
                        return true;
                }
                break;
        }
    }
    return false;
}
{% endhighlight %}

![](SfDataGrid_images/Filtering_img3.png)

## Clear filtering

SfDataGrid allows you to clear the applied filtering by setting the `SfDataGrid.View.Filter` property to `null`.

The below code example illustrates how to clear the applied filtering in SfDataGrid.

{% highlight c# %}
// Code-Behind

private void OnFilterChanged()
{
    if (dataGrid.View != null)
    {
        this.dataGrid.View.Filter = null;
        this.dataGrid.View.RefreshFilter();
    }
}
{% endhighlight %}
