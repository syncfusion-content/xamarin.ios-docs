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

	Position sliderposition = Position.Left;	
	slideDrawer.Position=sliderposition;

{% endhighlight %}

![](images/Left.png)

## Right

Sets the NavigationDrawer sliding position to the right.

{% highlight c# %}

	Position sliderposition = Position.Right;	
	slideDrawer.Position=sliderposition;

{% endhighlight %}

![](images/Right.png)
	
## Top

Sets the NavigationDrawer sliding position to the top.

{% highlight c# %}

	Position sliderposition = Position.Top;	
   	slideDrawer.Position=sliderposition;

{% endhighlight %}

![](images/Top.png)

## Bottom

Sets the NavigationDrawer sliding position to the bottom.

{% highlight c# %}

	Position sliderposition = Position.Bottom;	
	slideDrawer.Position=sliderposition;

{% endhighlight %}

![](images/bottom.png)






