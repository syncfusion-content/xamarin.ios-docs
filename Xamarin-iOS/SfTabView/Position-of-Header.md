---
layout: post
title: Positioning of Header
description: Positioning of header in Syncfusion® TabView control for Xamarin.iOS platform
platform: xamarin.ios
control: SfTabView
documentation: ug
---

## Positioning of Header

Tab headers can be positioned either above the content or below the content. This can be done by setting the `TabHeaderPosition` property of `SfTabView`.

{% tabs %}

{% highlight C# %}

tabView.TabHeaderPosition = TabHeaderPosition.Bottom;
			
{% endhighlight %}

{% endtabs %}

When the header is not needed, set the `DisplayMode` property of `SfTabView` to `NoHeader`.
