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

## Set ToolTip Precision

The `ToolTipPrecision` property is used to define the precision of the value displayed in the ToolTip.

{% tabs %}

{% highlight c# %}

	rangeSlider.ToolTipPrecision = 2;
	
{% endhighlight %}

{% endtabs %}

## Set ToolTip Placement

The position of the ToolTip in relation to the thumb can be controlled by the `ToolTipPlacement` property. It has the following options.

1. BottomRight
2. TopLeft
3. None

### BottomRight

The ToolTip will be placed either below the Thumb in horizontal orientation or right of the Thumb in vertical orientation.

{% tabs %}

{% highlight c# %}

rangeSlider.ToolTipPlacement = SFToolTipPlacement.SFToolTipPlacementBottomRight;
	
{% endhighlight %}

{% endtabs %}

### TopLeft

the ToolTip will be placed either above the Thumb in horizontal orientation or left of the Thumb in vertical orientation.

{% tabs %}

{% highlight c# %}

rangeSlider.ToolTipPlacement = SFToolTipPlacement.SFToolTipPlacementTopLeft;
	
{% endhighlight %}

{% endtabs %}

### None

ToolTip will be collapsed.

{% tabs %}

{% highlight c# %}

rangeSlider.ToolTipPlacement = SFToolTipPlacement.SFToolTipPlacementNone;
	
{% endhighlight %}

{% endtabs %}



