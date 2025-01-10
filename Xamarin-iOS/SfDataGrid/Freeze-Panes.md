---
layout: post
title: Freeze Panes | SfDataGrid | Xamarin.iOS | Syncfusion
description: How to freeze rows and columns in a SfDataGrid.
platform: xamarin.ios
control: SfDataGrid
documentation: UG
---

# Freeze panes

SfDataGrid allows you to freeze the rows and columns when scrolling the grid.

## Freeze Rows

SfDataGrid provides extensive support to freeze the rows at the top of the view below the header row by setting the [SfDataGrid.FrozenRowsCount](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_FrozenRowsCount) property. 

The following code example illustrates freezing two rows in SfDataGrid.

{% highlight c# %}
//Setting number of rows to freeze in SfDataGrid
dataGrid.FrozenRowsCount = 2; 
{% endhighlight %}

### Limitation

* `FrozenRowsCount` should be lesser than the number of rows that is displayed in View.
* For example: 
If you have 10 rows in view, then you set `FrozenRowsCount` to a maximum value of 9.

N> Header row is frozen by default and works regardless of the `FrozenRowsCount` property.


## Freeze Columns

SfDataGrid also provides support to freeze the columns at the left of the view by setting the [SfDataGrid.FrozenColumnsCount](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_FrozenColumnsCount) property. 

The following code example illustrates freezing two columns in SfDataGrid.

{% highlight c# %}
//Setting number of columns to freeze in SfDataGrid
dataGrid.FrozenColumnsCount = 2;  
{% endhighlight %}

### Limitation

* `FrozenColumnsCount` should be lesser than number of columns displayed in View.
* For example: 
If you have 5 columns in view, then you can set `FrozenColumnsCount` to a maximum value of 4.

N> RowHeader is frozen by default and works regardless of the `FrozenColumnsCount` property.
