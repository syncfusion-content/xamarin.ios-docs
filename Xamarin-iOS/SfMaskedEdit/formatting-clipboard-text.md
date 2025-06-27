---
layout: post
title: Formatting clipboard text of Syncfusion® SfMaskedEdit Xamarin.iOS
description: Learn how to configure clipboard text formatting during cut and copy operations in Syncfusion® SfMaskedEdit for Xamarin.iOS using CutCopyMaskFormat property.
platform: xamarin.ios
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---

# Formatting clipboard text

SfMaskedEdit allows you to format the clipboard text in a mask scenario (when the Mask property is set). When you perform cut or copy operations, the clipboard text will be formatted with your input characters and the literals defined in the mask. You can modify this behavior and configure the clipboard to hold characters with or without prompt and literals by setting the CutCopyMaskFormat property. The clipboard text can be formatted using any of the following enum values:

* ExcludePromptAndLiterals
* IncludePrompt
* IncludeLiterals
* IncludePromptAndLiterals

## ExcludePromptAndLiterals

Clipboard text will contain only the typed characters, the prompt characters and literals are excluded.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.Mask = "00/00/0000";
maskedEdit.CutCopyMaskFormat = MaskFormat.ExcludePromptAndLiterals;
{% endhighlight %}
{% endtabs %}

## IncludePrompt

Clipboard text contains the typed characters and prompt characters, literals are excluded.
	
{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.Mask = "00/00/0000";
maskedEdit.CutCopyMaskFormat = MaskFormat.IncludePrompt;
{% endhighlight %}
{% endtabs %}

## IncludeLiterals

Clipboard text contains the typed characters and literals, prompt characters are excluded.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.Mask = "00/00/0000";
maskedEdit.CutCopyMaskFormat = MaskFormat.IncludeLiterals;
{% endhighlight %}
{% endtabs %}

## IncludePromptAndLiterals

Clipboard text contains typed characters, prompt characters, and literals.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.Mask = "00/00/0000";
maskedEdit.CutCopyMaskFormat = MaskFormat.IncludePromptAndLiterals;
{% endhighlight %}
{% endtabs %}
