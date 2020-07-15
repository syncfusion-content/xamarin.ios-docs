---
layout: post
title: Localization in Syncfusion NumericTextBox control for Xamarin.iOS
description: Learn how to localize the Syncfusion NumericTextBox control to any specific culture in Xamarin.iOS platform.
platform: Xamarin.iOS
control: NumericTextBox
documentation: ug
---
# Localization in NumericTextBox

The SfNumericTextBox value can be localized to any specific culture. It can be specified by setting the `CultureInfo` property with `NSLocale` object instance.

N> Default `CultureInfo` property value is en-US.

{% highlight c# %}

[C#]

numericTextBox.CultureInfo = new NSLocale("zh-CN");
	
{% endhighlight %}

![Display the NumericTextBox with Culture](images/Culture.png)

