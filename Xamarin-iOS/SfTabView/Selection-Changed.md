---
layout: post
title: Selection Changed
description: Selection changed event in TabView control for Xamarin.iOS platform
platform: xamarin.ios
control: SfTabView
documentation: ug
---

# Selection Changed

The `SelectionChanged` event is triggered when the selection changes due to swiping or dynamically setting the `SelectedIndex` property of `SfTabView`.

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

## Enable Swiping

When you need to restrict the selection changed event through user interaction, set the `EnableSwiping` property of `SfTabView` to `false`.

