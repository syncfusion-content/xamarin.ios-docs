---
layout: post
title: Row Drag and Drop | SfDataGrid | Xamarin | Syncfusion
description:  How to enable and perform row drag and drop operation and its customization.
platform: xamarin.ios
control: SfDataGrid
documentation: UG
---

# Row Drag and Drop

SfDataGrid allows you to drag and drop a row by setting the [SfDataGrid.AllowDraggingRow](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~AllowDraggingRow.html) property to `true`. A Customizable row drag and drop template is displayed  while dragging a row. The drag and drop operation can be handled based on the requirement using [SfDataGrid.QueryRowDragging](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~AllowDraggingRow.html) event. 

The following code example illustrates how to enable row drag and drop in SfDataGrid.

{% tabs %}
{% highlight c# %}
sfGrid.AllowDraggingRow = true;
{% endhighlight %}
{% endtabs %}

![Row drag and drop](SfDataGrid_images/Rowdraganddrop.gif)

## Dragging scenarios

SfDataGrid allows you to perform the drag and drop operation with both the data rows and groups.

* Records can be reordered to any position with auto scrolling.
* Groups position can be reordered using drag and drop. But no groups can be added inside other groups. 
* Data rows can be reordered within the same group or into the other groups as well. 

N> Reordering changes are made only in `SfDataGrid.View` and not in the underlying data. Thus the changes will be reverted when performing sorting, grouping or any other operation that refreshes the view. Reordering underlying data can be achieved by handling `QueryRowDragging` event in the sample side as explained below in [Reordering underlying data](# Reordering underlying data ).

## Row drag and drop template

SfDataGrid allows you to load a desired content when performing row drag and drop operation using the [SfDataGrid.RowDragDropTemplate](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~RowDragDropTemplate.html). 

## Default template

Default template will be loaded, if template is not explicitly assigned for row drag and drop operations. 

![Default template for row drag view](SfDataGrid_images/DefaultTemplateIOS.png)

## Customizing row drag and drop template

You can load any type of custom view inside `SfDataGrid.RowDragDropTemplate` based on your application’s  requirement.

Refer the following code example that shows how to load row like view in template.

{% tabs %}
{% highlight c# %}

//Assigning custom view to row drag and drop template.
sfGrid.RowDragDropTemplate = new RowDragDropTemplate();

sfGrid.QueryRowDragging += SfGrid_QueryRowDragging;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

private void SfGrid_QueryRowDragging(object sender, QueryRowDraggingEventArgs e)
{
     if (e.Reason == QueryRowDraggingReason.DragStarted)
     {
        (sfGrid.RowDragDropTemplate as RowDragDropTemplate).UpdateRow(e.RowData);
     }         
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
//Row template a custom view which represent row.

public class RowDragDropTemplate : UIView
{
    #region Field

    UILabel label1;
    UILabel label2;
    UILabel label3;
    UILabel label4;

    #endregion

    #region Constructor 

    public RowDragDropTemplate()
    {
        label1 = new UILabel() { TextAlignment = UITextAlignment.Center, TextColor = UIColor.Black, LineBreakMode = UILineBreakMode.TailTruncation, Font = UIFont.FromName("HelveticaNeue", 12) };
        label2 = new UILabel() { TextAlignment = UITextAlignment.Center, TextColor = UIColor.Black, LineBreakMode = UILineBreakMode.TailTruncation, Font = UIFont.FromName("HelveticaNeue", 12) };
        label3 = new UILabel() { TextAlignment = UITextAlignment.Center, TextColor = UIColor.Black, LineBreakMode = UILineBreakMode.TailTruncation, Font = UIFont.FromName("HelveticaNeue", 12) };
        label4 = new UILabel() { TextAlignment = UITextAlignment.Center, TextColor = UIColor.Black, LineBreakMode = UILineBreakMode.TailTruncation, Font = UIFont.FromName("HelveticaNeue", 12) };

        this.AddSubview(label1);
        this.AddSubview(label2);
        this.AddSubview(label3);
        this.AddSubview(label4);

        this.Layer.MasksToBounds = true;
        this.Layer.AllowsEdgeAntialiasing = true;
        this.Layer.BorderWidth = 0.25f;
        this.Layer.BorderColor = UIColor.Black.CGColor;
    }

    #endregion

    #region Method

    public void UpdateRow(object rowData)
    {
        try
        {
            var orderInfo = rowData as OrderInfo;
            label1.Text = orderInfo.OrderID;
            label2.Text = orderInfo.EmployeeID;
            label3.Text = orderInfo.CustomerID;
            label4.Text = orderInfo.FirstName;
        }
        catch { }
    }

    public override void LayoutSubviews()
    {
        base.LayoutSubviews();
        label1.Frame = new CGRect(0, 0, this.Frame.Width / 4, this.Frame.Height);
        label2.Frame = new CGRect(this.Frame.Width / 4, 0, this.Frame.Width / 4, this.Frame.Height);
        label3.Frame = new CGRect((this.Frame.Width / 4) * 2, 0, this.Frame.Width / 4, this.Frame.Height);
        label4.Frame = new CGRect((this.Frame.Width / 4) * 3, 0, this.Frame.Width / 4, this.Frame.Height);
    }

    #endregion
}

{% endhighlight %}
{% endtabs %}

![Customized template for row drag view](SfDataGrid_images/CustomizedTemplate.png)

You can download the customizing row drag-and-drop template sample [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/RowDragandDropTemplate_IOS1749446243).

## Events in row drag and drop

`QueryRowDragging` event is fired upon starting to drag a row and will be continuously fired till the dragging ends. By handing the `SfDataGrid.QueryRowDragging` event you can also cancel the dragging of a particular row.

The `QueryRowDragging` event provides following properties in [QueryRowDraggingEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.QueryRowDraggingEventArgs.html):

* [From](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.QueryRowDraggingEventArgs~From.html) – Returns the index of the row currently being dragged.
* [To](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.QueryRowDraggingEventArgs~To.html) – Returns the dragging index where you try to drop the row. 
* [Reason](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.QueryRowDraggingEventArgs~Reason.html) – Returns row dragging details as `QueryRowDraggingReason`.
* [RowData](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.QueryRowDraggingEventArgs~RowData.html) – Returns the underlying data associated with the dragged row.
* [CurrentRowData](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.QueryRowDraggingEventArgs~CurrentRowData.html)  – Returns the corresponding row data, over which the row drag view is currently placed.
* [CanAutoScroll](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.QueryRowDraggingEventArgs~CanAutoScroll.html): Returns whether auto-scrolling should happen when row drag view reaches the top or bottom of the `SfDataGrid`.
* [Cancel](https://msdn.microsoft.com/en-us/library/system.componentmodel.canceleventargs_properties(v=vs.110).aspx) – A Boolean property to cancel the event.

## Cancel dragging for particular row

Dragging of a particular row can be canceled using [QueryRowDraggingReason](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.QueryRowDraggingReason.html) argument of the `QueryRowDragging` event handler. 

{% tabs %}
{% highlight c# %}

this.SfGrid.QueryRowDragging += SfGrid_QueryRowDragging;

private void SfGrid_QueryRowDragging(object sender, QueryRowDraggingEventArgs e)
{
    //e.From returns the index of the dragged row.
    //e.Reason returns the dragging status of the row.
    if (e.From == 1 && e.Reason == QueryRowDraggingReason.DragStarted)
        e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

## Cancel dropping when dragging over particular rows

Dropping when dragging over particular rows can be canceled using `QueryRowDraggingReason` argument of the `QueryRowDragging` event handler.

{% tabs %}
{% highlight c# %}

this.SfGrid.QueryRowDragging += SfGrid_QueryRowDragging;

private void SfGrid_QueryRowDragging(object sender, QueryRowDraggingEventArgs e)
{
    //e.To returns the index of the current row.
    //e.Reason returns the dragging status of the row.
    if ((e.To > 5 || e.To < 10) &&
    (e.Reason == QueryRowDraggingReason.DragEnded || e.Reason == QueryRowDraggingReason.Dragging))
        e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

## Cancel dropping of particular row 

Dropping of a particular row can be canceled using `QueryRowDraggingReason` argument of the `QueryRowDragging` event handler.

{% tabs %}
{% highlight c# %}

this.SfGrid.QueryRowDragging += SfGrid_QueryRowDragging;

private void SfGrid_QueryRowDragging(object sender, QueryRowDraggingEventArgs e)
{
    //e.From returns the index of the dragged row.
    //e.Reason returns the dragging status of the row.
    if (e.From == 1 && e.Reason == QueryRowDraggingReason.DragEnded)
        e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

## Cancel dropping at a particular position

Dropping at a particular position can be canceled using `QueryRowDraggingReason` argument of the `QueryRowDragging` event handler. 

{% tabs %}
{% highlight c# %}

this.SfGrid.QueryRowDragging += SfGrid_QueryRowDragging;

private void SfGrid_QueryRowDragging(object sender, QueryRowDraggingEventArgs e)
{
    //e.To returns the index of the current row.
    //e.Reason returns the dragging status of the row.
    if ((e.To == 5 || e.To == 7) && e.Reason == QueryRowDraggingReason.DragEnded)
        e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

## Cancel dropping of a particular row in a position

Dropping of a particular row in a position can be canceled using the `QueryRowDraggingReason` and `Position` arguments of the `QueryRowDragging` event handler. 

{% tabs %}
{% highlight c# %}

this.SfGrid.QueryRowDragging += SfGrid_QueryRowDragging;

private void SfGrid_QueryRowDragging(object sender, QueryRowDraggingEventArgs e)
{
     //e.To returns the index of the current row.
     //e.Position returns the x and y position of the current row
      if ((e.To == 3) && e.Position == new Point(60,280) && e.Reason == QueryRowDraggingReason.DragEnded)
        e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}   

## Cancel drag and drop between frozen and non-frozen rows

### Cancel dragging between frozen and non-frozen rows

Dragging between frozen and non-frozen rows can be canceled using `QueryRowDraggingReason` and `From` arguments of the `QueryRowDragging` event handler by checking whether the value of `From` argument is a frozen row index.

{% tabs %}
{% highlight c# %}

SfGrid.FrozenRowsCount = 4;

this.SfGrid.QueryRowDragging += SfGrid_QueryRowDragging;

private void SfGrid_QueryRowDragging(object sender, QueryRowDraggingEventArgs e)
{
     //e.From returns the index of the dragged frozen row.
     //e.To returns the index of the current row.
      if (e.From > sfGrid.GetHeaderIndex() && e.From <= sfGrid.FrozenRowsCount && e.Reason == QueryRowDraggingReason.DragStarted)
        e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

### Cancel dropping between frozen and non-frozen rows

Dropping between frozen and non-frozen rows can be canceled using `QueryRowDraggingReason` and `From` arguments of the `QueryRowDragging` event handler by checking whether the value of `From` argument is a frozen row index. 

{% tabs %}
{% highlight c# %}

SfGrid.FrozenRowsCount = 4;

this.SfGrid.QueryRowDragging += SfGrid_QueryRowDragging;

private void SfGrid_QueryRowDragging(object sender, QueryRowDraggingEventArgs e)
{
      //e.From returns the index of the dragged frozen row.
      //e.To returns the index of the current row.
      if (e.From > sfGrid.GetHeaderIndex() && e.From <= sfGrid.FrozenRowsCount && e.Reason == QueryRowDraggingReason.DragEnded)
        e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

N> FrozenRowsCount must be less than rows in view.

## Reorder the underlying data

Reordering changes directly on the underlying data can be done using `QueryRowDraggingReason` argument of the `QueryRowDragging` event handler. Refer following code sample to make permanent reordering changes.

{% tabs %}
{% highlight c# %}

this.SfGrid.QueryRowDragging += SfGrid_QueryRowDragging;

private void SfGrid_QueryRowDragging(object sender, QueryRowDraggingEventArgs e)
{
    //e.To returns the index of the current row.
    //e.From returns the index of the dragged row.
    if (e.Reason == QueryRowDraggingReason.DragEnded)
    {
        var collection = (sender as SfDataGrid).ItemsSource as IList;
        collection.RemoveAt(e.From - 1);
        collection.Insert(e.To - 1, e.RowData);
    }
}

{% endhighlight %}
{% endtabs %}

## Drop a grid row in the last position

The `To` property of the `QueryRowDraggingEventArgs` denotes the current drop index of the dragged row when dragging over the grid rows. It returns the same index when you drag a row over the rows in last position or last but one. In order to programmatically track whether the dragged row is dropped at the last position or last but one, SfDataGrid provides the `Position` property in `QueryRowDraggingEventArgs` which denotes the position of the RowDragView.

Refer the following code example in which the `Position` property is used to determine whether the row is dropped in the last position.

{% tabs %}
{% highlight c# %}

this.SfGrid.QueryRowDragging += SfGrid_QueryRowDragging;

private void SfGrid_QueryRowDragging(object sender, QueryRowDraggingEventArgs e)
{
    var totalHeight = dataGrid.RowColumnIndexToPoint(new RowColumnIndex(viewModel.OrdersInfo.Count, 0)).Y + this.dataGrid.RowHeight;
    if (e.Reason == QueryRowDraggingReason.DragEnded)
    {
        if (Math.Ceiling(e.Position.Y + (dataGrid.RowHeight / 2)) > totalHeight && e.To == viewModel.OrdersInfo.Count)
        {
            // Will hit if the row is dropped at the last position                 
            UIAlertView alert = new UIAlertView("RowDragAndDrop info", "The row is dropped at the last position", null, "OK");
            alert.Show();     
        }
    }
}

{% endhighlight %}
{% endtabs %}

## Customizing row drag-and-drop indicators

The SfDataGrid allows you to customize the row drag-and-drop indicators by writing a custom grid style, deriving from [DataGridStyle](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.DataGridStyle.html) and assigning it to the [SfDataGrid.GridStyle](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~GridStyle.html) property.

{% tabs %}
{% highlight c#%}

dataGrid.GridStyle = new CustomGridStyle();

{% endhighlight %}
{% endtabs %}  

{% tabs %}
{% highlight c#%}

// Custom style class
public class CustomGridStyle : DataGridStyle
{
    public CustomGridStyle()
    {
    }
    public override UIImage GetRowDragDownIndicator()
    {
        return new ImageMapStream(LoadResource("RedDown.png").ToArray()).ToUIImage();
    }
    public override UIImage GetRowDragUpIndicator()
    {
        return new ImageMapStream(LoadResource("RedUp.png").ToArray()).ToUIImage();
    }
}

{% endhighlight %}
{% endtabs %}

![Cutsomized row drag and drop indicator](SfDataGrid_images/CustomizedIndicator_ROW.png)

## Updating summaries when dragging and dropping a row between groups

Grouping and summaries of items in SfDataGrid are manipulated based on group key. When you drag and drop an item from one group to another group, the group key of the dragged item will differ from the group key of the items in the dropped group. Hence by default, the summaries will not be updated. This is the actual behavior of SfDataGrid. 

Hence, in order to update the summaries when a row is dragged and dropped between groups you need to call the `UpdateCaptionSummaries` and `Refresh` methods in the `QueryRowDragging` event.

{% tabs %}
{% highlight c#%}
public class MyViewController:UIViewController
{
    SfDataGrid dataGrid;
    ViewModel viewModel;
    public MyViewController()
    {
         dataGrid = new SfDataGrid();
         viewModel = new ViewModel();
     }
     public override void ViewDidLoad()
     {
         base.ViewDidLoad();
         this.View.BackgroundColor = UIColor.White;
         dataGrid.ItemsSource = viewModel.OrdersInfo;
         dataGrid.ColumnSizer = ColumnSizer.Auto;
         dataGrid.AutoGenerateColumns = true;
         dataGrid.GroupColumnDescriptions.Add(new GroupColumnDescription() { ColumnName = "CustomerID" });
         dataGrid.AllowDraggingRow = true;
         dataGrid.QueryRowDragging += DataGrid_QueryRowDragging;

         GridSummaryRow summaryRow = new GridSummaryRow();
         summaryRow.Title = "Total Salary:{TotalSalary}";
         summaryRow.ShowSummaryInRow = true;
         summaryRow.SummaryColumns.Add(new GridSummaryColumn()
         {
              Name = "TotalSalary",
              MappingName = "Salary",
              Format = "'{Count}'",
              SummaryType = SummaryType.CountAggregate
         });
         dataGrid.CaptionSummaryRow = summaryRow;
      }

      public override void ViewDidLayoutSubviews()
      {
         dataGrid.Frame = new CGRect(0, 50, View.Frame.Width, View.Frame.Height - 20);
         base.ViewDidLayoutSubviews();
      }

      private async void DataGrid_QueryRowDragging(object sender,  QueryRowDraggingEventArgs e)
      {
          if (e.Reason == QueryRowDraggingReason.DragEnded)
          {
              await Task.Delay(100);
              this.dataGrid.View.TopLevelGroup.UpdateCaptionSummaries();
              this.dataGrid.View.Refresh();
          }
      }
            
}
{% endhighlight %}
{% endtabs %}

The following screenshot shows the output rendered when executing the above code example.

![Update summary during row drag and drop](SfDataGrid_images/UpdatedSummary.png)

## Cancel auto scrolling

Vertical auto-scrolling of the `SfDataGrid` during row drag and drop can be canceled using `CanAutoScroll` argument of the `QueryRowDragging` event handler.

{% tabs %}
{% highlight c# %}

this.SfGrid.QueryRowDragging += SfGrid_QueryRowDragging;

private void SfGrid_QueryRowDragging(object sender, QueryRowDraggingEventArgs e)
{  
    // Disable scroll while dragging and dropping the Rows.    
    e.CanAutoScroll = false;
}

{% endhighlight %}
{% endtabs %}
