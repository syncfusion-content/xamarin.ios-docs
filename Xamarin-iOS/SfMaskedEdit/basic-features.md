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

![SfMaskedEdit setting value](SfMaskedEditImages/settingValue.png)

## Setting Prompt Character

The prompt character is displayed for the absence of your input in the mask, and its default value is '_'. You can set a custom prompt character using the `PromptChar` property.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.Mask = "00/00/0000";
maskedEdit.PromptChar = '*';
{% endhighlight %}
{% endtabs %}

![SfMaskedEdit setting prompt character](SfMaskedEditImages/settingPrompt.png)

## Setting Placeholder

The placeholder will prompt you with instructions or important information when the control is not in focus and no valid characters are entered. The placeholder text and its appearance can be modified using the `Placeholder` and `AttributedPlaceholder` properties respectively.
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

![SfMaskedEdit setting placeholder](SfMaskedEditImages/Settingplaceholder.png)

You can find the complete basic features sample from this [link](http://files2.syncfusion.com/Xamarin.iOS/Samples/MaskedEdit_BasicFeatures.zip).
