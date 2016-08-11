---
layout: post
title: Various features in Syncfusion Rotator control for Xamarin.iOS
description: Learn how to set the autoplay option, loop the items, enable Text Area  and choose the navigation direction in Rotator control for Xamarin.Android 
platform: Xamarin.iOS
control: Rotator
documentation: ug
---

# Adding Looping and Delays

Looping and delay can be enabled in SfRotator control and also we can customize the Text and Navigation direction.

## Toggle AutoPlay

The `EnableAutoPlay` property specifies whether the items should navigate automatically based on `NavigationDelay` property, when the property value is set to true.

N> By default, the property value is set to false.

{% tabs %}

{% highlight C# %}

	rotator.EnableAutoPlay = True;

{% endhighlight %}

{% endtabs %}

## Set Navigation Delay

The `NavigationDelay` property specifies the duration to delay the switch to next navigation item, when `EnableAutoPlay` property is enabled.

N> The property value should be in milliseconds.

{% tabs %}

{% highlight C# %}

	rotator.NavigationDelay = 2000;

{% endhighlight %}

{% endtabs %}

## Looping Items

The `EnableLooping` property specifies whether the items should navigate to first item once it reaches the last item and vice-versa.

{% tabs %}

{% highlight C# %}

	rotator.EnableLooping = True;

{% endhighlight %}

{% endtabs %}