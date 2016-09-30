---
layout: post
title: Transition of drawer in Syncfusion NavigationDrawer control for Xamarin.iOS
description: Learn how to set Transition of the DrawerView panel.
platform: Xamarin.iOS
control: NavigationDrawer
documentation: ug
---
# Drawer Opening Animation

The `Transition` property specifies the sliding animations for the DrawerView panel. The `Transition` property has the following three options:

* SlideOnTop
* Push
* Reveal

N> The default transition is SlideOnTop.

## SlideOnTop

Slides the DrawerContent on top of the main content.

{% tabs %}

{% highlight c# %} 

	navigationDrawer.Transition = SFNavigationDrawerTransition.SFNavigationDrawerTransitionSlideOnTop;

{% endhighlight %}

{% endtabs %}

![](images/Slide-on-top.png)

## Push

This transition slides the Drawer and main content simultaneously.

{% tabs %}

{% highlight c# %} 

	navigationDrawer.Transition = SFNavigationDrawerTransition.SFNavigationDrawerTransitionSlideOnPush;

{% endhighlight %}

{% endtabs %}

![](images/push.png)

## Reveal

The Drawer content is in fixed position and the main content will slide to reveal the drawer content.

{% tabs %}

{% highlight c# %} 

	navigationDrawer.Transition = SFNavigationDrawerTransition.SFNavigationDrawerTransitionSlideOnReveal;

{% endhighlight %}

{% endtabs %}

![](images/Reveal.png)
