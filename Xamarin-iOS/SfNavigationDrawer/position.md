---
layout: post
title: Drawer position configuration for Syncfusion® NavigationDrawer control in Xamarin.iOS
description: Learn how to configure the position of the DrawerView panel in NavigationDrawer control.
platform: xamarin.ios
control: NavigationDrawer
documentation: ug
---

# Drawer Position Configuration

The `Position` property specifies the sliding position of the DrawerView panel. The drawer can be positioned to slide from any of the four screen edges. The `Position` property supports the following four options:
* Left

* Right

* Top

* Bottom

N> The default option is Left.

## Left Position

Configures the NavigationDrawer to slide from the left edge of the screen.
{% tabs %}

{% highlight c# %}

navigation.Position = SFNavigationDrawerPosition.SFNavigationDrawerPositionLeft;

{% endhighlight %}

{% endtabs %}

![Left position drawer example](images/left.png)

## Right Position

Configures the NavigationDrawer to slide from the right edge of the screen.
{% tabs %}

{% highlight c# %}

navigation.Position = SFNavigationDrawerPosition.SFNavigationDrawerPositionRight;

{% endhighlight %}

{% endtabs %}

![Right position drawer example](images/Right.png)

## Top Position

Configures the NavigationDrawer to slide from the top edge of the screen.
{% tabs %}

{% highlight c# %}

navigation.Position = SFNavigationDrawerPosition.SFNavigationDrawerPositionTop;

{% endhighlight %}

{% endtabs %}

![Top position drawer example](images/Top.png)

## Bottom Position

Configures the NavigationDrawer to slide from the bottom edge of the screen.
{% tabs %}

{% highlight c# %}

navigation.Position = SFNavigationDrawerPosition.SFNavigationDrawerPositionBottom;

{% endhighlight %}

{% endtabs %}

![Bottom position drawer example](images/bottom.png)

