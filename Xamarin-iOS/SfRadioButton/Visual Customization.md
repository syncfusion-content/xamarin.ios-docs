---
layout: post
title: Visual customization in SfRadioButton for Xamarin.iOS platform
description: Learn how to customize the basic features of SfRadioButton
platform: Xamarin.iOS
control: SfRadioButton
documentation: ug 
keywords: button, SfRadioButton, RadioButton

---


# Visual Customization

## Customizing state color
The default state colors can be customized using `CheckedColor` and `UncheckedColor `properties. The checked state color is updated to `CheckedColor` property value when the state is changed to the checked and unchecked state color is updated to `UncheckedColor` property value when the state is changed to unchecked.

{% tabs %}
{% highlight c# %}
SfRadioGroup radioGroup = new SfRadioGroup();
SfRadioButton check = new SfRadioButton();
check.SetTitle("RadioButton",UIControlState.Normal);
check.IsChecked = true;
check.CheckedColor = UIColor.Green;
SfRadioButton uncheck = new SfRadioButton();
uncheck.SetTitle("RadioButton", UIControlState.Normal);
uncheck.UncheckedColor = UIColor.FromRGB(238, 130, 238);
radioGroup.AddArrangedSubview(check);
radioGroup.AddArrangedSubview(uncheck);
{% endhighlight %}
{% endtabs %}

![](Images/StateColor.png)

## Setting appearance of caption text

You can customize the display text appearance of `SfRadioButton` control using the following properties:

* `SetTitleColor`: Changes the color of the text.
* `HorizontalAlignment`: Changes the horizontal alignment of the caption text.
* `Font`:Changes the font family of the text and sets font attributes(bold/italic/none) of the text and also sets font size of the caption text.

{% tabs %}
{% highlight c# %}
SfRadioButton radioButton = new SfRadioButton();
radioButton.SetTitle("RadioButton", UIControlState.Normal);
radioButton.IsChecked = true;
radioButton.SetTitleColor(UIColor.FromRGB(238, 130, 238), UIControlState.Normal);
radioButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
radioButton.Font = UIFont.FromName("Arial", 20);
radioButton.Font = UIFont.SystemFontOfSize(20);
UIFontDescriptor fontDescriptor = radioButton.Font.FontDescriptor;
radioButton.Font = UIFont.FromDescriptor(fontDescriptor.CreateWithTraits(UIFontDescriptorSymbolicTraits.Bold), 0);
{% endhighlight %}
{% endtabs %}

![](Images/CaptionAppereance.png)

This demo can be downloaded from this [link](http://files2.syncfusion.com/Xamarin.Android/Samples/MaskedEdit_VisualCustomize.zip).
