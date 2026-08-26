---
layout: post
title: Ticks in Syncfusion® RangeSlider control for Xamarin.iOS
description: This section provides details about how to configure and customize ticks in RangeSlider control for Xamarin.iOS
platform: xamarin.ios
control: RangeSlider
documentation: ug
---

# Customizing SfRangeSlider Ticks

Tick marks can be placed along the track in a uniform manner, or their position can be customized.

## TickPlacement

The `TickPlacement` property determines where to draw tick marks in relation to the track. Available options for this property are:

* BottomRight

* Inline

* None

* Outside

* TopLeft

> **Note:** The default option is `Inline`.

## BottomRight

Tick marks can be placed either below the track in horizontal orientation or to the right of the track in vertical orientation.

{% tabs %}

{% highlight c# %}

	rangeSlider.TickPlacement = SFTickPlacement.SFTickPlacementBottomRight;

{% endhighlight %}

{% endtabs %}

![The BottomRight](images/BottomRight.png)

## TopLeft

Tick marks are placed either above the track in horizontal orientation or to the left of the track in vertical orientation.

{% tabs %}

{% highlight c# %}

	rangeSlider.TickPlacement = SFTickPlacement.SFTickPlacementTopLeft;

{% endhighlight %}

{% endtabs %}

![The TopLeft](images/TopLeft.png)

## Inline

Ticks are placed along the track.

{% tabs %}

{% highlight c# %}

	rangeSlider.TickPlacement = SFTickPlacement.SFTickPlacementInline;

{% endhighlight %}

{% endtabs %}

![The Inline](images/Inline.png)

## Outside

Tick marks are placed on both sides of the track in either horizontal or vertical orientation.

{% tabs %}

{% highlight c# %}

	rangeSlider.TickPlacement = SFTickPlacement.SFTickPlacementOutside;

{% endhighlight %}

{% endtabs %}

![The Outside](images/Outside.png)

## Customizing Tick Color

The RangeSlider control provides the `TickColor` property to customize the color of ticks in the tick bar.

{% highlight c# %}

	SfRangeSlider sfRangeSlider = new SfRangeSlider();
	sfRangeSlider.Frame = new CoreGraphics.CGRect(10, 50, 350, 300);
	sfRangeSlider.TickColor = UIColor.Red;
	sfRangeSlider.TickLength = 10;
	this.View.AddSubview(sfRangeSlider);
 
{% endhighlight %}

![The TickColor](images/TickColor.png)
