---
layout: post
title: Localization in Syncfusion NumericTextBox control for Xamarin.iOS
description: Learn how to localize the  NumericTextBox
platform: Xamarin.iOS
control: NumericTextBox
documentation: ug
---
# Localization

The SFNumericTextBox value can be localized to any specific culture. It can be specified by setting the `Culture` property with `NSLocale` object instance.

N> Default `Culture` property value is en-US.

{% tabs %}

{% highlight c# %}

numericTextBox.CultureInfo = new NSLocale("zh-CN");
	
{% endhighlight %}

{% endtabs %}

![](images/Culture.png)

