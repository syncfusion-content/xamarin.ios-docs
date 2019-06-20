---
layout: post
title: Selection Indicator | SfSegmentedControl  | Xamarin.iOS | Syncfusion
description: How to handle selection indicator settings in segmented control
platform: Xamarin.iOS
control: SfSegmentedControl
documentation: ug
---

# Indicating the selected item

The segmented control indicates the selected item by differentiating it with text color of the item or using selection strip.

## Selection text color

You can change the text color of the selected item to desired color. The selected item's text color can be customized using the `SelectionTextColor` property.

{% highlight c# %}

segmentControl.SelectionTextColor = UIColor.FromRGB(4, 142, 172);

{% endhighlight %}

![](images/Selection-indicator/SegmentedControl_Selectiontextcolor.png)

## Selection Strip

A selection strip is used to indicate the selected item in the segmented control. The selection strip can be customized in many forms.

#### Position

The position of the selection indicator can be customized in different ways such as top, bottom, fill, and border.

###### Top

The selection strip can be displayed as a line with customizable color and thickness. It can be positioned at the top of selected item.

{% highlight c# %}

segmentControl.SelectionIndicatorSettings = new SelectionIndicatorSettings() {Position = SelectionIndicatorPosition.Top};

{% endhighlight %}


![](images/Selection-indicator/SegmentedControl_Top.png)

###### Bottom

Like top placement, selection strip can be customized by its color and thickness and can be positioned at the bottom of selected item.

{% highlight c# %}

segmentControl.SelectionIndicatorSettings = new SelectionIndicatorSettings() {Position = SelectionIndicatorPosition.Bottom};

{% endhighlight %}

![](images/Selection-indicator/SegmentedControl_Bottom.png)

###### Fill

The selection strip can be placed over a segment item to indicate the selection. You can customize its color to highlight the item.

{% highlight c# %}

segmentControl.SelectionIndicatorSettings = new SelectionIndicatorSettings() {Position = SelectionIndicatorPosition.Fill};

{% endhighlight %}

![](images/Selection-indicator/SegmentedControl_Fill.png)

###### Border

The selection strip can be set as a border to highlight the selected item.

{% highlight c# %}

segmentControl.SelectionIndicatorSettings = new SelectionIndicatorSettings() {Position = SelectionIndicatorPosition.Border};

{% endhighlight %}

![](images/Selection-indicator/SegmentedControl_Border.png)

#### Color

The background color of the selection strip can be customized using the `Color` property of `SelectionIndicatorSettings`.

{% highlight c# %}

segmentControl.SelectionIndicatorSettings = new SelectionIndicatorSettings() { Color = UIColor.FromRGB(44,123,188)};

{% endhighlight %}

![](images/Selection-indicator/SegmentedControl_Stripcolor.png)

#### Thickness

The border thickness of the selection strip can be customized using the `Thickness` property of `SelectionIndicatorSettings`.

{% highlight c# %}

segmentControl.SelectionIndicatorSettings = new SelectionIndicatorSettings() { StrokeThickness= 10 };

{% endhighlight %}





