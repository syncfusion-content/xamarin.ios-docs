---
layout: post
title: Auto scrolling the Syncfusion segmented control for Xamarin.iOS
description: Learn how to auto scroll the selected index in the segmented control
platform: Xamarin.iOS
control: SfSegmentedControl
documentation: ug
---

# Autoscrolling the selected segment item

Auto scrolling for selected item change can be enabled by setting value to the [`AutoScrollSelectedItem`]() property as true and also able to set the scroll position of segment item by using the [`ScrollToPosition`]() property. The default value for [`AutoScrollSelectedItem`]() is false and [`ScrollToPosition`]() is [`MakeVisible`](). The following options are available in [`ScrollToPosition`]() :
	
* [`MakeVisible`]() -  Scroll to selected segment item to make it visible in the control. If the item is already visible, scrolling will not occur.
* [`Start`]() -  Scroll to selected segment item at the start of the control.
* [`Center`]() - Scroll to selected segment item at the center of the control.
* [`End`]() - Scroll to selected segment item at the end of the control.

{% tabs %}

{% highlight c# %}

segmentedControl.SelectedIndex = 5;

segmentedControl.AutoScrollSelectedItem = true;

segmentedControl.ScrollToPosition = Syncfusion.iOS.Buttons.ScrollToPosition.Center;

{% endhighlight %}

{% endtabs %}