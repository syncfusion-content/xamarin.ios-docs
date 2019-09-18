---
layout: post
title: auto scrolling the Syncfusion segmented control for Xamarin.iOS | SfSegmentedControl | Xamarin.iOS | Syncfusion
description: Learn how auto scroll in segmented control to the selected index
platform: Xamarin.iOS
control: SfSegmentedControl
documentation: ug
---

# Autoscrolling the selected segment item

Segmented control allows auto scrolling the selected segment items when the selected item is not in the view. Auto scrolling can be enabled by setting true for the [`AutoScrollSelectedItem`]() property and dynamically change the selected index, the selected segment will auto scroll based on the [`ScrollToPosition`]() value set. The default value for [`AutoScrollSelectedItem`]() is false and [`ScrollToPosition`]() is [`MakeVisible`]().

The [`ScrollToPosition`]() enum contains the following values:
	
* [`MakeVisible`]() - Scrolls a specific segment item to make visible in the view. If the item is already in view, scrolling will not occur.
* [`Start`]() - Scrolls a specific segment item to be positioned at the start of the view.
* [`Center`]() - Scrolls a specific segment item to be positioned at the center of the view.
* [`End`]() - Scrolls a specific segment item to be positioned at the end of the view.

{% tabs %}

{% highlight c# %}

segmentedControl.SelectedIndex = 5;

segmentedControl.AutoScrollSelectedItem = true;

segmentedControl.ScrollToPosition = Syncfusion.iOS.Buttons.ScrollToPosition.Center;

{% endhighlight %}

{% endtabs %}