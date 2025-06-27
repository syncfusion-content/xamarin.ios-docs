---
layout: post
title: Localization in Syncfusion® SfNumericUpDown control for Xamarin.iOS
description: Learn how to localize the Syncfusion® SfNumericUpDown control to any specific culture in Xamarin.iOS platform.
platform: xamarin.ios
control: SfNumericUpDown
documentation: ug
---
# Localization in SfNumericUpDown

## Culture

The SfNumericUpDown value can be localized to any specific culture. It can be specified by setting the `CultureInfo` property with an `NSLocale` object instance.

N> The default `CultureInfo` property value is en-US.

{% highlight C# %}

[C#]

numeric.CultureInfo = new  new NSLocale("en-IN");
	
{% endhighlight %}

![Display the SfNumericUpDown with culture](images/Culture.png)
