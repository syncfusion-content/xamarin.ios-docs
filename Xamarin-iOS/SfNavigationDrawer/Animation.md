---
layout: post
title: Transition animations for Syncfusion® NavigationDrawer control in Xamarin.iOS
description: Learn how to configure transition animations for the DrawerView panel in NavigationDrawer.
platform: xamarin.ios
control: NavigationDrawer
documentation: ug
---
# Drawer Opening Animation

The `Transition` property specifies the sliding animations for the DrawerView panel. The `Transition` property provides the following three animation options:

* SlideOnTop
* Push
* Reveal

N> The default transition is SlideOnTop.

## SlideOnTop

Slides the drawer content on top of the main content, overlaying it during the transition.

{% tabs %}

{% highlight c# %} 

	navigation.Transition = SFNavigationDrawerTransition.SFNavigationDrawerTransitionSlideOnTop;

{% endhighlight %}

{% endtabs %}

![SlideOnTop transition animation example](images/Slide-on-top.png)
## Push

This transition slides both the drawer and main content simultaneously, pushing the main content aside as the drawer opens.

{% tabs %}

{% highlight c# %} 

	navigation.Transition = SFNavigationDrawerTransition.SFNavigationDrawerTransitionPush;

{% endhighlight %}

{% endtabs %}

![Push transition animation example](images/push.png)
## Reveal

The drawer content remains in a fixed position while the main content slides away to reveal the drawer underneath.

{% tabs %}

{% highlight c# %} 

	navigation.Transition = SFNavigationDrawerTransition.SFNavigationDrawerTransitionReveal;

{% endhighlight %}

{% endtabs %}

![Reveal transition animation example](images/Reveal.png)
