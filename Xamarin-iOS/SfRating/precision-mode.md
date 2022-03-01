---
layout: post
title: Precision Mode in Syncfusion Rating control for Xamarin.iOS
description: Learn how to change the Precision Mode of rating control
platform: Xamarin.iOS
control: Rating
documentation: ug
---

# Precision Mode

The precision mode defines the accuracy level of the SfRating control. It has Standard, Half, and Exact options.

## Standard

The rating item will be filled completely based on the rating value.

{% tabs %}

{% highlight c# %}

	   rating.Precision = SFRatingPrecision.Standard;

{% endhighlight %}

{% endtabs %}

![SfRating standard precision mode](images/standard.jpg)

## Half

The rating item will be filled partially based on the rating value.

{% tabs %}

{% highlight c# %}

	   rating.Precision = SFRatingPrecision.Half;

{% endhighlight %}

{% endtabs %}

![SfRating half precision mode](images/half.jpg) 

## Exact

The rating item will be filled exactly based on the rating value.

{% tabs %}

{% highlight c# %}

	   rating.Precision = SFRatingPrecision.Exact;

{% endhighlight %}

{% endtabs %}

![SfRating exact precision mode](images/exact.jpg) 