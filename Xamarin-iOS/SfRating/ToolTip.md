---

layout: post
title: ToolTip in Syncfusion Rating control for Xamarin.iOS
description: Learn how to change the ToolTip of rating control
platform: Xamarin.iOS
control: Rating
documentation: ug

---


# ToolTip

## ToolTipPlacement

Rating control provides tooltip support with rating value using `TooltipPlacement` property. 

N> By default, this property value is set to None.

### TopLeft 

The tooltip will display on top of the SfRating control. 

{% highlight c# %}

	   rating.TooltipPlacement=TooltipPlacement.TopLeft;

{% endhighlight %}

![](images/topLeft.jpg) 

### BottomRight

The tooltip will display on bottom of the SfRating control.

{% highlight c# %}

	   rating.TooltipPlacement=TooltipPlacement.BottomRight;

{% endhighlight %}

![](images/rightBottom.jpg)

### None

It is used to invisible the tool tip in the SfRating control.

{% highlight c# %}

	   rating.TooltipPlacement=TooltipPlacement.None;

{% endhighlight %}

![](images/null.jpg)

## Tooltip Precision

The `ToolTipPrecision` property sets the number precisions to be displayed after decimal point in tool tip. 

N> The default value of ToolTip precision is 1. 

{% highlight c# %}

      rating.TooltipPlacement=6;

{% endhighlight %}

![](images/toolTipPrecision.jpg)
