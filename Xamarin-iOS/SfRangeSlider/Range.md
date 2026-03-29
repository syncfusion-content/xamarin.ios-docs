---
layout: post
title: Range in Syncfusion® RangeSlider control for Xamarin.iOS
description: This section provides details about how to set dual thumb slider and its ranges in RangeSlider control.
platform: xamarin.ios
control: RangeSlider
documentation: ug
---

# Slider Range Support

The SfRangeSlider control supports selecting a range of values by using two thumbs.

## Set Show Range

The `ShowRange` property should be set to `true` for displaying two thumbs in the track with a range of values.

> **Note:** When this property is set to `false`, a single thumb is displayed without any range.

{% tabs %}

{% highlight c# %}

	rangeSlider.ShowRange = True;

{% endhighlight %}

{% endtabs %}

## Set Range Values

This section explains how to set the range start and end values.

### RangeStart

Gets or sets the start value of the range.

{% tabs %}

{% highlight c# %}

	rangeSlider.RangeStart = 0;

{% endhighlight %}

{% endtabs %}

### RangeEnd

Gets or sets the end value of the range.

{% tabs %}

{% highlight c# %}

	rangeSlider.RangeEnd = 10;

{% endhighlight  %}

{% endtabs %} 

## ValueChangeMode

The `ValueChangeMode` property changes the value based on the touch interaction with the `SfRangeSlider` control. It consists of the following two types:

* Default
* OnThumb

> **Note:** The default value of the `ValueChangeMode` property is `Default`.


### Default

The value is updated when you touch inside the control.

{% tabs %}

{% highlight c# %}

	rangeSlider.ValueChangeMode = ValueChangeMode.Default;

{% endhighlight %}

{% endtabs %}


### OnThumb

The value is updated when you touch or move the thumb/knob.

{% tabs %}

{% highlight c# %}

	rangeSlider.ValueChangeMode = ValueChangeMode.OnThumb;

{% endhighlight %}

{% endtabs %}

## Value

Gets or sets the range value, which ranges between `Minimum` and `Maximum`. The default value of RangeSlider is 0.

{% tabs %}

{% highlight c# %}

	 rangeSlider.Value = 30;

{% endhighlight %}

{% endtabs %}
