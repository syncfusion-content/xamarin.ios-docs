---
layout: post
title: Using Mask Characters as Literals in Syncfusion® SfMaskedEdit
description: Learn how to use mask characters as literals in Syncfusion® SfMaskedEdit for Xamarin.iOS by escaping them with backslash for special character display.
platform: xamarin.ios
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---

# Using Mask Characters as Literals

To use a mask character as a literal, precede the mask character with a backslash (\). For example, to display the dollar sign ($), set the mask as follows:

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = @"\$ 0000";
{% endhighlight %}
{% endtabs %}

This will produce a mask that displays a dollar sign ($) followed by the prompt characters for entering numbers.

![Dollar sign with number input](SfMaskedEditImages/maskasliteral.png)

This demo can be downloaded from this [link](http://files2.syncfusion.com/Xamarin.iOS/Samples/MaskedEdit_UsingMaskCharactersAsLiterals.zip).
