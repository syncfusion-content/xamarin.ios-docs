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

numericupdown.AllowNull=true;

{% endhighlight %}

{% endtabs %}

![](images/allownull.png)

## Set Hint Text

The `WaterMark` text is used to display some information regarding the SfNumericEditBox. This watermark is visible when textbox is empty or Null.

{% tabs %}

{% highlight c# %}

numericupdown.WaterMark = (NSString)"NumericUpDown";

{% endhighlight %}

{% endtabs %}

N> By default the property value is false

![](images/watermark.png)
