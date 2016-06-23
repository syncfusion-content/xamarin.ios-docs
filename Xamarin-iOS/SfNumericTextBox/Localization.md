---
layout: post
title: Localization in Syncfusion NumericTextBox control for Xamarin.iOS
description: Learn how to localize the  NumericTextBox
platform: Xamarin.iOS
control: NumericTextBox
documentation: ug
---
# Localization

## Culture

The NumericTextBox value can be localized to any specific culture. It can be specified by setting the `Culture` property with `NSLocale` object instance.

N> Default `Culture` property value is en-US.

{% highlight c# %}

	numericTextBox.Culture = new NSLocale("zh-CN");
	
{% endhighlight %}


![](images/Culture.png)

