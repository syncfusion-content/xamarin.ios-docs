---
layout: post
title: Range in Syncfusion RangeSlider control for Xamarin.iOS
description: Thsi section provides the details about how to set Dual thumb slider and its ranges in RangeSlider control.
platform: Xamarin.iOS
control: RangeSlider
documentation: ug
---

# The Slider Range Supports

The SfRangeSlider control supports to select range of value by using two Thumbs.

## Set Show Range

The `ShowRange` property should be set to true for displaying two thumbs in track with range of values.

N> When this property is set to false, single thumb is displayed without any range 

{% tabs %}

{% highlight c# %}

	rangeSlider.ShowRange = True;

{% endhighlight %}

{% endtabs %}

## Set Range values

This section explains about setting Range start and end value.

### RangeStart

Gets and sets the start value of the range.

{% tabs %}

{% highlight c# %}

	rangeSlider.RangeStart = 0;

{% endhighlight %}

{% endtabs %}

### RangeEnd

Gets and sets the end value of the range.

{% tabs %}

{% highlight c# %}

	rangeSlider.RangeEnd = 10;

{% endhighlight  %}

{% endtabs %} 

## ValueChangeMode

The ValueChangeMode property changes the value based on the touch of the `SfRangeSlider` control. It consists of the following two types

* Default
* OnThumbPress

N> The default value of the ValueChangeMode property is `Default`.


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

Gets or sets the range value, which ranges between Minimum and Maximum. The default value of RangeSlider is 0.

{% tabs %}

{% highlight c# %}

	 rangeSlider.Value = 30;

{% endhighlight %}

{% endtabs %}
