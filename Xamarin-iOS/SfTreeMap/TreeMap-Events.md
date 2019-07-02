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

The [`ItemSelected`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFTreeMap~ItemSelected_EV.html) event occurs when an item is selected. The selected leaf node underlying data item and IsSelected boolean property will be passed as arguments to [`TreeMapItemSelectedEventArgs`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.TreeMapItemSelectedEventArgs.html). The [`IsSelected`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.TreeMapItemSelectedEventArgs~IsSelected.html) property indicates whether the item has been selected.

Set the [`HighlightOnSelection`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFTreeMap~HightlightOnSelection.html) property to true to use the `ItemSelected` event.

{% tabs %}

{% highlight C# %}

treeMap.HighlightOnSelection = true;

treeMap.ItemSelected += TreeMap_ItemSelected;

private void TreeMap_ItemSelected(object sender, TreeMapSelectedEventArgs e)
        {
           
        }

{% endhighlight %}

{% endtabs %}
