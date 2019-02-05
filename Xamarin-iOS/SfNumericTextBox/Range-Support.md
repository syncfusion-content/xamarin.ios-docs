---
title: Range Support in Syncfusion NumericTextBox control for Xamarin.iOS
description: Learn how to use range support for NumericTextBox control.
platform: Xamarin.iOS
control: NumericTextBox
documentation: ug
---

# Range Support

Restrict the values within a specific range by setting the Maximum and Minimum property values.

{% tabs %}
	
{% highlight c# %}
	
        SfNumericTextBox numericTextBox = new SfNumericTextBox();
        numericTextBox.Minimum = 50;
        numericTextBox.Maximum = 1000;
        numericTextBox.Value = 10;
        numericTextBox.Frame = new CGRect(10, 50, 350, 40);
        this.View.AddSubview(numericTextBox);
			
{% endhighlight %}

{% endtabs %}

N> Default Value of `Maximum` and `Minimum` is "null".