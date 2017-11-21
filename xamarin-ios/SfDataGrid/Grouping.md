---
layout: post
title: Grouping | SfDataGrid | Xamarin.iOS | Syncfusion
description: How to group a column in a SfDataGrid and about the properites and customizations in grouping.
platform: xamarin.ios
control: SfDataGrid
documentation: UG
---

# Grouping 

A group represents a collection of records that belong to a particular category. When grouping is applied, the data is organized into a hierarchical structure based on matching field values. The records having identical values in the grouped column are combined to form a group. Each group is identified by its [CaptionSummaryRow](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~CaptionSummaryRow.html) to get the underlying records in view.

N> To update grouping for the newly added row or column, set the `SfDataGrid.View.LiveDataUpdateMode` to `LiveDataUpdateMode.AllowDataShaping`.

## Programmatic Grouping

SfDataGrid also allows to perform grouping from the code by defining the [GroupColumnDescription](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GroupColumnDescription.html) object and adding it in the [SfDataGrid.GroupColumnDescriptions](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GroupColumnDescriptions.html) collection. SfDataGrid groups the data based on the `GroupColumnDescription` object that is added to this collection.

`GroupColumnDescription` object holds following two properties:

* [ColumnName](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GroupColumnDescription~ColumnName.html): Name of the grouped column.
* [Converter](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GroupColumnDescription~Converter.html): Get the `IValueConverter` as input that helps to apply the custom grouping.

The following code example illustrates how to apply grouping by a column in SfDataGrid.

{% highlight c# %}
    dataGrid.GroupColumnDescriptions.Add (new GroupColumnDescription () {
    ColumnName = "CustomerID",
}); 
{% endhighlight %}

The following screenshot shows the output rendered when grouping is applied.
![](SfDataGrid_images/Grouping.png)

## Expand groups while grouping
 
You can expand all the groups while grouping by setting [SfDataGrid.AutoExpandGroups](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~AutoExpandGroups.html) to `true`. So, when user group any column, then all groups will be in expanded state. 

{% highlight c# %}
this.dataGrid.AutoExpandGroups = true;
this.dataGrid.AllowGroupExpandCollapse = true;
{% endhighlight %}

## Expand or collapse the groups

By default, the groups will be in expanded state in a SfDataGrid. However, you can expand or collapse a group in runtime by setting the [SfDataGrid.AllowGroupExpandCollapse](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~AllowGroupExpandCollapse.html) as `true`.

{% highlight c# %}
this.dataGrid.AllowGroupExpandCollapse = true;
{% endhighlight %}

### Expand or collapse all the Groups

You can expand or collapse all the groups at programmatically at runtime by using [SfDataGrid.ExpandAllGroup](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~ExpandAllGroup.html) and [SfDataGrid.CollapseAllGroup](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~CollapseAllGroup.html) methods.

{% tabs %}
{% highlight c# %}
this.dataGrid.ExpandAllGroup();
this.dataGrid.CollapseAllGroup();
{% endhighlight %}
{% endtabs %}

### Expand or Collapse the specific Group

You can expand or collapse specific group by using [SfDataGrid.ExpandGroup](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~ExpandGroup.html) and [SfDataGrid.CollapseGroup](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~CollapseGroup.html) methods.

{% highlight c# %}
var group = (dataGrid.View.Groups[0] as Group);
this.dataGrid.ExpandGroup(group);
this.dataGrid.CollapseGroup(group);
{% endhighlight %}

![](SfDataGrid_images/GroupExpandCollapse.png)

## Custom Grouping

SfDataGrid allows you to group a column based on custom logic when the standard grouping techniques do not meet the requirements. To achieve the custom grouping, you need to write a converter that implements `IValueConverter` with your custom grouping logic and assign that converter to the [GroupColumnDescription.Converter](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GroupColumnDescription~Converter.html) property.

The following code example illustrates how to set the custom grouping converter for the group description that is added to group the Freight column.

{% highlight c# %}
dataGrid.GroupColumnDescriptions.Add (new GroupColumnDescription () {
    ColumnName = "Freight",
    Converter = new GroupConverter()
}); 
{% endhighlight %}

The following code example illustrates the converter used for applying custom grouping logic.

{% highlight c# %}
public class GroupConverter : IValueConverter
{
    public GroupConverter()
    {
        
    }

    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        var orderInfo = value as OrderInfo;
        if (orderInfo.Freight > 0 && orderInfo.Freight <= 250)
            return "<=250";
        else if (orderInfo.Freight > 250 && orderInfo.Freight <= 500)
            return ">250 & <=500";
        else if (orderInfo.Freight > 500 && orderInfo.Freight <= 750)
            return ">500 & <=750";
        else
            return ">1000";
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        return null;
    }
}
{% endhighlight %}

## Display based grouping using GroupMode property

By default column grouping occurs based on the value in the underlying collection thereby creating a new group for each new value of that column. However you can also group a column based on the Display value by setting the [GridColumn.GroupMode](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~GroupMode.html) property as `Display`. In the below code example we have set [GridColumn.Format](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridColumn~Format.html) property as "#" which displays only the rounded off value in the `GridCell`.  

{% highlight c# %}
GridNumericColumn cargoWeight = new GridTextColumn();
cargoWeight.MappingName = "ShipmentWeight";
cargoWeight.GroupMode = Syncfusion.Data.DataReflectionMode.Display;
cargoWeight.Format = "#";
{% endhighlight%} 

The below screenshot shows the comparison between the two Group modes. GroupMode.Value on the left and GroupMode.Display on the right.
![](SfDataGrid_images/GroupMode.png)

## Clearing or Removing Group

### Clearing the Group

 You can clear the grouping applied to the SfDataGrid by removing the items from the `SfDataGrid.GroupColumnDescriptions` collection or clearing the collection. Please refer the below code snippets to remove the grouping applied to the SfDataGrid.

{% highlight c# %}
public class MyViewController:UIViewController
{
    SfDataGrid dataGrid;
    ViewModel viewModel;
    UIButton clearGroupingButton;
    UIStackView stackView;
    public MyViewController()
    {
        dataGrid = new SfDataGrid();
        viewModel = new ViewModel();
        clearGroupingButton = new UIButton();
        stackView = new UIStackView();
    }

    public override void ViewDidLoad()
    {
        base.ViewDidLoad();
        dataGrid.ItemsSource = viewModel.OrdersInfo; 
        dataGrid.GroupColumnDescriptions.Add(new GroupColumnDescription()
        {
            ColumnName = "Freight",
        });
        stackView.Axis = UILayoutConstraintAxis.Vertical;
        clearGroupingButton.SetTitle("Remove Grouping", UIControlState.Normal);
        clearGroupingButton.BackgroundColor=UIColor.White;
        clearGroupingButton.SetTitleColor(UIColor.Black, UIControlState.Normal);
        clearGroupingButton.TouchDown += ClearGroupingButton_TouchDown;
        clearGroupingButton.HeightAnchor.ConstraintEqualTo(200).Active = true;
        dataGrid.HeightAnchor.ConstraintEqualTo(600).Active=true;
        stackView.AddArrangedSubview(removeGroupingButton);
        stackView.AddArrangedSubview(dataGrid);
        this.View.AddSubview(stackView);
    }

    private void ClearGroupingButton_TouchDown(object sender, System.EventArgs e)
    {
        //Clearing the Group
        dataGrid.GroupColumnDescriptions.Clear();

        //Removing the Group based on group item
        //var groupColumn = dataGrid.GroupColumnDescriptions[0];
        //dataGrid.GroupColumnDescriptions.Remove(groupColumn);
        
        //Removing the Group based on group index
        //dataGrid.GroupColumnDescriptions.RemoveAt(0);
    }

    public override void ViewDidLayoutSubviews()
    {
        stackView.Frame = new CGRect(0, 30, this.View.Frame.Width, this.View.Frame.Height);
        base.ViewDidLayoutSubviews();
    }
}
{% endhighlight %}

Run the application to render the following output. 

![](SfDataGrid_images/Remove_Grouping.png)

N> You can also clear or remove the grouping on [GridTappedEventsArgs](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridTappedEventsArgs.html), [GridDoubleTappedEventsArgs](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridDoubleTappedEventsArgs.html) or [GridLongPressedEventsArgs](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GridLongPressedEventsArgs.html)

## Events

### GroupExpanding event

The [SfDataGrid.GroupExpanding](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~GroupExpanding_EV.html) event occurs when the group is being expanded.
 
The [GroupChangingEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GroupChangingEventArgs.html) of the `GroupExpanding` event provides the information about the expanding group and it has the following members.

[Syncfusion.Data.Group](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GroupChangingEventArgs~Group.html) - Gets the group that’s being expanded.

[Cancel](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true) – Decides whether to cancel the group expansion.
 
You can cancel the group expansion by setting `GroupChangingEventArgs.Cancel` to `true`.

{% highlight c# %}
this.dataGrid.GroupExpanding += dataGrid_GroupExpanding;

void dataGrid_GroupExpanding(object sender, Syncfusion.SfDataGrid.GroupChangingEventArgs e)
{
    if (e.Group.Key.Equals(1001))    
        e.Cancel = true;    
}       
{% endhighlight %}

### GroupExpanded event

The [SfDataGrid.GroupExpanded](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~GroupExpanded_EV.html) event occurs after the group is expanded.

The [GroupChangedEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GroupChangedEventArgs.html) of the `GroupExpanded` event provides the information about the expanded group and it has the following member.

[Syncfusion.Data.Group](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.GroupChangedEventArgs~Group.html) - Gets the expanded group.

### GroupCollapsing event 

The [SfDataGrid.GroupCollapsing](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~GroupCollapsing_EV.html) event occurs when the group is being collapsed.

The `GroupChangingEventArgs` of the `GroupCollapsing` event provides the information about the collapsing group and it contains the following member.

`Syncfusion.Data.Group` - Gets the group that’s being collapsed.

`Cancel` – Decides whether to cancel the group collapsing.

You can cancel the group is being collapsed by using `GroupChangingEventArgs.Cancel` of `GroupCollapsing` event.

{% highlight c# %}
this.dataGrid.GroupCollapsing += dataGrid_GroupCollapsing;

void dataGrid_GroupCollapsing(object sender, Syncfusion.SfDataGrid.GroupChangingEventArgs e)
{
    if (e.Group.Key.Equals(1001))    
        e.Cancel = true;    
}
{% endhighlight %}

### GroupCollapsed event
 
The [SfDataGrid.GroupCollapsed](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfdatagrid/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~GroupCollapsed_EV.html) event occurs after the group is collapsed.
 
`GroupChangedEventArgs` of the `GroupCollapsed` event  provides the information about collapsed group and it contains the following member.

`Syncfusion.Data.Group` - Gets the collapsed group.

## Animate group expand/collapse icon

SfDatagrid loads two different icons for denoting the group expanded and collapsed state. However, SfDataGrid allows you to rotate the expander icon animatedly for denoting the collapsed status by overriding the `DataGridStyle.GetGroupCollapseIcon` method and returning `null`.

The below code example illustrates how to enable the group/expand collapse icons animation by writing a custom style. 

{% tabs %}
{% highlight c# %}

//Apply custom style to SfDataGrid from code 

dataGrid.GridStyle = new CustomStyle ();

//Custom Style class

public class CustomStyle : DataGridStyle
{ 
   public CustomStyle ()
   {
       
   }
   public override ImageSource GetGroupCollapseIcon()
   {
       return null;
   }
}

{% endhighlight %}
{% endtabs %}

## Hiding the column when grouped

In SfDataGrid a column will be generated with the default column width by default. In order to group by a column that should not be visible in view, add the column to the [SfDataGrid.Columns](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~Columns.html) collection and set its width as 0. Thus the column will be grouped and will not be visually seen. Please refer the below code example.

{% highlight c# %}
dataGrid.Columns.Add (new GridTextColumn () { 
    MappingName = "ShippingDate",
    Width = 0
});

dataGrid.GroupColumnDescriptions.Add (new GroupColumnDescription () { 
    ColumnName = "ShippingDate"
});
{% endhighlight %}