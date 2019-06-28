---
layout: post
title: ItemSelected Event in Syncfusion SfTreeMap control
description: This section explains the ItemSelected event support in TreeMap. 
platform: Xamarin.Android
control: TreeMap
documentation: ug
---

# TreeMap Events

## ItemSelected

The [`ItemSelected`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfTreeMap.Android~Com.Syncfusion.Treemap.SfTreeMap~ItemSelected_EV.html) event occurs when an item is selected. The selected leaf node underlying data item and IsSelected boolean property will be passed as arguments to [`ItemSelectedEventArgs`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfTreeMap.Android~Com.Syncfusion.Treemap.TreeMapSelectedEventArgs.html). The [`IsSelected`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfTreeMap.Android~Com.Syncfusion.Treemap.TreeMapSelectedEventArgs~IsSelected.html) property indicates whether the item has been selected.

Set the [`HighlightOnSelection`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfTreeMap.Android~Com.Syncfusion.Treemap.SfTreeMap~HighlightOnSelection.html) property to true to use the `ItemSelected` event.

{% tabs %}

{% highlight C# %}

treeMap.HighlightOnSelection = true;

treeMap.ItemSelected += TreeMap_ItemSelected;

private void TreeMap_ItemSelected(object sender, TreeMapSelectedEventArgs e)
        {
           
        }

{% endhighlight %}

{% endtabs %}
