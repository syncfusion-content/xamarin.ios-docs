---
layout: post
title: Configure Selection Values in Syncfusion® RangeSlider
description: Learn how to configure minimum value, maximum value, tick frequency, step frequency, and snapping modes for RangeSlider
platform: xamarin.ios
control: RangeSlider
documentation: ug
---

# Selection Value Configuration

Various customization options are available to configure the selection value in SfRangeSlider.

## Set Minimum Value

Gets or sets the minimum possible value of the range. The thumb cannot move beyond this value.

{% tabs %}

{% highlight c# %}

rangeSlider.Minimum = 0;

{% endhighlight %}

{% endtabs %}

## Set Maximum Value

Gets or sets the maximum possible value of the range. The thumb cannot move beyond this value.

{% tabs %}

{% highlight c# %}

rangeSlider.Maximum = 24;

{% endhighlight %}

{% endtabs %}

## Set Tick Frequency

The `TickFrequency` property is used to determine the number of ticks to be displayed along the track based on `Minimum` and `Maximum` values.

{% tabs %}

{% highlight c# %}

rangeSlider.TickFrequency=4;

{% endhighlight %}

{% endtabs %}

> **Note:** When the `SnapsTo` property is set to `Ticks`, the `TickFrequency` is used to specify the interval between snap points.

## Set Interval Between Snap Points

The `StepFrequency` property is used to specify the interval between snap points.

{% tabs %}

{% highlight c# %}

rangeSlider.StepFrequency=4;

{% endhighlight %}

{% endtabs %}

> **Note:** When the `SnapsTo` property is set to `StepValues`, the `StepFrequency` property is enabled.

## Set Snapping Mode

The `SnapsTo` property determines whether the RangeSlider snaps to steps or ticks. Available options for this property are:

* `StepValues` - The `StepFrequency` property will be used to specify the interval between snap points.
* `Ticks` - The `TickFrequency` property will be used to specify the interval between snap points.
* `None` - The thumb moves independently of any values.

> **Note:** The default option is `Ticks`.

{% tabs %}

{% highlight c# %}

rangeSlider.SnapsTo = SFSnapsTo.SFSnapsToTicks;

{% endhighlight %}

{% endtabs %}
