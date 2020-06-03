---
layout: post
title: Ticks of Syncfusion RangeSlider control for Xamarin.iOS
description: Learn how to set ticks in proper position for RangeSlider control in Xamarin.iOS
platform: Xamarin.iOS
control: RangeSlider
documentation: ug
---

# Customizing ticks

Tick marks can be placed along the track in a uniform manner or it's position can also be customized.

## TickPlacement

The `TickPlacement` property determines where to draw tick marks in relation to the track. Available options for this property are,

* BottomRight

* Inline

* None

* Outside

* TopLeft

N> The default option is Inline.

## BottomRight

Tick marks can be placed either below the track in horizontal orientation or right of the track in vertical orientation.

{% tabs %}

{% highlight c# %}

	rangeSlider.TickPlacement = SFTickPlacement.SFTickPlacementBottomRight;

{% endhighlight %}

{% endtabs %}

![](images/BottomRight.png)

## TopLeft

Tick marks are placed either above the track in horizontal orientation or left of the track in vertical orientation.

{% tabs %}

{% highlight c# %}

	rangeSlider.TickPlacement = SFTickPlacement.SFTickPlacementTopLeft;

{% endhighlight %}

{% endtabs %}

![](images/TopLeft.png)

## Inline

Ticks are placed along the track.

{% tabs %}

{% highlight c# %}

	rangeSlider.TickPlacement = SFTickPlacement.SFTickPlacementInline;

{% endhighlight %}

{% endtabs %}

![](images/Inline.png)

## Outside

Tick marks are placed on both sides of the track either in horizontal or vertical orientation.

{% tabs %}

{% highlight c# %}

	rangeSlider.TickPlacement = SFTickPlacement.SFTickPlacementOutside;

{% endhighlight %}

{% endtabs %}

![](images/Outside.png)


## Customizing tick color

The range slider control provides the `TickColor` property to customize the color of ticks in tick bar.

{% highlight c# %}

	SfRangeSlider sfRangeSlider = new SfRangeSlider();
	sfRangeSlider.Frame = new CoreGraphics.CGRect(10, 50, 350, 300);
	sfRangeSlider.TickColor = UIColor.Red;
	sfRangeSlider.TickLength = 10;
	this.View.AddSubview(sfRangeSlider);
 
{% endhighlight %}

![](images/TickColor.png)
