---
layout: post
title: Appearance and Styling in Syncfusion Rating control for Xamarin.iOS
description: Learn how to change the Appearance and Styling of rating control
platform: Xamarin.iOS
control: Rating
documentation: ug
---

# Restrict User Selection

SfRating control provides support for changeable or unchangeable values for Rating control. This is achieved by the `ReadOnly` property. When this property is set to True, the Rating value becomes unchangeable. By default, this property value is set to False.

{% tabs %}

{% highlight c# %}

	rating.ReadOnly = true;

{% endhighlight %}

{% endtabs %}

![Restrict user selection](images/readOnly.jpg)
