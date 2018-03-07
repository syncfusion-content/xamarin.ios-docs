---
layout: post
title: Getting Started with Syncfusion SfMaskedEdit control for Xamarin.IOS
description: A quick tour to initial users on Syncfusion SfMaskedEdit control for Xamarin.IOS platform 
platform: Xamarin.IOS
control: SfMaskedEdit
documentation: ug
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

You can find the complete basic features sample from this [link](http://www.syncfusion.com/downloads/support/directtrac/general/ze/BasicFeatures-59189404.zip).
