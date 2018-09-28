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

                                                
{% highlight c# %}

	rangeSlider.DragStarted+=(object sender, DragThumbEventArgs e) =>
	{
         //perform the operation
	};

	rangeSlider.DragCompleted+=(object sender, DragThumbEventArgs e) =>
	{
         //perform the operation
	};

{% endhighlight %}
                                    
