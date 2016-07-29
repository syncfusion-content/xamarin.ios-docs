---
layout: post
title: Position of Drawer in Syncfusion NavigationDrawer control for Xamarin.iOS
description: Learn how to set position of the DrawerView panel.
platform: Xamarin.iOS
control: NavigationDrawer
documentation: ug
---
# Position

The `Position` property specifies the sliding position of the DrawerView panel. The `Position` property has the following four options:

* Left

* Right

* Top

* Bottom

N> The default option is Left.

## Left

Sets the NavigationDrawer sliding position to the left.


{% highlight c# %}

	navigationDrawer.Position = SFNavigationDrawerPosition.SFNavigationDrawerPositionLeft;

{% endhighlight %}

![](images/left.png)

## Right

Sets the NavigationDrawer sliding position to the right.

{% highlight c# %}

	navigationDrawer.Position = SFNavigationDrawerPosition.SFNavigationDrawerPositionRight;

{% endhighlight %}

![](images/Right.png)
	
## Top

Sets the NavigationDrawer sliding position to the top.

{% highlight c# %}

	navigationDrawer.Position = SFNavigationDrawerPosition.SFNavigationDrawerPositionTop;

{% endhighlight %}

![](images/Top.png)

## Bottom

Sets the NavigationDrawer sliding position to the bottom.

{% highlight c# %}

	navigationDrawer.Position = SFNavigationDrawerPosition.SFNavigationDrawerPositionBottom;

{% endhighlight %}

![](images/bottom.png)






