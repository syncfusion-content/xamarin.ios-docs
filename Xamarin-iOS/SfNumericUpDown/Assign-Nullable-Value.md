---
layout: post
title: Various Features in Syncfusion NumericUpDown control for Xamarin.iOS
description: Learn how to decide maximum decimal digits to be displayed, nullable value support, autoreverse, setting range and configuring step value in NumericUpDown
platform: Xamarin.iOS
control: NumericUpDown
documentation: ug
---
# Assign Nullable Value

The null values can be set in SfNumericUpDown `Value` property, by setting `AllowNull` property value to true.

N> By default, the property value is false.

{% tabs %}

{% highlight C# %}

[C#]

numeric.AllowNull = true;

{% endhighlight %}

{% endtabs %}

![Display the NumericUpDown with Null value](images/allownull.png)

## Set Hint Text

The `WaterMark` text is used to display some information regarding the SfNumericEditBox. This watermark is visible when textbox is empty or Null.

{% tabs %}

{% highlight c# %}

[C#]

numeric.WaterMark = (NSString)"NumericUpDown";

{% endhighlight %}

{% endtabs %}

N> By default the property value is false

![Display the NumericUpDown with hint text](images/watermark.png)
