---
layout: post
title: Scrolling | TreeView for Xamarin.iOS | Syncfusion
description: Describes about programmatic scrolling of treeview.
platform: Xamarin.iOS
control: SfTreeView
documentation: ug
---

# Scrolling

## Programmatic scrolling

### Bring InTo View

The TreeView allows programmatically scrolling based on the data model and [TreeViewNode](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeView.iOS~Syncfusion.TreeView.Engine.TreeViewNode.html) by using the [BringIntoView](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeView.iOS~Syncfusion.iOS.TreeView.SfTreeView~BringIntoView.html) method.

It also enables and disables the scrolling animation when changing the view. By default, the scrolling will be animated.

{% tabs %}
{% highlight c# %}

SfTreeView treeView;
FileManagerViewModel viewModel;

public override void ViewDidLoad()
{
    base.ViewDidLoad();
    // Perform any additional setup after loading the view
    SfTreeView treeView = new SfTreeView(View.Bounds);
    viewModel = new FileManagerViewModel();
    treeView.ChildPropertyName = "SubFiles";
    treeView.ItemsSource = viewModel.Folders;
    treeView.Adapter = new NodeImageAdapter();
    treeView.Loaded += TreeView_Loaded;

    Add(treeView);
}

private void TreeView_Loaded(object sender, TreeViewLoadedEventArgs e)
{
    var count= viewModel.ImageNodeInfo.Count;
    var data = viewModel.ImageNodeInfo[count-1];
    treeView.BringIntoView(data);
}

{% endhighlight %}
{% endtabs %}

## Scrollbar Visibility

The TreeView provides an option to enable or disable the `Scrollbar` visibility by using the [IsScrollBarVisible](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeView.iOS~Syncfusion.iOS.TreeView.SfTreeView~IsScrollBarVisible.html) property. By default, the value will be true.

N> Due to some restrictions in native ScrollView, you cannot change the `IsScrollBarVisible` value at runtime. It can be defined only when initializing the TreeView.

{% tabs %}
{% highlight c# %}

treeView.IsScrollBarVisible = false;

{% endhighlight %}
{% endtabs %}