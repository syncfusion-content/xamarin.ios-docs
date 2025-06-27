---
layout: post
title: Restrict User Selection in Syncfusion® Rating control for Xamarin.iOS
description: Learn how to restrict user selection in Syncfusion® Xamarin.iOS Rating control using the ReadOnly property to prevent rating modifications.
platform: xamarin.ios
control: Rating
documentation: ug
---

# Restrict User Selection

The SfRating control provides support for controlling whether users can modify the rating value. This functionality is achieved through the `ReadOnly` property. When this property is set to `true`, the rating value becomes unchangeable, preventing user interaction. By default, this property is set to `false`, allowing users to modify the rating.

{% tabs %}

{% highlight c# %}

	rating.ReadOnly = true;

{% endhighlight %}

{% endtabs %}

![Restrict user selection](images/readOnly.jpg)
