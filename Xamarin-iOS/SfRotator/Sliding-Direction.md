---
layout: post
title: Various features in Syncfusion Rotator control for Xamarin.iOS
description: Learn how to set the autoplay option, loop the items, enable Text Area  and choose the navigation direction in Rotator control for Xamarin.Android 
platform: Xamarin.iOS
control: Rotator
documentation: ug
---

# Sliding Direction

The `NavigationDirection` property specifies the direction in which items should be navigated in Rotator control.

## Horizontal

Items can be navigated in horizontal direction.

{% tabs %}

{% highlight C# %}

	rotator.NavigationDirection = SFRotatorNavigationDirection.Horizontal;

{% endhighlight %}

{% endtabs %}

## Vertical

Items can be navigated in vertical direction.

{% tabs %}

{% highlight C# %}

	rotator.NavigationDirection = SFRotatorNavigationDirection.Vertical;

{% endhighlight %}

{% endtabs %}

## LeftToRight

Items can be navigated from Left to Right only.

{% tabs %}

{% highlight C# %}

	rotator.NavigationDirection = SFRotatorNavigationDirection.LeftToRight;

{% endhighlight %}

{% endtabs %}

## RightToLeft

Items can be navigated from Right to Left only.

{% tabs %}

{% highlight C# %}

	rotator.NavigationDirection = SFRotatorNavigationDirection.RightToLeft;

{% endhighlight %}

{% endtabs %}

## TopToBottom

Items can be navigated from Top to Bottom only.

{% tabs %}

{% highlight C# %}

	rotator.NavigationDirection = SFRotatorNavigationDirection.TopToBottom;

{% endhighlight %}

{% endtabs %}

## BottomToTop

Items can be navigated from Bottom to Top only.

{% tabs %}

{% highlight C# %}

	rotator.NavigationDirection = SFRotatorNavigationDirection.BottomToTop;

{% endhighlight %}

{% endtabs %}