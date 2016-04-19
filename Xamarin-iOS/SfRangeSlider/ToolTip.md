---
layout: post
title: ToolTip support for Syncfusion RangeSlider control for Xamarin.iOS
description: Learn how to set tooltip for RangeSlider in Xamarin.iOS
platform: Xamarin.iOS
control: RangeSlider
documentation: ug
---

# ToolTip Support

The tooltip shows the current value based on thumb position.

## ToolTipPrecision

The `ToolTipPrecision` property is used to define the precision of the value displayed in the tooltip.

{% highlight c# %}

	sfRangeSlider.ToolTipPrecision = 2;
	
{% endhighlight %}

## ToolTipPlacement

The position of the tooltip in relation to the thumb can be controlled by the `ToolTipPlacement` property. It has the following options.

1. BottomRight
2. TopLeft
3. None

### BottomRight

The Tooltip will be placed either below the Thumb in horizontal orientation or right of the Thumb in vertical orientation.

{% highlight c# %}

	sfRangeSlider.ToolTipPlacement = ToolTipPlacement.BottomRight;
	
{% endhighlight %}

### TopLeft

the Tooltip will be placed either above the Thumb in horizontal orientation or left of the Thumb in vertical orientation.

{% highlight c# %}

	sfRangeSlider.ToolTipPlacement = ToolTipPlacement.TopLeft;
	
{% endhighlight %}

### None

Tooltip will be collapsed.

{% highlight c# %}

	sfRangeSlider.ToolTipPlacement = ToolTipPlacement.None;
	
{% endhighlight %}



