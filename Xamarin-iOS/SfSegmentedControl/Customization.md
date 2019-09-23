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

The text inside the segmented control can be customized by its font size, color, and font family.

### Font family and size

You can customize the font family and font size of the segmented item using the `Font` property.

{% highlight c# %}

segmentedControl.Font = UIFont.FromName("Helvetica-Bold", 10f);

{% endhighlight %}

{% highlight c# %}

segmentedControl.Font = UIFont.SystemFontOfSize(20);

{% endhighlight %}

![SegmentedControl Font in Xamarin.iOS](images/Customization/SegmentedControl_Font.png)

### Font color

You can customize the text color of the segmented item using the `FontColor` property.

{% highlight c# %}

segmentedControl.FontColor = UIColor.Red;

{% endhighlight %}

![SegmentedControl FontColor in Xamarin.iOS](images/Customization/SegmentedControl_Fontcolor.png)

## Border

You can customize the border of the segmented control by using the `BorderColor`  and `BorderThickness` properties. Border of each segment item can also be customized using the `SegmentBorderColor`  and `SegmentBorderThickness` properties.

{% highlight c# %}

segmentedControl.BorderColor = UIColor.Red;
segmentedControl.BorderThickness = 5;

{% endhighlight %}

![SegmentedControl Border in Xamarin.iOS](images/Customization/SegmentedControl_Border.png)

## Padding

You can handle the padding between the segment items by using the `SegmentPadding` property.

{% highlight c# %}

segmentedControl.SegmentPadding = 15;

{% endhighlight %}

![SegmentedControl Padding in Xamarin.iOS](images/Customization/SegmentedControl_Padding.png)

## Corner radius

The segmented control provides corner radius support to control, each segment item and selected segment item.

### Control radius

The segmented control also handles corner radius for border line of the whole control using the `CornerRadius` property.

{% highlight c# %}

segmentedControl.CornerRadius = 15;

{% endhighlight %}

![SegmentedControl CornerRadius in Xamarin.iOS](images/Customization/SegmentedControl_ControlRadius.png)

### Segment items radius

The segmented control customizes corner radius for each segmented item using the `SegmentCornerRadius` property.

{% highlight c# %}

segmentedControl.SegmentCornerRadius = 15;

{% endhighlight %}

![SegmentedControl SegmentCornerRadius in Xamarin.iOS](images/Customization/SegmentedControl_ItemCornerRadius.png)

### Selected segment radius

You can customize the corner radius for selected segment item using the `CornerRadius` property of `SelectionIndicatorSettings`.

{% highlight c# %}

segmentedControl.SelectionIndicatorSettings = new SelectionIndicatorSettings() {CornerRadius = 15};

{% endhighlight %}

![Selected segment item CornerRadius in Xamarin.iOS](images/Customization/SegmentedControl_SelectionRadius.png)

## Color

The segmented control allows users to customize the background color of control, segment items and selected segment item.

### Control color

You can customize the background color of the control by setting a value to the `Color` property.

{% highlight c# %}

segmentedControl.Color = UIColor.FromRGB(4, 142, 172);

{% endhighlight %}

![SegmentedControl Color in Xamarin.iOS](images/Customization/SegmentedControl_Color.png)

### Segment items color

You can customize the background color of each segment item by setting a value to the `SegmentBackgroundColor` property.

{% highlight c# %}

segmentedControl.SegmentBackgroundColor = UIColor.FromRGB(53,80,136);

{% endhighlight %}

![SegmentedControl SegmentBackgroundColor in Xamarin.iOS](images/Customization/SegmentedControl_SegmentColor.png)

### Selected segment color

You can customize the background color of selected segment item using the `Color` property of `SelectionIndicatorSettings`.

{% highlight c# %}

segmentedControl.SelectionIndicatorSettings = new SelectionIndicatorSettings() {Color = UIColor.FromRGB(53,80,136)};

{% endhighlight %}

## Programmatically scrolling in segmented control 

SegmentedControl allows programmatic scrolling based on the index and item using the `ScrollTo` methods mentioned below.

### ScrollTo(index, scrollToPosition)

This method is used to scroll the segment item based on given index and [`ScrollToPosition`]() value.

{% tabs %}

{% highlight c# %}

segmentedControl.ScrollTo(5,  Syncfusion.iOS.Buttons.ScrollToPosition.Start);

{% endhighlight %}

{% endtabs %}

### ScrollTo(item, scrollToPosition)

This method is used to scroll the segment item based on the given data or `SfSegmentItem` and [`ScrollToPosition`]() value.

{% tabs %}

{% highlight c# %}

segmentedControl.ScrollTo(viewModel.Items[5], Syncfusion.iOS.Buttons.ScrollToPosition.Start);

{% endhighlight %}

{% endtabs %}