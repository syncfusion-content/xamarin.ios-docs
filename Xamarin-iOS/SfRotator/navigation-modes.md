---
layout: post
title: NavigationMode of Syncfusion Rotator control for Xamarin.iOS
description: Learn how to view the different navigation modes of the Rotator control in Xamarin.iOS
platform: Xamarin.iOS 
control: Rotator
documentation: ug
---

# Navigation Modes

The `NavigationStripMode` property specifies the appearance of navigation bar items. The image data can be selected either by Thumbnail or by Dots navigation modes.

* `Thumbnail` - The slider items will be loaded in thumbnail view additionally. When a thumbnail item is clicked, the slider will switch to the corresponding image data.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripMode = SFRotatorNavigationStripMode.Thumbnail;	

{% endhighlight %}

{% endtabs %}

![](images/thumbnail.png)

* `Dots` - The slider items will be loaded in dots view additionally. When a dots item is clicked, the slider will switch to the corresponding image data.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripMode = SFRotatorNavigationStripMode.Dots;	

{% endhighlight %}

{% endtabs %}

![](images/dots.png)

## Items / Dot Strip Positions

The `NavigationStripPosition` position specifies the placement position of the navigation bar items such as thumbnail or dots relative to the slider area. 

There are four available positions,

* `Bottom` - Sets the position of the navigation bar items to bottom.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripPosition = SFRotatorNavigationStripPosition.Bottom;

{% endhighlight %}

{% endtabs %}

* `Left` - Sets the position of the navigation bar items to left.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripPosition = SFRotatorNavigationStripPosition.Left;

{% endhighlight %}

{% endtabs %}

* `Top` - Sets the position of the navigation bar items to top.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripPosition = SFRotatorNavigationStripPosition.Top;

{% endhighlight %}

{% endtabs %}

* `Right` - Sets the position of the navigation bar items to right.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripPosition = SFRotatorNavigationStripPosition.Right;

{% endhighlight %}

{% endtabs %}

![](images/tabstrip.png)

