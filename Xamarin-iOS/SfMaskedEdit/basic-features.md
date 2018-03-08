---
layout: post
title: Basic features in SfMaskedEdit for Xamarin.iOS platform
description: Learn how to customize the basic features of SfMaskedEdit
platform: Xamarin.iOS
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---

# Basic Features

## Setting Value

The SfMaskedEdit control displays the value that can be set using the `Value` property:

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.Mask = "00/00/0000";
maskedEdit.Value = @"14/11/2014";
{% endhighlight %}
{% endtabs %}

![](SfMaskedEditImages/settingValue.png)

## Setting Prompt Character

Displays prompt character for the absence of your input in Mask and its default value is ‘_’. You can set the custom prompt character using `PromptChar` property.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.Mask = "00/00/0000";
maskedEdit.PromptChar = '*';
{% endhighlight %}
{% endtabs %}

![](SfMaskedEditImages/settingPrompt.png)

## Setting Placeholder

The placeholder will prompt you with instructions or important information when it is not on focus and any valid characters are not entered. 
The placeholder text and its appearance can be modified using `Placeholder` and properties respectively.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.Mask = "00/00/0000";
maskedEdit.Placeholder = "Type here..";
UIStringAttributes placeholderAttributes = new UIStringAttributes();
//Setting placeholder color.
placeholderAttributes.ForegroundColor = UIColor.LightGray;

//Setting placeholder font size.
placeholderAttributes.Font = UIFont.SystemFontOfSize(20);

//Setting placeholder font descriptor.
UIFontDescriptor fontDescriptor = placeholderAttributes.Font.FontDescriptor;
placeholderAttributes.Font = UIFont.FromDescriptor(fontDescriptor.CreateWithTraits(UIFontDescriptorSymbolicTraits.Bold), 0);

//Setting placeholder font family.
placeholderAttributes.Font = UIFont.FromName("Arial", placeholderAttributes.Font.PointSize);
maskedEdit.AttributedPlaceholder = new NSAttributedString(maskedEdit.Placeholder, placeholderAttributes);
{% endhighlight %}
{% endtabs %}

![](SfMaskedEditImages/Settingplaceholder.png)

You can find the complete basic features sample from this [link](http://files2.syncfusion.com/Xamarin.iOS/Samples/MaskedEdit_BasicFeatures.zip).
