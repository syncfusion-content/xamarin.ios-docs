---
title: Range Support in Syncfusion® SfNumericTextBox control for Xamarin.iOS
description: Learn how to restrict the value with a specific range in SfNumericTextBox control in Xamarin.iOS platform.
platform: xamarin.ios
control: SfNumericTextBox
documentation: ug
---

# Range Support in SfNumericTextBox

You can restrict the values within a specific range by setting the `Maximum` and `Minimum` property values.

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

N> The default value of `Maximum` and `Minimum` is null.
