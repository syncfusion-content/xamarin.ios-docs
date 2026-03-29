---
layout: post
title: Selection Changed | SfSegmentedControl | Xamarin.iOS | Syncfusion®
description: Learn how to handle selection changed events in Segmented Control
platform: xamarin.ios
control: SfSegmentedControl
documentation: ug
---

# Selection Changed

The selection changed event occurs when changing from one segment item to another in the Segmented Control. It can be handled in two ways:

## User Interface

When users navigate from one item to another, the selection is changed, so the `SelectedIndex` value is updated to the new index of the item. The Segmented Control provides the `SelectionChanged` event, which occurs when the selection is changed with `SelectionChangedEventArgs`.

`Index` - Gets the current index value of the selected item.

{% highlight c# %}
SfSegmentedControl segmentedControl = new SfSegmentedControl();
segmentedControl.SelectionChanged += (object sender, SelectionChangedEventArgs e) =>
{
segmentedControl.BorderColor = UIColor.Red;
};
{% endhighlight %}

## Selected index programmatically

Users can set the default value programmatically for the selection to be placed. The selection is updated based on the index value given for `SelectedIndex`.

{% highlight c# %}
SfSegmentedControl segmentedControl = new SfSegmentedControl();
segmentedControl.SelectedIndex = 2;
{% endhighlight %}

![SegmentedControl SelectedIndex in Xamarin.iOS](images/Selection-changed/SegmentedControl_SelectionChange.png)


