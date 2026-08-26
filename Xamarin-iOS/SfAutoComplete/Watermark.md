---
layout: post
title: Watermark in Syncfusion® AutoComplete control for Xamarin.iOS
description: Learn how to set the watermark in AutoComplete control to provide helpful placeholder text for users.
platform: xamarin.ios
control: AutoComplete
documentation: ug
---

# Watermark

The `Watermark` property is used to display placeholder information in the SfAutoComplete control. This watermark is visible when the text box is empty or null. The watermark text disappears when the user begins to type in the SfAutoComplete control.

{% highlight C# %}

countryAutoComplete.Watermark=(NSString)"Enter a country name";

{% endhighlight %}

![Input field with watermark text](images/watermark.png)
