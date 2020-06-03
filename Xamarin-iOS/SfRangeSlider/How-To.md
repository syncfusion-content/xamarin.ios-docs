---
layout: post
title: Events in Syncfusion RangeSlider control for Xamarin.iOS
description: Learn how to populate events in RangeSlider control
platform: Xamarin.iOS
control: RangeSlider 
documentation: ug
---

## How to get notifications when a thumb drag is started and completed?

The `DragStarted` event is raised when a thumb is dragged. After the thumb releases the pointer capture, the `DragCompleted` event is raised. The `IsStartThumb` property of the `DragThumbEventArgs` returns a boolean value, which indicates the thumb used for performing drag operations.

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>IsStartThumb</td>
<td>Indicates the thumb used for performing drag operations.</td>
</tr>
</table>

{% tabs %}

{% highlight c# %}

	rangeSlider.DragStarted += (object sender, DragThumbEventArgs e) =>
	{
         //perform the operation
	};

	rangeSlider.DragCompleted += (object sender, DragThumbEventArgs e) =>
	{
         //perform the operation
	};

{% endhighlight %}

{% endtabs %}

## How to trigger ValueChange event?

The `ValueChange` event is triggered when `SfRangeSlider` value is changed. The argument contains the value of RangeSlider.

`Value` - Used to gets or sets the value for range slider.

{% tabs %}

{% highlight c# %}

        private void RangeSlider_ValueChange(object sender, ValueEventArgs e)
        {
            var rangeValue = e.Value;
        }

{% endhighlight %}

{% endtabs %}

## How to trigger RangeChange event?

The `RangeChange` event is triggered when either ``RangeStart`` or `RangeEnd` values are changed. The argument contains the following information.

`RangeStart` – Gets or sets the range start value of range slider.
`RangeEnd` – Gets or sets the range end value of range slider.

{% tabs %}

{% highlight c# %}

     private void RangeSlider_RangeValueChange(object sender, RangeEventArgs e)
        {
            var rangeStart = e.RangeStart;
            var rangeEnd = e.RangeEnd;
        }

{% endhighlight %}

{% endtabs %}

## How to trigger RangeStartChange event?

The `RangeStartChange` event is triggered when `RangeStart` value is changed. The argument contains `RangeStart` value.

{% tabs %}

{% highlight c# %}

        private void RangeSlider_RangeStartValueChange(object sender, RangeStartEventArgs e)
        {
            var rangeStart = e.RangeStart;
        }

{% endhighlight %}

{% endtabs %}

## How to trigger RangeEndChange event?

The `RangeEndChange` event is triggered when `RangeEnd` value is changed. The argument contains `RangeEnd` value.

{% tabs %}

{% highlight c# %}

        private void RangeSlider_RangeEndValueChange(object sender, RangeEndEventArgs e)
        {
            var rangeEnd = e.RangeEnd;
        }

{% endhighlight %}

{% endtabs %}

## How to trigger ThumbTouchDown event?

The `ThumbTouchDown` event occurs when touching the thumb. The argument contains the state of the thumb.

`IsStartThumb` - Gets the state whether thumb touch down position is start or end. If the thumb touch down position is start, then `IsStartThumb` state is true. If it's end, then `IsStartThumb` state is false. It is a read only property.

{% tabs %}

{% highlight c# %}

        private void RangeSlider_ThumbTouchDown(object sender, DragThumbEventArgs e)
        {
            var isTouchDown = e.IsStartThumb;
        }

{% endhighlight %}

{% endtabs %}

## How to trigger ThumbTouchUp event?

`IsStartThumb` - Gets the state whether thumb touch up position is start or end. If the thumb touch up position is start, then `IsStartThumb` state is true. If it's end, then IsStartThumb state is false. It is a read only property.

{% tabs %}

{% highlight c# %}

        private void RangeSlider_ThumbTouchUp(object sender, DragThumbEventArgs e)
        {
            var isTouchUp = e.IsStartThumb;
        }
		
{% endhighlight %}

{% endtabs %}