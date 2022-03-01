---
layout: post
title: Selection Indicator strip
description: Selection Indicator in Syncfusion TabView control for Xamarin.iOS platform
platform: Xamarin.iOS
control: TabView
documentation: ug
---

# Selection Indicator Strip

The selection indicator strip can be used to indicate the selected index of the tab view control. This can be customized with the built-in APIs that are available in the `SelectionIndicatorSettings` of `SfTabView`.

![](images/Selection-Indicator/xamarin_ios_tabstyle02.png)


The selection indicator can be positioned below the title or above the title, or else it can be filled to the entire selected header space.

{% tabs %}

{% highlight C# %}

		var selectionIndicatorSettings = new SelectionIndicatorSettings();
		selectionIndicatorSettings.Color = Color.Yellow;
		selectionIndicatorSettings.Position = SelectionIndicatorPosition.Top;
		selectionIndicatorSettings.StrokeThickness = 10;

		tabView.SelectionIndicatorSettings = selectionIndicatorSettings;

			
{% endhighlight %}

{% endtabs %}

N> Stroke thickness will not applicable when the selection indicator’s position is set to "Fill".

