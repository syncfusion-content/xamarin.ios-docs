---
layout: post
title: Getting Started with Syncfusion SfMaskedEdit control for Xamarin.IOS
description: A quick tour to initial users on Syncfusion SfMaskedEdit control for Xamarin.IOS platform 
platform: Xamarin.IOS
control: SfMaskedEdit
documentation: ug
---


# Hiding Prompt Characters

When the `HidePromptOnLeave` property is set to true, prompt characters are ignored when control loses focus. Again, the prompt characters are restored when the control is focused.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.HidePromptOnLeave = true;
{% endhighlight %}
{% endtabs %}

![](SfMaskedEditImages/Hideprompt.png)

This demo can be downloaded from this [link](http://www.syncfusion.com/downloads/support/directtrac/general/ze/HidingPrompt-109551610.zip).
