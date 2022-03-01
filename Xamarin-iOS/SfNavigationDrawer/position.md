---
layout: post
title: Position of Drawer in Syncfusion NavigationDrawer control for Xamarin.iOS
description: Learn how to set position of the DrawerView panel.
platform: Xamarin.iOS
control: NavigationDrawer
documentation: ug
---
# Configuring The Drawer In Different Sides

The `Position` property specifies the sliding position of the DrawerView panel. The `Position` property has the following four options.

* Left

* Right

* Top

* Bottom

N> The default option is Left.

## Left

Sets the NavigationDrawer sliding position to the left.

{% tabs %}

{% highlight c# %}

navigation.Position = SFNavigationDrawerPosition.SFNavigationDrawerPositionLeft;

{% endhighlight %}

{% endtabs %}

![](images/left.png)

## Right

Sets the NavigationDrawer sliding position to the right.

{% tabs %}

{% highlight c# %}

navigation.Position = SFNavigationDrawerPosition.SFNavigationDrawerPositionRight;

{% endhighlight %}

{% endtabs %}

![](images/Right.png)
	
## Top

Sets the NavigationDrawer sliding position to the top.

{% tabs %}

{% highlight c# %}

navigation.Position = SFNavigationDrawerPosition.SFNavigationDrawerPositionTop;

{% endhighlight %}

{% endtabs %}

![](images/Top.png)

## Bottom

Sets the NavigationDrawer sliding position to the bottom.

{% tabs %}

{% highlight c# %}

navigation.Position = SFNavigationDrawerPosition.SFNavigationDrawerPositionBottom;

{% endhighlight %}

{% endtabs %}

![](images/bottom.png)






