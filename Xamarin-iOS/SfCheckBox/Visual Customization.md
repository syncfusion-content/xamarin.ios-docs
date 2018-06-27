---
layout: post
title: Visual customization in SfCheckBox for Xamarin.iOS platform
description: Learn how to customize the basic features of SfCheckBox
platform: Xamarin.iOS
control: SfCheckBox
documentation: ug 
keywords: button, SfCheckBox, CheckBox

---

# Visual Customization

## Customizing shape
The check box shape can be customized using `CornerRadius` property. This property specifies uniform radius value for every corner of the check box.

{% tabs %}
{% highlight c# %}
SfCheckBox checkBox = new SfCheckBox();
checkBox.SetTitle("CheckBox", UIControlState.Normal);
checkBox.IsChecked = true;
checkBox.CornerRadius = 5.0f;
{% endhighlight %}
{% endtabs %}

![](Images/Radius.png)

## Customizing state color
The default state colors can be customized using `CheckedColor` and `UncheckedColor `properties. The checked/indeterminate state color is updated to `CheckedColor` property value when the state is changed to the checked/indeterminate and unchecked state color is updated to `UncheckedColor` property value when the state is changed to unchecked. 
{% tabs %}
{% highlight c# %}
SfCheckBox check = new SfCheckBox();
check.SetTitle("CheckBox", UIControlState.Normal);
check.IsChecked = true;
check.CheckedColor = UIColor.Green;
SfCheckBox uncheck = new SfCheckBox();
uncheck.SetTitle("CheckBox",UIControlState.Normal);
uncheck.UncheckedColor = UIColor.FromRGB(238, 130, 238);
SfCheckBox indeterminate = new SfCheckBox();
indeterminate.IsChecked = null;
indeterminate.IsThreeState = true;
indeterminate.SetTitle("CheckBox", UIControlState.Normal);
indeterminate.CheckedColor = UIColor.Purple;
{% endhighlight %}
{% endtabs %}

![](Images/StateColor.png)

## Setting appearance of caption text
You can customize the display text appearance of `SfCheckBox` control using the following properties:

* `SetTitleColor`: Changes the color of the text.
* `HorizontalAlignment`: Changes the horizontal alignment of the caption text.
* `Font`:Changes the font family of the text and sets font attributes(bold/italic/none) of the text and also sets font size of the caption text.

{% tabs %}
{% highlight c# %}
SfCheckBox caption = new SfCheckBox();
caption.IsChecked = true;
caption.SetTitle("CheckBox", UIControlState.Normal);
caption.SetTitleColor(UIColor.FromRGB(238, 130, 238), UIControlState.Normal);
caption.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
caption.Font = UIFont.FromName("Arial", 20);
caption.Font = UIFont.SystemFontOfSize(20);
UIFontDescriptor fontDescriptor = caption.Font.FontDescriptor;
caption.Font = UIFont.FromDescriptor(fontDescriptor.CreateWithTraits(UIFontDescriptorSymbolicTraits.Bold), 0);
{% endhighlight %}
{% endtabs %}

![](Images/CaptionAppearance.png)

This demo can be downloaded from this [link](http://files2.syncfusion.com/Xamarin.Android/Samples/MaskedEdit_VisualCustomize.zip).