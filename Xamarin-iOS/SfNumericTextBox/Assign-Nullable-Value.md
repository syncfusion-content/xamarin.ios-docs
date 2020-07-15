---
layout: post
title: Various features in Syncfusion NumericTextBox control for Xamarin.iOS
description: Learn how to decide maximum decimal digits to be displayed and nullable value support in NumericTextBox.
platform: Xamarin.iOS
control: NumericTextBox
documentation: ug
---
# Assign Nullable Value

The null values can be set in SfNumericTextBox `Value` property, by setting `AllowNull` property value to true.

N> By default, the property value is false.

{% highlight c# %}

[C#]

numericTextBox.AllowNull = true;

{% endhighlight %}


![Display the NumericTextBox with AllowNull](images/AllowNull.png)

## Set Hint Text

The `WaterMark` property can be used to provide a hint that helps the user to get started with their input. The watermark text is visible when value is empty or null.

{% highlight c# %}

[C#]
	
numericTextBox.WaterMark = "Principal Amount";
	 
{% endhighlight %}
	
![Display the NumericTextBox with WaterMark](images/WaterMark.png)