---
layout: post
title: Various features in Syncfusion Numeric TextBox control for Xamarin.iOS
description: Learn how to decide maximum decimal digits to be displayed and nullable value support in Numeric TextBox.
platform: Xamarin.iOS
control: SfNumericTextBox
documentation: ug
---
# Set Maximum Number of Decimal Digits

The maximum number of digits to be displayed after the decimal point can be specified by using `MaximumNumberDecimalDigits` property. 

N> The `MaximumNumberDecimalDigits` property can be provided with positive value only.

{% highlight c# %}

[C#]

numericTextBox.MaximumNumberDecimalDigits = 2;
  
{% endhighlight %}

![Display the SfNumericTextBox with MaximumNumberDecimalDigits](images/MaximumNumberDecimalDigits.png)

