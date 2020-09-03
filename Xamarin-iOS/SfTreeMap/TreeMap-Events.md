---
layout: post
title: ItemSelected Event in Syncfusion SfTreeMap control
description: This section explains the ItemSelected event support in TreeMap. 
platform: Xamarin.iOS
control: TreeMap
documentation: ug
---

# TreeMap Events

## ItemSelected

The [`ItemSelected`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFTreeMap.html) event occurs when an item is selected. The selected leaf node underlying data item and the IsSelected boolean property will be passed as arguments to [`TreeMapItemSelectedEventArgs`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.TreeMapItemSelectedEventArgs.html). The [`IsSelected`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.TreeMapItemSelectedEventArgs.html#Syncfusion_SfTreeMap_iOS_TreeMapItemSelectedEventArgs_IsSelected) property indicates whether the item has been selected.

Set the [`HighlightOnSelection`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFTreeMap.html#Syncfusion_SfTreeMap_iOS_SFTreeMap_HightlightOnSelection) property to true to use the `ItemSelected` event.

{% tabs %}

{% highlight C# %}

treeMap.HightlightOnSelection = true;

treeMap.ItemSelected += TreeMap_ItemSelected;

  void TreeMap_ItemSelected(object sender, TreeMapItemSelectedEventArgs e)
        {

        }

{% endhighlight %}

{% endtabs %}
