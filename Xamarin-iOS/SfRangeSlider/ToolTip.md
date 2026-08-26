---
layout: post
title: ToolTip Support for Syncfusion® RangeSlider control for Xamarin.iOS
description: Learn how to implement and customize tooltips for SfRangeSlider control with various display options and styling configurations
platform: xamarin.ios
control: RangeSlider
documentation: ug
---

# ToolTip Support

The tooltip shows the current value based on the thumb position.

## Set ToolTip Precision

The `ToolTipPrecision` property is used to define the precision of the value displayed in the ToolTip.

{% tabs %}

{% highlight c# %}

	rangeSlider.ToolTipPrecision = 2;
	
{% endhighlight %}

{% endtabs %}

## Set ToolTip Placement

The position of the ToolTip in relation to the thumb can be controlled by the `ToolTipPlacement` property. It has the following options:

1. BottomRight
2. TopLeft
3. None

### BottomRight

The ToolTip will be placed either below the thumb in horizontal orientation or to the right of the thumb in vertical orientation.

{% tabs %}

{% highlight c# %}

rangeSlider.ToolTipPlacement = SFToolTipPlacement.SFToolTipPlacementBottomRight;
	
{% endhighlight %}

{% endtabs %}

### TopLeft

The ToolTip will be placed either above the thumb in horizontal orientation or to the left of the thumb in vertical orientation.

{% tabs %}

{% highlight c# %}

rangeSlider.ToolTipPlacement = SFToolTipPlacement.SFToolTipPlacementTopLeft;
	
{% endhighlight %}

{% endtabs %}

### None

The ToolTip will be hidden.

{% tabs %}

{% highlight c# %}

rangeSlider.ToolTipPlacement = SFToolTipPlacement.SFToolTipPlacementNone;
	
{% endhighlight %}

{% endtabs %}

## ToolTip Color Customization

The RangeSlider control provides properties to customize the ToolTip appearance:
`TooltipTextColor` - Used to change the tooltip text color.
`TooltipBackgroundColor` - Used to change the tooltip background color.

{% tabs %}

{% highlight c# %}

    rangeSlider.ToolTipBackgroundColor = UIColor.Red;
    rangeSlider.TooltipTextColor = UIColor.White;
	
{% endhighlight %}

{% endtabs %}


