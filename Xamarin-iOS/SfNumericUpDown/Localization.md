---
layout: post
title: Localization in Syncfusion NumericUpDown control for Xamarin.iOS
description: Learn how to localize the Syncfusion NumericUpDown control to any specific culture in Xamarin.iOS platform.
platform: Xamarin.iOS
control: NumericUpDown
documentation: ug
---
# Localization in SfNumericUpDown

## Culture

The NumericUpDown value can be localized to any specific culture. It can be specified by setting the `CultureInfo` property with `System.Globalization.CultureInfo` object instance.

N> Default `CultureInfo` property value is en-US.

{% highlight C# %}

[C#]

numeric.CultureInfo = new  new NSLocale("en-IN");
	
{% endhighlight %}

![Display the NumericUpDown with culture](images/Culture.png)




