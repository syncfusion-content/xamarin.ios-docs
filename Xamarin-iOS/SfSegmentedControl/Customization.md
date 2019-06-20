---
layout: post
title: Customization | SfSegmentedControl | Xamarin.iOS | Syncfusion 
description: How to customize the segmented control
platform: Xamarin.iOS
control: SfSegmentedControl
documentation: ug
---

# Customization

The segmented control supports customizing segment color, text color, icon size, selection color, and more. This control also supports enabling the segments to fit your application’s theme. It can be customized in the following areas.

## Text appearance

The text inside the segmented control can be customized by its font size, color, and its font family.

### Font family and size

You can customize the font family and font size of the segmented item using the `Font` property.

{% highlight c# %}

segmentedControl.Font = UIFont.FromName("Helvetica-Bold", 10f);

{% endhighlight %}

{% highlight c# %}

segmentedControl.Font = UIFont.SystemFontOfSize(20);

{% endhighlight %}

![](images/Customization/SegmentedControl_Font.png)

### Font color

You can customize the text color of the segmented item using the `FontColor` property.

{% highlight c# %}

segmentedControl.FontColor = UIColor.Red;

{% endhighlight %}

![](images/Customization/SegmentedControl_Fontcolor.png)

## Border

You can customize the border of segmented control by using the `BorderColor`  and `BorderThickness` properties and border of each segment items can also customized by using the `SegmentBorderColor`  and `SegmentBorderThickness`.

{% highlight c# %}

segmentedControl.BorderColor = UIColor.Red;
segmentedControl.BorderThickness = 5;

{% endhighlight %}

![](images/Customization/SegmentedControl_Border.png)

## Padding

You can handle the padding between the segment items by using the `SegmentPadding` property.

{% highlight c# %}

segmentedControl.SegmentPadding = 15;

{% endhighlight %}

![](images/Customization/SegmentedControl_Padding.png)

## Corner radius

The segmented control provides corner radius support for control, each segment items and selected segment item.

### Control radius

The segmented control also handles corner radius for border line of the whole control using `CornerRadius` property.

{% highlight c# %}

segmentedControl.CornerRadius = 15;

{% endhighlight %}

![](images/Customization/SegementedControl_ControlRadius.png)

### Segment items radius

The segmented control customizes the corner radius for each segmented item using `SegmentCornerRadius` property.

{% highlight c# %}

segmentedControl.SegmentCornerRadius = 15;

{% endhighlight %}

{% endtabs %}

![](images/Customization/SegmentedControl_ItemCornerRadius.png)

### Selected segment radius

You can customize the corner radius for selected segment item using the `CornerRadius` property of `SelectionIndicatorSettings`.

{% highlight c# %}

segmentedControl.SelectionIndicatorSettings = new SelectionIndicatorSettings() {CornerRadius = 15};

{% endhighlight %}

![](images/Customization/SegmentedControl_SelectionRadius.png)

## Color

The segmented control allow users to customize the background color of control, segment items and selected segment item.

### Control color

You can customize the background color of the control by setting value for the `Color` property.

{% highlight c# %}

segmentedControl.Color = UIColor.FromRGB(4, 142, 172);

{% endhighlight %}

![](images/Customization/SegmentedControl_Color.png)

### Segment items color

You can customize the background color of the for each segment items by setting value for the `SegmentBackgroundColor` property.

{% highlight c# %}

segmentedControl.SegmentBackgroundColor = UIColor.FromRGB(53,80,136);

{% endhighlight %}

![](images/Customization/SegmentedControl_SegmentColor.png)

### Selected segment color

You can customize the background color of selected segment item using the `Color` property of `SelectionIndicatorSettings`.

{% highlight c# %}

segmentedControl.SelectionIndicatorSettings = new SelectionIndicatorSettings() {Color = UIColor.FromRGB(53,80,136)};

{% endhighlight %}


