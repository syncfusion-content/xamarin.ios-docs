---
layout: post
title: Various features of Syncfusion RangeSlider control for Xamarin.iOS
description: Learn how to set minimum value, maximum value, tick frequency, step frequency, enabling snaps to support and orientation for RangeSlider
platform: Xamarin.iOS
control: RangeSlider
documentation: ug
---

# Orientation of SfRangeSlider

SfRangeSlider provides option to display the values and the slider either horizontally or vertically.

N> The default option is Horizontal.

## Horizontal

In this orientation, the values and the slider are set horizontally. 

{% tabs %}

{% highlight c# %}

rangeSlider.Orientation = SFOrientation.SFOrientationHorizontal;

{% endhighlight %}

{% endtabs %}

![The RangeSlider Horizontal](images/RangeSlider-Horizontal.png)

## Vertical

In this Orientation, the values and the slider are set vertically. 

{% tabs %}

{% highlight c# %}

rangeSlider.Orientation = SFOrientation.SFOrientationVertical;

{% endhighlight %}

{% endtabs %}

![The RangeSlider Vertical](images/RangeSlider-Vertical.png)


