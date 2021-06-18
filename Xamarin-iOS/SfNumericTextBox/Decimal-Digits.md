---
layout: post
title: Various features in Syncfusion Numeric TextBox control for Xamarin.iOS
description: Learn how to decide maximum decimal digits and default decimal digits to be displayed and nullable value support in Numeric TextBox.
platform: Xamarin.iOS
control: SfNumericTextBox
documentation: ug
---
# Set Maximum Number of Decimal Digits

The maximum number of digits to be displayed after the decimal point can be specified by using the [`MaximumNumberDecimalDigits`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfNumericTextBox.iOS.SfNumericTextBox_1.html#Syncfusion_SfNumericTextBox_iOS_SfNumericTextBox_MaximumNumberDecimalDigits) property. 

N> The `MaximumNumberDecimalDigits` property can be provided with positive value only.

{% highlight c# %}

[C#]

numericTextBox.MaximumNumberDecimalDigits = 2;
  
{% endhighlight %}

![Display the SfNumericTextBox with MaximumNumberDecimalDigits](images/MaximumNumberDecimalDigits.png)

## Remove Default Decimal Digits in Xamarin Numeric Entry

Based on the [`MaximumNumberDecimalDigits`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfNumericTextBox.iOS.SfNumericTextBox_1.html#Syncfusion_SfNumericTextBox_iOS_SfNumericTextBox_MaximumNumberDecimalDigits) property, the default number of decimal digits is displayed. By disabling the `AllowDefaultDecimalDigits` Boolean property, those default digits can be removed from the numeric entry view. 

{% tabs %}

{% highlight c# %}
            
    numericTextBox.AllowDefaultDecimalDigits = false;
  
{% endhighlight %}

{% endtabs %}

![Display the textbox value without default decimal digits](images/AllowDefaultDecimalDigits.png)
