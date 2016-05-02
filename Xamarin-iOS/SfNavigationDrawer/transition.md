---
layout: post
title: Transition of drawer in Syncfusion NavigationDrawer control for Xamarin.iOS
description: Learn how to set Transition of the DrawerView panel.
platform: Xamarin.iOS
control: NavigationDrawer
documentation: ug
---
# Transition

The `Transition` property specifies the sliding animations for the DrawerView panel. The `Transition` property has the following three options:

* SlideOnTop
* Push
* Reveal

N> The default transition is SlideOnTop.

## SlideOnTop

Slides the DrawerContent on top of the main content.

{% highlight c# %} 

	slideDrawer.Transition=Transition.SlideOnTop;

{% endhighlight %}

![](images/Slide-on-top.png)

## Push

This transition slides the Drawer and main content simultaneously.

{% highlight c# %} 

	slideDrawer.Transition=Transition.Push;

{% endhighlight %}

![](images/Push.png)

## Reveal

The Drawer content is in fixed position and the main content will slide to reveal the drawer content.

{% highlight c# %} 

	slideDrawer.Transition=Transition.Reveal;

{% endhighlight %}

![](images/reveal.png)
