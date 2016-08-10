---
layout: post
title: Various features in Syncfusion NumericTextBox control for Xamarin.iOS
description: Learn how to decide maximum decimal digits to be displayed and nullable value support in NumericTextBox.
platform: Xamarin.iOS
control: NumericTextBox
documentation: ug
---
# Set Maximum Number of Decimal Digits

The maximum number of digits to be displayed after the decimal point can be specified by using `MaximumNumberDecimalDigits` property. 

N> The `MaximumNumberDecimalDigits` property can be provided with positive value only.

{% tabs %}

{% highlight c# %}

numericTextBox.MaximumNumberDecimalDigits=2;
  
{% endhighlight %}

{% endtabs %}

![](images/MaximumNumberDecimalDigits.png)

## Nullable Value

The null values can be set in NumericTextBox `Value` property, by setting `AllowNull` property value to true.

N> By default, the property value is false.

{% highlight c# %}

numericTextBox.AllowNull=true;

{% endhighlight %}

![](images/AllowNull.png)

