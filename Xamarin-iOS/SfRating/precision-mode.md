---
layout: post
title: Precision Mode in Syncfusion® Rating Control for Xamarin.iOS
description: Learn how to configure precision modes (Standard, Half, Exact) in Syncfusion® Rating control for Xamarin.iOS to control rating accuracy levels.
platform: xamarin.ios
control: SfRating
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

![SfRating Standard Precision Mode](images/standard.jpg)

## Half

The rating item will be filled partially based on the rating value.

{% tabs %}

{% highlight c# %}

	   rating.Precision = SFRatingPrecision.Half;

{% endhighlight %}

{% endtabs %}

![SfRating Half Precision Mode](images/half.jpg)

## Exact

The rating item will be filled exactly based on the rating value.

{% tabs %}

{% highlight c# %}

	   rating.Precision = SFRatingPrecision.Exact;

{% endhighlight %}

{% endtabs %}

![SfRating Exact Precision Mode](images/exact.jpg)
