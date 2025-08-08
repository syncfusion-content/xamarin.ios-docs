---
layout: post
title: Nullable values in Syncfusion® NumericUpDown for Xamarin.iOS
description: Learn how to decide maximum decimal digits to be displayed, nullable value support, autoreverse, setting range and configuring step value in SfNumericUpDown
platform: xamarin.ios
control: SfNumericUpDown
documentation: ug
---
# Assign Nullable Value

Null values can be set in the SfNumericUpDown `Value` property by setting the `AllowNull` property to true.

N> By default, the property value is false.

{% highlight C# %}

[C#]

numeric.AllowNull = true;

{% endhighlight %}

![Display the SfNumericUpDown with Null value](images/allownull.png)

## Set Hint Text

The `WaterMark` text is used to display information about the SfNumericUpDown control. This watermark is visible when the control is empty or null.

{% highlight c# %}

[C#]

numeric.WaterMark = (NSString)"NumericUpDown";

{% endhighlight %}

N> By default, the property value is false.

![Display the SfNumericUpDown with hint text](images/watermark.png)
