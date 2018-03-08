---
layout: post
title: Getting Started with Syncfusion SfMaskedEdit control for Xamarin.IOS
description: A quick tour to initial users on Syncfusion SfMaskedEdit control for Xamarin.IOS platform 
platform: Xamarin.IOS
control: SfMaskedEdit
documentation: ug
---

# Using Mask Characters as Literals

To use mask character as a literal, precede the mask character with a backslash (\). For example, to display the dollar sign ($), then set the mask as follows:

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = @"\$ 0000";
{% endhighlight %}
{% endtabs %}

This will produce a mask that displays a dollar sign ($) followed by the prompt characters for entering numbers.

![](SfMaskedEditImages/maskasliteral.png)

This demo can be downloaded from this [link](http://www.syncfusion.com/downloads/support/directtrac/general/ze/MaskCharactersAsLiterals809955669.zip).
