---
layout: post
title: Filtering | SfDataGrid | Xamarin | Syncfusion
description: How to filter the records in view in a SfDataGrid.
platform: xamarin.iOS
control: SfDataGrid
documentation: UG
---

# Filtering 

SfDataGrid provides support to filter the records in view by setting the **SfDataGrid.View.Filter** property. You have to call the **SfDataGrid.View.RefreshFilter()** method after assigning the Filter property for the records to get filtered in view.
 
The following code example illustrates how to apply filtering in SfDataGrid. FilterRecords method filters the data that contains the filterText value. Assign FilterRecords method to **SfDataGrid.View.Filter** predicate to filter the CustomerID column.
 
{% highlight c# %}
//For Filtering:
 
UISearchBar filterText = new UISearchBar ();
filterText.TextChanged += OnFilterTextChanged;
filterText.Placeholder = "Search CustomerID"; 
viewModel.FilterTextChanged = OnFilterChanged;

void OnFilterTextChanged(object sender, UISearchBarTextChangedEventArgs e)
{
    viewModel.FilterText = e.SearchText;
} 

private void OnFilterChanged()
{
    if (dataGrid.View != null) {
        this.dataGrid.View.Filter = viewModel.FilerRecords;
        this.dataGrid.View.RefreshFilter ();
    }
}
{% endhighlight %}

The following code example illustrates the code for filtering the data using FilterRecords method in the ViewModel.

{% highlight c# %}
//ViewModel.cs: 

internal delegate void FilterChanged();

internal FilterChanged FilterTextChanged;

private string filterText = "";

public string FilterText {
    get { return filterText; }
    set {
        filterText = value;
        OnFilterTextChanged ();
        RaisePropertyChanged ("FilterText");
    }
}

private void OnFilterTextChanged()
{
    if (FilterTextChanged != null)
        FilterTextChanged ();
}

public bool FilerRecords(object order)
{
    var item = order as OrderInfo;
    if (item != null && FilterText.Equals ("") && !string.IsNullOrEmpty (FilterText))
        return true;
    else if (item != null) {
        var exactValue = item.CustomerID.ToLower ();
        string text = FilterText.ToLower ();
        return exactValue.Contains (text);
    }
    return false;
} 
{% endhighlight %}
