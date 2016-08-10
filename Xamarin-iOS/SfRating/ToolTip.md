---

layout: post
title: ToolTip in Syncfusion Rating control for Xamarin.iOS
description: Learn how to change the ToolTip of rating control
platform: Xamarin.iOS
control: Rating
documentation: ug

---


# ToolTip

The ToolTip shows the value of the SfRating control.

## Set Tooltip Placement

Rating control provides ToolTip support with rating value using `TooltipPlacement` property. 

N> By default, this property value is set to None.

### TopLeft 

The ToolTip will display on top of the SfRating control. 

{% tabs %}

{% highlight c# %}

rating.TooltipPlacement=SFRatingTooltipPlacement.TopLeft;

{% endhighlight %}

{% endtabs %}

![](images/topLeft.jpg) 

### BottomRight

The tooltip will display on bottom of the SfRating control.

{% highlight c# %}

	   rating.TooltipPlacement=SFRatingTooltipPlacement.BottomRight;

{% endhighlight %}

![](images/rightBottom.jpg)

### None

It is used to invisible the tool tip in the SfRating control.

{% tabs %}

{% highlight c# %}

rating.TooltipPlacement=SFRatingTooltipPlacement.None;

{% endhighlight %}

{% endtabs %}

![](images/null.jpg)

## Set ToolTip Precision

The `ToolTipPrecision` property sets the number precisions to be displayed after decimal point in ToolTip. 

N> The default value of ToolTip precision is 1. 

{% tabs %}

{% highlight c# %}

rating.TooltipPlacement=6;

{% endhighlight %}

{% endtabs %}

![](images/toolTipPrecision.jpg)
