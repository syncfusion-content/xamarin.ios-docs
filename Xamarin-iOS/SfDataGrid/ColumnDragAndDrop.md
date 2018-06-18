---
layout: post
title: Column Drag and Drop | SfDataGrid | Xamarin | Syncfusion
description: How to enable and perform column drag and drop operation and its customization.
platform: xamarin.ios
control: SfDataGrid
documentation: UG
---

# Column Drag and Drop

The data grid allows dragging and dropping a column header by setting the [SfDataGrid.AllowDraggingColumn](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~AllowDraggingColumn.html) property to `true`. The drag view is displayed when dragging the column header. Drag and drop operations can be handled using the [SfDataGrid QueryColumnDragging](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~QueryColumnDragging_EV.html) event. 

The following code example illustrates how to enable column drag and drop in SfDataGrid.

{% highlight c# %}
sfGrid.AllowDraggingRow = true;
{% endhighlight %}

## Column drag and drop event

The `QueryColumnDragging` event is fired when dragging a column, and will be continuously fired until the dragging ends. By handing the `SfDataGrid.QueryColumnDragging ` event, you can cancel the dragging of a particular column header.

The `QueryColumnDragging` event provides the following arguments through [QueryColumnDraggingEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.QueryColumnDraggingEventArgs.html):

* [From](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.QueryColumnDraggingEventArgs~From.html): Returns the index of the dragging column.
* [To](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.QueryColumnDraggingEventArgs~To.html): Returns the dragging index where you try to drop the column.
* [Reason](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.QueryColumnDraggingEventArgs~Reason.html): Returns column dragging details as `QueryColumnDraggingReason`.
* [DraggingPosition](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.QueryColumnDraggingEventArgs~DraggingPosition.html): Returns the position of the drag view during column drag and drop operations.
* [Cancel](https://msdn.microsoft.com/en-us/library/system.componentmodel.canceleventargs_properties(v=vs.110).aspx): Returns a Boolean property to cancel the event.

![](SfDataGrid_images/ColumnDragAndDrop.png)

## Customize column drag and drop indicators

The data grid allows customizing the column drag and drop indicators by writing a custom grid style deriving from the [DataGridStyle](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.DataGridStyle.html) and assigning it to the [SfDataGrid.GridStyle](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~GridStyle.html) property.

The following code example shows how to customize the column drag and drop indicators in the data grid:

{% highlight c#%}

dataGrid.GridStyle = new CustomGridStyle();

{% endhighlight %}

{% highlight c#%}
// Custom style class
public class CustomGridStyle : DataGridStyle
{
    public CustomGridStyle()
    {     
    }
    public override UIImage GetColumnDragUpIndicator()
    {
        return new ImageMapStream(LoadResource("GreenUp.png").ToArray()).ToUIImage();
    }
    public override UIImage GetColumnDragDownIndicator()
    {
        return new ImageMapStream(LoadResource("GreenDown.png").ToArray()).ToUIImage();
    }
}
{% endhighlight %}

![](SfDataGrid_images/CustomizeColumnDragAndDrop.png)

## How to

### Cancel dragging for a particular column

Dragging can be canceled for a particular column by handling the `QueryColumnDragging` event and using conditions based on [QueryColumnDraggingReason](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.QueryColumnDraggingReason.html). Refer to the following code sample to cancel dragging for a particular column:

{% highlight c# %}

private void SfGrid_QueryColumnDragging(object sender, QueryColumnDraggingEventArgs e)
{
    //e.From returns the index of the dragged column.
    //e.Reason returns the dragging status of the column.
    if (e.From == 1 && e.Reason == QueryColumnDraggingReason.DragStarted)
        e.Cancel = true;
}

{% endhighlight %}

### cancel dropping when dragging over particular columns

Dropping can be canceled over particular columns while dragging a column.Refer to the following code sample to cancel dropping over particular columns:

{% highlight c# %}

private void SfGrid_QueryColumnDragging(object sender, QueryColumnDraggingEventArgs e)
{
    //e.To returns the index of the current column.
    //e.Reason returns the dragging status of the column.
    if ((e.To > 5 || e.To < 10) &&
    (e.Reason == QueryColumnDraggingReason.DragEnded || e.Reason == QueryColumnDraggingReason.Dragging))
        e.Cancel = true;
} 

{% endhighlight %}

### cancel dropping for a particular column

Dropping can be canceled for a particular column by handling the `QueryColumnDragging` event and using conditions based on `QueryColumnDraggingReason`. Refer to the following code sample to cancel dropping for a particular column:

{% highlight c# %}

private void SfGrid_QueryColumnDragging(object sender, QueryColumnDraggingEventArgs e)
{
    //e.From returns the index of the dragged column.
    //e.Reason returns the dragging status of the column.
    if (e.From == 1 && e.Reason == QueryColumnDraggingReason.DragEnded)
        e.Cancel = true;
}

{% endhighlight %}

### cancel dropping at a particular position

Dropping at a particular position can be canceled by handling the `QueryColumnDragging` event and using conditions based on `QueryColumnDraggingReason`. Refer to the following code sample to cancel dropping at a particular position:

{% highlight c# %}

private void SfGrid_QueryColumnDragging(object sender, QueryColumnDraggingEventArgs e)
{
    //e.To returns the index of the current column.
    //e.Reason returns the dragging status of the column.
    if ((e.To == 5 || e.To == 7) && e.Reason == QueryColumnDraggingReason.DragEnded)
        e.Cancel = true;
}

{% endhighlight %}