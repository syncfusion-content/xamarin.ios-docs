---
layout: post
title: Navigation Modes of Syncfusion® Rotator Control for Xamarin.iOS
description: Learn how to configure navigation modes (Thumbnail, Dots) and strip positions in Syncfusion® Xamarin.iOS Rotator control for image navigation.
platform: xamarin.ios
control: SfRotator
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

![Thumbnail Navigation Mode](images/thumbnail.png)
* `Dots` - The slider items will be loaded in dots view additionally. When a dots item is clicked, the slider will switch to the corresponding image data.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripMode = SFRotatorNavigationStripMode.Dots;	

{% endhighlight %}

{% endtabs %}

![Dots Navigation Mode](images/dots.png)
## Items/Dot Strip Positions

The `NavigationStripPosition` property specifies the placement position of the navigation bar items such as thumbnail or dots relative to the slider area.

There are four available positions:

* `Bottom` - Sets the position of the navigation bar items to the bottom.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripPosition = SFRotatorNavigationStripPosition.Bottom;

{% endhighlight %}

{% endtabs %}

* `Left` - Sets the position of the navigation bar items to the left.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripPosition = SFRotatorNavigationStripPosition.Left;

{% endhighlight %}

{% endtabs %}

* `Top` - Sets the position of the navigation bar items to the top.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripPosition = SFRotatorNavigationStripPosition.Top;

{% endhighlight %}

{% endtabs %}

* `Right` - Sets the position of the navigation bar items to the right.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripPosition = SFRotatorNavigationStripPosition.Right;

{% endhighlight %}

{% endtabs %}

![Navigation Strip Positions](images/tabstrip.png)
