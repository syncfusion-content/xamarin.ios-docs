---
layout: post
title: Positioning of header 
description: Positioning of header in Syncfusion TabView control for Xamarin.iOS platform
platform: Xamarin.iOS
control: TabView
documentation: ug
---

## Positioning of header

Tab headers can be positioned either above the content or below the content; it can be done by setting the `TabHeaderPosition` property of `SfTabView`.

{% tabs %}

{% highlight C# %}

tabView.TabHeaderPosition = TabHeaderPosition.Bottom;
			
{% endhighlight %}

{% endtabs %}

When the header is not needed, set the `DisplayMode` property of `SfTabView` to `NoHeader`.
