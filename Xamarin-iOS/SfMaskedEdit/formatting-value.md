---
layout: post
title: Getting Started with Syncfusion SfMaskedEdit control for Xamarin.IOS
description: A quick tour to initial users on Syncfusion SfMaskedEdit control for Xamarin.IOS platform 
platform: Xamarin.IOS
control: SfMaskedEdit
documentation: ug
---

# Formatting Value

SfMaskedEdit allows you to format the characters in the `Value` property in a mask scenario (when the Mask property is set). By default, the Value property holds your input characters, prompt characters and the literals defined in the mask. You can modify this and allow the Value property to hold the characters without prompt and literals by setting the ValueMaskFormat property of the control. The Value in the SfMaskedEdit is formatted by any one of the following formatting enum values:

* ExcludePromptAndLiterals
* IncludePrompt
* IncludeLiterals
* IncludePromptAndLiterals


## ExcludePromptAndLiterals

Value contains only the typed characters, the prompt characters and literals are excluded.

## IncludePrompt

Value contains the typed characters and prompt characters, literals are excluded.

## IncludeLiterals

Value contains the typed characters and literals, prompt characters are excluded.

## IncludePromptAndLiterals

Value contains typed characters, prompt characters, and literals.

{% tabs %}
{% highlight c# %}
UILabel label1, label2, label3, label4;
SfMaskedEdit maskedEdit1 = new SfMaskedEdit();
            maskedEdit1 = new SfMaskedEdit();
            maskedEdit1.MaskType = MaskType.Text;
            maskedEdit1.Mask = "00/00/0000";
            maskedEdit1.ValueMaskFormat = MaskFormat.ExcludePromptAndLiterals;
            maskedEdit1.ValueChanged += MaskedEdit1_ValueChanged;
            label1 = new UILabel();

            SfMaskedEdit maskedEdit2 = new SfMaskedEdit();
            maskedEdit2 = new SfMaskedEdit();
            maskedEdit2.MaskType = MaskType.Text;
            maskedEdit2.Mask = "00/00/0000";
            maskedEdit2.ValueMaskFormat = MaskFormat.IncludeLiterals;
            maskedEdit2.ValueChanged += MaskedEdit2_ValueChanged;
            label2 = new UILabel();

            SfMaskedEdit maskedEdit3 = new SfMaskedEdit();
            maskedEdit3 = new SfMaskedEdit();
            maskedEdit3.MaskType = MaskType.Text;
            maskedEdit3.Mask = "00/00/0000";
            maskedEdit3.ValueMaskFormat = MaskFormat.IncludePrompt;
            maskedEdit3.ValueChanged += MaskedEdit3_ValueChanged;
            label3 = new UILabel();

            SfMaskedEdit maskedEdit4 = new SfMaskedEdit();
            maskedEdit4 = new SfMaskedEdit();
            maskedEdit4.MaskType = MaskType.Text;
            maskedEdit4.Mask = "00/00/0000";
            maskedEdit4.ValueMaskFormat = MaskFormat.IncludePromptAndLiterals;
            maskedEdit4.ValueChanged += MaskedEdit4_ValueChanged;
            label4 = new UILabel(); 
			
private void MaskedEdit1_ValueChanged(object sender, ValueChangedEventArgs e)
        {
            label1.Text = e.Value as string;
        }

        private void MaskedEdit2_ValueChanged(object sender, ValueChangedEventArgs e)
        {
            label2.Text = e.Value as string;
        }

        private void MaskedEdit3_ValueChanged(object sender, ValueChangedEventArgs e)
        {
            label3.Text = e.Value as string;
        }

        private void MaskedEdit4_ValueChanged(object sender, ValueChangedEventArgs e)
        {
            label4.Text = e.Value as string;
        }
{% endhighlight %}
{% endtabs %}

Refer this [link](Events#valuechanged-event) to know more about the `ValueChanged` event of SfMaskedEdit control.

![](SfMaskedEditImages/valueformat.png)

This demo can be downloaded from this [link](http://www.syncfusion.com/downloads/support/directtrac/general/ze/FormattingValue-2100102900.zip).
