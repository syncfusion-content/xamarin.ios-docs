---
layout: post
title: Events in Syncfusion® RangeSlider control for Xamarin.iOS
description: This section provides details about how to handle events in RangeSlider control for Xamarin.iOS
platform: xamarin.ios
control: RangeSlider 
documentation: ug
---

# Events in RangeSlider
## How to Get Notifications When a Thumb Drag is Started and Completed?

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

## How to Trigger ValueChange Event?

The `ValueChange` event is triggered when the `SfRangeSlider` value is changed. The argument contains the value of the RangeSlider.

`Value` - Used to get or set the value for the range slider.

{% tabs %}

{% highlight c# %}

        private void RangeSlider_ValueChange(object sender, ValueEventArgs e)
        {
            var rangeValue = e.Value;
        }

{% endhighlight %}

{% endtabs %}

## How to Trigger RangeChange Event?

The `RangeChange` event is triggered when either `RangeStart` or `RangeEnd` values are changed. The argument contains the following information:

`RangeStart` – Gets or sets the range start value of the range slider.
`RangeEnd` – Gets or sets the range end value of the range slider.

{% tabs %}

{% highlight c# %}

     private void RangeSlider_RangeValueChange(object sender, RangeEventArgs e)
        {
            var rangeStart = e.RangeStart;
            var rangeEnd = e.RangeEnd;
        }

{% endhighlight %}

{% endtabs %}

## How to Trigger RangeStartChange Event?

The `RangeStartChange` event is triggered when the `RangeStart` value is changed. The argument contains the `RangeStart` value.

{% tabs %}

{% highlight c# %}

        private void RangeSlider_RangeStartValueChange(object sender, RangeStartEventArgs e)
        {
            var rangeStart = e.RangeStart;
        }

{% endhighlight %}

{% endtabs %}

## How to Trigger RangeEndChange Event?

The `RangeEndChange` event is triggered when the `RangeEnd` value is changed. The argument contains the `RangeEnd` value.

{% tabs %}

{% highlight c# %}

        private void RangeSlider_RangeEndValueChange(object sender, RangeEndEventArgs e)
        {
            var rangeEnd = e.RangeEnd;
        }

{% endhighlight %}

{% endtabs %}

## How to Trigger ThumbTouchDown Event?

The `ThumbTouchDown` event occurs when touching the thumb. The argument contains the state of the thumb.

`IsStartThumb` - Gets the state whether the thumb touch down position is start or end. If the thumb touch down position is start, then the `IsStartThumb` state is `true`. If it's end, then the `IsStartThumb` state is `false`. It is a read-only property.

{% tabs %}

{% highlight c# %}

        private void RangeSlider_ThumbTouchDown(object sender, DragThumbEventArgs e)
        {
            var isTouchDown = e.IsStartThumb;
        }

{% endhighlight %}

{% endtabs %}

## How to Trigger ThumbTouchUp Event?

The `ThumbTouchUp` event occurs when releasing the thumb. The argument contains the state of the thumb.
`IsStartThumb` - Gets the state whether the thumb touch up position is start or end. If the thumb touch up position is start, then the `IsStartThumb` state is `true`. If it's end, then the `IsStartThumb` state is `false`. It is a read-only property.

{% tabs %}

{% highlight c# %}

        private void RangeSlider_ThumbTouchUp(object sender, DragThumbEventArgs e)
        {
            var isTouchUp = e.IsStartThumb;
        }
		
{% endhighlight %}

{% endtabs %}