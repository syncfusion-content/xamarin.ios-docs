---
layout: post
title: Selection Indicator Strip
description: Selection Indicator in Syncfusion® TabView control for Xamarin.iOS platform
platform: xamarin.ios
control: SfTabView
documentation: ug
---

# Selection Indicator Strip

The selection indicator strip can be used to indicate the selected index of the TabView control. This can be customized with the built-in APIs that are available in the `SelectionIndicatorSettings` of `SfTabView`.

![Selection Indicator Strip](images/Selection-Indicator/xamarin_ios_tabstyle02.png)

The selection indicator can be positioned below the title, above the title, or it can be filled to the entire selected header space.

{% tabs %}

{% highlight C# %}

		var selectionIndicatorSettings = new SelectionIndicatorSettings();
		selectionIndicatorSettings.Color = Color.Yellow;
		selectionIndicatorSettings.Position = SelectionIndicatorPosition.Top;
		selectionIndicatorSettings.StrokeThickness = 10;

		tabView.SelectionIndicatorSettings = selectionIndicatorSettings;

			
{% endhighlight %}

{% endtabs %}

> **Note:** Stroke thickness is not applicable when the selection indicator's position is set to "Fill".
