---
layout: post
title: Header Visibility in Syncfusion® Rotator Control for Xamarin.iOS
description: Discover how to manage header visibility and text panel display in Syncfusion® Xamarin.iOS Rotator control to show additional item details.
platform: xamarin.ios
control: SfRotator
documentation: ug
---

# Header Visibility

The `IsTextVisible` property can be used to enable the text area visibility in the bottom area of SfRotator for providing additional information about items. The `IsTextVisible` property is used to change the visibility of the text panel that is displayed when the SfRotatorItem collection is set and will have no effect when setting an item template.

> **Note:** By default, the property value is false.

{% tabs %}

{% highlight C# %}

	rotator.IsTextVisible = True;

{% endhighlight %}

{% endtabs %}

