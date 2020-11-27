---
layout: post
title: Working with Xamarin.iOS TreeView | TreeView for Xamarin.iOS | Syncfusion
description: This topic describes how to use Syncfusion Xamarin.iOS TreeView along with interacting events and other different functionalities
platform: Xamarin.iOS
control: SfTreeView
documentation: ug
---

# Working with TreeView in Xamarin.iOS TreeView (SfTreeView)

## Interacting with TreeView Items

### Loaded event

The [Loaded](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.TreeView.SfTreeView.html) event is raised when the TreeView is loading in view for the first time.

{% tabs %}
{% highlight c# %}
treeView.Loaded += TreeView_Loaded;

private void TreeView_Loaded(object sender, TreeViewLoadedEventArgs e)
{
	var alert = UIAlertController.Create ("TreeView", "Loaded in the view", UIAlertControllerStyle.Alert);
	alert.AddAction (UIAlertAction.Create ("OK", UIAlertActionStyle.Default, null));
	PresentViewController (alert, true, null);
}
{% endhighlight %}
{% endtabs %}

The `Loaded` event is used for the following use case:

* To scroll the desired item by using the [BringIntoView](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.TreeView.SfTreeView.html).

### Tapped event

The [ItemTapped](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.TreeView.SfTreeView.html) event will be triggered whenever tapping the item.  [ItemTappedEventArgs](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.TreeView.ItemTappedEventArgs.html) has the following members which provides the information for `ItemTapped` event:

 * `Node`: Gets the [TreeViewNode](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.TreeView.Engine.TreeViewNode.html) and data associated with the tapped item as its arguments.
 * `Position`: Gets the touch position in the tapped item.
 * `Handled`: Gets or sets whether the event is handled or not.

{% tabs %}
{% highlight c# %}

treeView.ItemTapped += TreeView_ItemTapped;

private void TreeView_ItemTapped(object sender, ItemTappedEventArgs e)
{
	var alert = UIAlertController.Create ("TreeView", "ItemTapped", UIAlertControllerStyle.Alert);
	alert.AddAction (UIAlertAction.Create ("OK", UIAlertActionStyle.Default, null));
	PresentViewController (alert, true, null);
}

{% endhighlight %}
{% endtabs %}

### ItemDoubleTapped event

The [ItemDoubleTapped](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.TreeView.SfTreeView.html) event will be triggered whenever double tapping the item. The [ItemDoubleTappedEventArgs](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.TreeView.ItemDoubleTappedEventArgs.html) has the following members providing information for the `ItemDoubleTapped` event:

 * `Node`: Gets the [TreeViewNode](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.TreeView.Engine.TreeViewNode.html) and data associated with the double tapped item as its arguments.
 * `Position`: Gets the touch position in the double tapped item.
 * `Handled`: Gets or sets whether the event is handled or not.

{% tabs %}
{% highlight c# %}

treeView.ItemDoubleTapped += TreeView_ItemDoubleTapped;

private void TreeView_ItemDoubleTapped(object sender, ItemDoubleTappedEventArgs e)
{
	var alert = UIAlertController.Create ("TreeView", "ItemDoubleTapped", UIAlertControllerStyle.Alert);
	alert.AddAction (UIAlertAction.Create ("OK", UIAlertActionStyle.Default, null));
	PresentViewController (alert, true, null);
}

{% endhighlight %}
{% endtabs %}

### ItemHolding event

The [ItemHolding](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.TreeView.SfTreeView.html) event will be triggered whenever the item is long pressed.
 [ItemHoldingEventArgs](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.TreeView.ItemHoldingEventArgs.html) has the following members which provides the information for `ItemHolding` event:

 * `Node`: Gets the [TreeViewNode](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.TreeView.Engine.TreeViewNode.html) and data associated with the hold item as its arguments.
 * `Position`: Gets the touch position in the hold item.
 * `Handled`: Gets or sets whether the event is handled or not.

{% tabs %}
{% highlight c# %}

treeView.ItemHolding += TreeView_ItemHolding;
private void TreeView_ItemHolding(object sender, ItemHoldingEventArgs e)
{
	var alert = UIAlertController.Create ("TreeView", "ItemHolding", UIAlertControllerStyle.Alert);
	alert.AddAction (UIAlertAction.Create ("OK", UIAlertActionStyle.Default, null));
	PresentViewController (alert, true, null);
}

{% endhighlight %}
{% endtabs %}

### Update the runtime changes

The [PropertyChanged](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_PropertyChanged) event will be triggered whenever a properties in TreeViewNode is changed. You can get the name of the property that changed by using the `PropertyName` property of the `PropertyChangedEventArgs`.

{% tabs %}
{% highlight c# %}
treeviewnode.PropertyChanged += Treeviewnode_PropertyChanged;

private void Treeviewnode_PropertyChanged(object sender, PropertyChangedEventArgs e)
{
    if (treeviewnode.IsExpanded)
        DisplayAlert("treeview", "nodeexpanded", "ok");
    else
        DisplayAlert("treeview", "nodecollapsed", "ok");
}
{% endhighlight %}
{% endtabs %}

### Refresh layout

[SetDirty](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_SetDirty) notifies the TreeViewNode to recalculate the child collection update mechanism to invalidate that node which helps to update the engine and refresh the UI.

{% tabs %}
{% highlight c# %}
node.SetDirty();
{% endhighlight %}
{% endtabs %}

