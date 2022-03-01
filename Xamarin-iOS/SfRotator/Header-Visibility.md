---
layout: post
title: Various features in Syncfusion Rotator control for Xamarin.iOS
description: Learn how to set the autoplay option, loop the items, enable Text Area  and choose the navigation direction in Rotator control for Xamarin.Android 
platform: Xamarin.iOS
control: Rotator
documentation: ug
---

# Header Visibility

The `IsTextVisible` property can be used to enable the text area visibility in bottom area of SfRotator for providing additional information of items. IsTextVisible property is used to change the visibility of the Text panel that is displayed when SfRotatorItem collection is set and will have no effect when setting Item template.

N> By default, the property value is false.

{% tabs %}

{% highlight C# %}

	rotator.IsTextVisible = True;

{% endhighlight %}

{% endtabs %}

