---
layout: post
title: Hiding prompt characters of Syncfusion® SfMaskedEdit Xamarin.iOS
description: Learn how to hide prompt characters in Syncfusion® SfMaskedEdit for Xamarin.iOS using HidePromptOnLeave property when control loses focus.
platform: xamarin.ios
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---

# Hiding Prompt Characters

When the `HidePromptOnLeave` property is set to true, prompt characters are hidden when the control loses focus. The prompt characters are restored when the control regains focus.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.HidePromptOnLeave = true;
{% endhighlight %}
{% endtabs %}

![SfMaskedEdit hiding prompt characters when control loses focus](SfMaskedEditImages/Hideprompt.png)

This demo can be downloaded from this [link](http://files2.syncfusion.com/Xamarin.iOS/Samples/MaskedEdit_HidingPrompt.zip).
