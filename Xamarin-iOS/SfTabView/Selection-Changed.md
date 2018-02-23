---
layout: post
title: Selection Changed
description: Selection changed event in TabView control for Xamarin.iOS platform
platform: Xamarin.iOS
control: TabView
documentation: ug
---

# Selection Changed

The `SelectionChanged` event notifies when the selection is changed due to swiping or dynamically setting the `SelectedIndex` property of `SfTabView`.

{% tabs %}

{% highlight C# %}

tabView.SelectionChanged += SfTabView_SelectionChanged;

		// Raised when selected index changed
	private void SfTabView_SelectionChanged(object sender, SelectionChangedEventArgs e)
	{
		var selectedIndex = e.Index;
	}

{% endhighlight %}

{% endtabs %}

## Enable swiping

When the selection changed event needs to be restricted through user interaction, set the `EnableSwiping` property of `SfTabView` to `false`.
