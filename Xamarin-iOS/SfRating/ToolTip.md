---

layout: post
title: ToolTip in Syncfusion® Rating control for Xamarin.iOS
description: Learn how to configure and customize ToolTip in Syncfusion® Xamarin.iOS Rating control including placement options and precision settings.
platform: xamarin.ios
control: Rating
documentation: ug

---

# ToolTip

ToolTip provides additional information about objects that are unfamiliar to users and are not directly displayed in the UI. In the Xamarin.iOS SfRating control, the tooltip displays the current `Value` data. It appears when a rating item is selected and disappears when the rating item is unselected.

## Set Tooltip Placement

The Rating control provides ToolTip support with rating value using the `TooltipPlacement` property.

> **Note:** By default, this property value is set to `None`.

### TopLeft 

The ToolTip will be displayed at the top-left of the SfRating control.

{% tabs %}

{% highlight c# %}

rating.TooltipPlacement = SFRatingTooltipPlacement.TopLeft;

{% endhighlight %}

{% endtabs %}

![Tooltip at Top](images/topLeft.jpg) 

### BottomRight

The ToolTip will be displayed at the bottom-right of the SfRating control.

{% highlight c# %}

	   rating.TooltipPlacement = SFRatingTooltipPlacement.BottomRight;

{% endhighlight %}

![Tooltip at Bottom](images/rightBottom.jpg)

### None

It is used to invisible the tool tip in the SfRating control.

{% tabs %}

{% highlight c# %}

rating.TooltipPlacement = SFRatingTooltipPlacement.None;

{% endhighlight %}

{% endtabs %}

![No tooltip](images/null.jpg)

## Set ToolTip Precision

The `ToolTipPrecision` property sets the number precisions to be displayed after decimal point in ToolTip. 

N> The default value of ToolTip precision is 1. 

{% tabs %}

{% highlight c# %}

rating.TooltipPrecision = 6;

{% endhighlight %}

{% endtabs %}

![Tooltip precision](images/toolTipPrecision.jpg)
