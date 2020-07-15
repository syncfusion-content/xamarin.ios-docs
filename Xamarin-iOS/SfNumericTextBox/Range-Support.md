---
title: Range Support in Syncfusion NumericTextBox control for Xamarin.iOS
description: Learn how to restrict the value with a specific range in NumericTextBox control in Xamarin.iOS platform.
platform: Xamarin.iOS
control: NumericTextBox
documentation: ug
---

# Range Support in NumericTextBox

Restrict the values within a specific range by setting the Maximum and Minimum property values.

{% highlight c# %}

[C#]
	
SfNumericTextBox numericTextBox = new SfNumericTextBox()
{
	Minimum = 50,
	Maximum = 1000,
	Value = 10,
};

this.Add(numericTextBox);
			
{% endhighlight %}

N> Default Value of `Maximum` and `Minimum` is "null".