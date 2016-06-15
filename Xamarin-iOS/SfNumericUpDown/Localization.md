---
layout: post
title: Localization in Syncfusion NumericUpDown control for Xamarin.iOS
description: Learn how to localize the NumericUpDown control
platform: Xamarin.iOS
control: NumericUpDown
documentation: ug
---
# Localization

## Culture

The NumericUpDown value can be localized to any specific culture. It can be specified by setting the `Culture` property with `System.Globalization.CultureInfo` object instance.

N> Default `Culture` property value is en-US.

{% highlight C# %}

	numericupdown.Culture = new System.Globalization.CultureInfo("en-IN");
	
{% endhighlight %}

![](images/Culture.png)




