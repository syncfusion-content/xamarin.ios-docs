---
layout: post
title: Handling OverFlow Tabs
description: Handling of Overflow tabs in Syncfusion TabView control for Xamarin.iOS platform
platform: Xamarin.iOS
control: TabView
documentation: ug
---

# Handling overflow tabs

When you have large number of tabs, the scroller will be enabled to view the overflow of headers, by default. It can be selected from a pop-up by setting the `OverflowMode` property of `SfTabView` to `DropDown`.

{% tabs %}

{% highlight C# %}

tabView.OverflowMode = OverflowMode.DropDown;
			
{% endhighlight %}

{% endtabs %}

By selecting drop-down option for tab view control, the `“Overflow button”` (or `“More button”`) will be added to the header. When you click the `“Overflow button”`, it will display a pop-up to navigate the other indices.

N> Pop-up will display the text value only; it will show the title value of the respective tab item.

## How to customize the more button?

The appearance of the text can be customized through the APIs that are available in `OverflowButtonSettings` of `SfTabView`. It has APIs to customize both text and font icons available in this button.

{% tabs %}

{% highlight C# %}

var overflowButtonSettings = new OverflowButtonSettings();
		overflowButtonSettings.BackgroundColor = Color.Red;
		overflowButtonSettings.DisplayMode = OverflowButtonDisplayMode.Text;
		overflowButtonSettings.Title = "...";
		overflowButtonSettings.TitleFontColor = Color.Yellow;
		tabView.OverflowButtonSettings = overflowButtonSettings;
			
{% endhighlight %}

{% endtabs %}
