---
layout: post
title: Auto Scrolling in Syncfusion® Segmented Control for Xamarin.iOS
description: Learn how to enable auto scrolling for the selected index in the Segmented Control
platform: xamarin.ios
control: SfSegmentedControl
documentation: ug
---

# Auto Scrolling the Selected Segment Item

Auto scrolling for selected item changes can be enabled by setting the `AutoScrollSelectedItem` property to `true`. You can set the scroll position of the segment item using the `ScrollToPosition` property. The default value for `AutoScrollSelectedItem` is `false`, and the default value for `ScrollToPosition` is `MakeVisible`. The following options are available for `ScrollToPosition`:
	
* `MakeVisible` - Scrolls to the selected segment item to make it visible in the control. If the item is already visible, scrolling will not occur.
* `Start` - Scrolls to the selected segment item at the start of the control.
* `Center` - Scrolls to the selected segment item at the center of the control.
* `End` - Scrolls to the selected segment item at the end of the control.

{% tabs %}

{% highlight c# %}

segmentedControl.SelectedIndex = 5;

segmentedControl.AutoScrollSelectedItem = true;

segmentedControl.ScrollToPosition = Syncfusion.iOS.Buttons.ScrollToPosition.Center;

{% endhighlight %}

{% endtabs %}