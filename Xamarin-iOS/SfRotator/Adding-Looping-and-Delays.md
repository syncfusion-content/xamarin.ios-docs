---
layout: post
title: Various Features in Syncfusion® Rotator Control for Xamarin.iOS
description: Learn how to set the autoplay option, loop the items, enable text area and choose the navigation direction in Rotator control for Xamarin.iOS
platform: xamarin.ios
control: SfRotator
documentation: ug
---

# Adding Looping and Delays

Looping and delay can be enabled in the SfRotator control. You can also customize the text and navigation direction.

## Toggle AutoPlay

The `EnableAutoPlay` property specifies whether the items should navigate automatically based on the `NavigationDelay` property when the property value is set to true.

> **Note:** By default, the property value is set to false.

{% tabs %}

{% highlight C# %}

	rotator.EnableAutoPlay = True;

{% endhighlight %}

{% endtabs %}

## Set Navigation Delay

The `NavigationDelay` property specifies the duration to delay the switch to the next navigation item when the `EnableAutoPlay` property is enabled.

> **Note:** The property value should be in milliseconds.

{% tabs %}

{% highlight C# %}

	rotator.NavigationDelay = 2000;

{% endhighlight %}

{% endtabs %}

## Looping Items

The `EnableLooping` property specifies whether the items should navigate to the first item once it reaches the last item and vice versa.

{% tabs %}

{% highlight C# %}

	rotator.EnableLooping = True;

{% endhighlight %}

{% endtabs %}