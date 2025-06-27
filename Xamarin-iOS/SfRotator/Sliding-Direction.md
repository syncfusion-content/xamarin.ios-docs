---
layout: post
title: Sliding Direction in Syncfusion® Rotator Control for Xamarin.iOS
description: Learn how to configure sliding direction in Syncfusion® Xamarin.iOS Rotator control with horizontal, vertical, and directional navigation options.
platform: xamarin.ios
control: SfRotator
documentation: ug
---

# Sliding Direction

The `NavigationDirection` property specifies the direction in which items should be navigated in the Rotator control.

## Horizontal

Items can be navigated in the horizontal direction.

{% tabs %}

{% highlight C# %}

	rotator.NavigationDirection = SFRotatorNavigationDirection.Horizontal;

{% endhighlight %}

{% endtabs %}

## Vertical

Items can be navigated in the vertical direction.

{% tabs %}

{% highlight C# %}

	rotator.NavigationDirection = SFRotatorNavigationDirection.Vertical;

{% endhighlight %}

{% endtabs %}

## Left to Right

Items can be navigated from left to right only.

{% tabs %}

{% highlight C# %}

	rotator.NavigationDirection = SFRotatorNavigationDirection.LeftToRight;

{% endhighlight %}

{% endtabs %}

## Right to Left

Items can be navigated from right to left only.

{% tabs %}

{% highlight C# %}

	rotator.NavigationDirection = SFRotatorNavigationDirection.RightToLeft;

{% endhighlight %}

{% endtabs %}

## Top to Bottom

Items can be navigated from top to bottom only.

{% tabs %}

{% highlight C# %}

	rotator.NavigationDirection = SFRotatorNavigationDirection.TopToBottom;

{% endhighlight %}

{% endtabs %}

## Bottom to Top

Items can be navigated from bottom to top only.

{% tabs %}

{% highlight C# %}

	rotator.NavigationDirection = SFRotatorNavigationDirection.BottomToTop;

{% endhighlight %}

{% endtabs %}