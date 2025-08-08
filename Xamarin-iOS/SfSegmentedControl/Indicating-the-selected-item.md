---
layout: post
title: Selection Indicator | SfSegmentedControl  | Xamarin.iOS | Syncfusion®
description: Learn how to handle selection indicator settings in Segmented Control
platform: xamarin.ios
control: SfSegmentedControl
documentation: ug
---

# Indicating the Selected Item

The Segmented Control indicates the selected item by differentiating it with the text color of the item or by using a selection strip.

## Selection Text Color

You can change the text color of the selected item to the desired color. The selected item's text color can be customized using the `SelectionTextColor` property.

{% highlight c# %}

segmentControl.SelectionTextColor = UIColor.FromRGB(4, 142, 172);

{% endhighlight %}

![SegmentedControl SelectionTextColor in Xamarin.iOS](images/Selection-indicator/SegmentedControl_Selectiontextcolor.png)

## Selection Strip

A selection strip is used to indicate the selected item in the Segmented Control. The selection strip can be customized in many forms.

### Position

The position of the selection indicator can be customized in different ways such as top, bottom, fill, and border.

###### Top

The selection strip can be displayed as a line with customizable color and thickness. It can be positioned at the top of the selected item.

{% highlight c# %}

segmentControl.SelectionIndicatorSettings = new SelectionIndicatorSettings() {Position = SelectionIndicatorPosition.Top};

{% endhighlight %}


![Selected segment item Top in Xamarin.iOS](images/Selection-indicator/SegmentedControl_Top.png)

#### Bottom

Like top placement, the selection strip can be customized by its color and thickness, and it can be positioned at the bottom of the selected item.

{% highlight c# %}

segmentControl.SelectionIndicatorSettings = new SelectionIndicatorSettings() {Position = SelectionIndicatorPosition.Bottom};

{% endhighlight %}

![Selected segment item Bottom in Xamarin.iOS](images/Selection-indicator/SegmentedControl_Bottom.png)

#### Fill

The selection strip can be placed over a segment item to indicate the selection. You can customize its color to highlight the item.

{% highlight c# %}

segmentControl.SelectionIndicatorSettings = new SelectionIndicatorSettings() {Position = SelectionIndicatorPosition.Fill};

{% endhighlight %}

![Selected segment item Fill in Xamarin.iOS](images/Selection-indicator/SegmentedControl_Fill.png)

#### Border

The selection strip can be set as a border to highlight the selected item.

{% highlight c# %}

segmentControl.SelectionIndicatorSettings = new SelectionIndicatorSettings() {Position = SelectionIndicatorPosition.Border};

{% endhighlight %}

![Selected segment item Border in Xamarin.iOS](images/Selection-indicator/SegmentedControl_Border.png)

### Color

The background color of the selection strip can be customized using the `Color` property of `SelectionIndicatorSettings`.

{% highlight c# %}

segmentControl.SelectionIndicatorSettings = new SelectionIndicatorSettings() { Color = UIColor.FromRGB(44,123,188)};

{% endhighlight %}

![Selected segment item Color in Xamarin.iOS](images/Selection-indicator/SegmentedControl_Stripcolor.png)

### Thickness

The border thickness of the selection strip can be customized using the `StrokeThickness` property of `SelectionIndicatorSettings`.

{% highlight c# %}

segmentControl.SelectionIndicatorSettings = new SelectionIndicatorSettings() { StrokeThickness= 10 };

{% endhighlight %}






