---
layout: post
title: Nullable values in Syncfusion® NumericTextBox for Xamarin.iOS
description: Learn how to decide maximum decimal digits to be displayed and nullable value support in Numeric TextBox.
platform: xamarin.ios
control: SfNumericTextBox
documentation: ug
---
# Assign Nullable Value

Null values can be set in the SfNumericTextBox `Value` property by setting the `AllowNull` property value to true.

N> By default, the property value is false.

{% highlight c# %}

[C#]

numericTextBox.AllowNull = true;

{% endhighlight %}


![Display the SfNumericTextBox with AllowNull](images/AllowNull.png)

## Set Hint Text

The `WaterMark` property can be used to provide a hint that helps the user get started with their input. The watermark text is visible when the value is empty or null.

{% highlight c# %}

[C#]
	
numericTextBox.WaterMark = "Principal Amount";
	 
{% endhighlight %}
	
![Display the SfNumericTextBox with WaterMark](images/WaterMark.png)