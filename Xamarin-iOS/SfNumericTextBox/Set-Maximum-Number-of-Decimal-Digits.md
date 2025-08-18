---
layout: post
title: Maximum decimal digits in Syncfusion® NumericTextBox Xamarin.iOS
description: Learn how to decide maximum decimal digits to be displayed and nullable value support in Numeric TextBox.
platform: xamarin.ios
control: SfNumericTextBox
documentation: ug
---
# Set Maximum Number of Decimal Digits

The maximum number of digits to be displayed after the decimal point can be specified by using the `MaximumNumberDecimalDigits` property.

N> The `MaximumNumberDecimalDigits` property can be provided with positive values only.

{% highlight c# %}

[C#]

numericTextBox.MaximumNumberDecimalDigits = 2;
  
{% endhighlight %}

![Display the SfNumericTextBox with MaximumNumberDecimalDigits](images/MaximumNumberDecimalDigits.png)

