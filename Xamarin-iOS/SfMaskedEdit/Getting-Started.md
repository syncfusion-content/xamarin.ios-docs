---
layout: post
title: Getting Started with Syncfusion SfMaskedEdit control for Xamarin.iOS.
description:  A quick tour to initial users on Syncfusion SfMaskedEdit control for Xamarin.iOS platform 
platform: Xamarin.iOS.
control: SfMaskedEdit
documentation: ug
---

# Getting Started

This section explains you the steps to configure a SfMaskedEdit control in a real-time scenario and also provides a walk-through on some of the customization features available in SfMaskedEdit control.
                        
## Reference Essential Studio Components in your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

**{Syncfusion Installed location}\Essential Studio{version number}\lib**

Example: C:\Program Files (x86)\Syncfusion\Essential Studio\16.1.0.24\Xamarin\lib

You have to add the following assembly reference to the iOS unified project.

**iOS-unifed\ Syncfusion.SfMaskedEdit.iOS.dll**


## Add SfMaskedEdit

**Add reference to SfMaskedEdit**

{% tabs %}

{% highlight c# %}

	using Syncfusion.iOS.MaskedEdit;

{% endhighlight %}

{% endtabs %}

**Create an instance of SfMaskedEdit**

{% tabs %}

{% highlight c# %}

SfMaskedEdit maskedEdit=new SfMaskedEdit();
this.AddSubview(maskedEdit);

{% endhighlight %}

{% endtabs %}

## Masking the input

To mask the input, set the MaskType and Mask properties as follows:

{% tabs %}

{% highlight c# %}

SfMaskedEdit maskededit = new SfMaskedEdit(); 
maskededit.MaskType = MaskType.Text; 
maskedEdit.Mask = "00/00/0000";
	
{% endhighlight %}

{% endtabs %}

This mask expression allows only numeric inputs in the places of 0.

## Setting Value

Set the Value for the control as follows,

{% tabs %}

{% highlight c# %}

SfMaskedEdit maskededit = new SfMaskedEdit(); 
maskededit.MaskType=MaskType.Text;
maskedEdit.Mask="00/00/0000";
maskedEdit.Value="14/11/2014";
	
{% endhighlight %}

{% endtabs %}
 
## MaskType

Each MaskType has different set of mask elements that are combined to form a mask expression. Based on the complexity and usage, mask types are classified as:

1.	Text
2.	Reg-Ex

## Text

Expressions that are generated with letters, digits and special characters are come under this group. This is mainly used for fixed length inputs. For example: Phone number, PAN number.

**Text Mask elements**
<table>
<tr>
<th>Elements</th>
<th>Description</th>
</tr>
<tr>
<td>A</td>
<td>Alphanumeric, required.</td>
</tr>
<tr>
<td>a</td>
<td>Alphanumeric, optional.</td>
</tr>
<tr>
<td>L</td>
<td>Letter, required. Restricts input to the ASCII letters a-z and A-Z. </td>
</tr>
<tr>
<td>l</td>
<td>Letter, optional. Restricts input to the ASCII letters a-z and A-Z. </td>
</tr>
<tr>
<td>0</td>
<td>Digit, required. This element accepts any single digit between 0 and 9</td>
</tr>
<tr>
<td>9</td>
<td>Digit or space, optional. </td>
</tr>
<tr>
<td>#</td>
<td>Digit or space, optional. Plus (+) and minus (-) signs are allowed.  </td>
</tr>
<tr>
<td>C</td>
<td>Character, optional. </td>
</tr>
<tr>
<td>\</td>
<td>Escapes a mask character, turning it into a literal. "\" is the escape sequence for a backslash.  </td>
</tr>
<tr>
<td>Any other characters</td>
<td>Considered as literals. Literals always occupy a static position in the mask at run time, and cannot be moved or deleted. </td>
</tr>
</table>
{% tabs %}

{% highlight c# %}

SfMaskedEdit maskedEdit=new SfMaskedEdit();
maskedEdit.Mask = "+1(000)000000";
maskedEdit.MaskType = MaskType.Text;
	
{% endhighlight %}

{% endtabs %}

This mask expression allows only numeric inputs in the places of 0.

## Regex

The expressions that are generated with regular expressions come under this group, preferable for variable length inputs and input in range. For example: Hexadecimal values [0-9A-C].
The regular expressions provide significant advantages when creating masks as compared with other masked modes. 

**Advantages:**
1)	Allows to enter value of indeterminate length.
2)	Restricts with specific pattern. Example email, password etc.
3)	Restricts to enter specific range at specific position.

**Regex Mask Elements**
<table>
<tr>
<th>Elements</th>
<th>Description</th>
</tr>
<tr>
<td>\w</td>
<td>Accepts any alphabet, number, including the _(Underscore) character.</td>
</tr>
<tr>
<td>\d</td>
<td>Accepts any digit.</td>
</tr>
<tr>
<td>{n}l</td>
<td>Accepts the input for 'n' number of times</td>
</tr>
<tr>
<td>{n,m}</td>
<td>Accepts the input for 'n' minimum number of times and 'm' maximum number of times</td>
</tr>
<tr>
<td>?</td>
<td>Optional input.</td>
</tr>
<tr>
<td>+</td>
<td>Accepts the input for one or more times.</td>
</tr>
<tr>
<td>*</td>
<td>Accepts the input for zero or more times.</td>
</tr>
<tr>
<td>[aeiou]</td>
<td>Accepts any single character included in the specified set of characters. </td>
</tr>
<tr>
<td>[0-9a-fA-F]</td>
<td>Accepts any character between[A-F]/[a-f] and numbers between [0-9].</td>
</tr>
</table>

{% tabs %}

{% highlight c# %}

SfMaskedEdit mask = new SfMaskedEdit();
mask.Mask = @"+(1)(\d{3})\d{5}";
mask.MaskType = MaskType.RegEx;

{% endhighlight %}

{% endtabs %}

This mask expression’\d{3}’ and’ \d{5}’ allows only numeric, where {n} is the count that the input should be accepted.

## Setting Value

The SfMaskedEdit control display value can be set using Value property,

{% tabs %}

{% highlight c# %}

SfMaskedEdit maskededit = new SfMaskedEdit(); 	
maskededit.MaskType=MaskType.Text;
maskedEdit.Mask="00/00/0000";	
maskedEdit.Value="14/11/2014";

{% endhighlight %}

{% endtabs %}

## Localization
The special symbols like a currency symbol, date separator, decimal separator etc., can be localized to any specific culture with 'Culture' property.

<table>
<tr>
<th>Elements</th>
<th>Description</th>
</tr>
<tr>
<td>.</td>
<td>Decimal separator determined by current culture.</td>
</tr>
<tr>
<td>,</td>
<td>Group separator determined by current culture.</td>
</tr>
<tr>
<td>/</td>
<td>Date separator determined by current culture. </td>
</tr>
<tr>
<td>:</td>
<td>Time separator determined by current culture.</td>
</tr>
<tr>
<td>$</td>
<td>Currency symbol determined by current culture.</td>
</tr>
</table>

{% tabs %}
{% highlight c# %}

SfMaskedEdit mask = new SfMaskedEdit();
mask.Mask = "$ 0,000.00";
mask.MaskType = MaskType.Text;
mask.Culture= new CultureInfo("fr-FR");

{% endhighlight %}
{% endtabs %}

## ValidationMode

Input validation happens based on the value of the ‘ValidationMode’ property. The enum values of this property are

•	KeyPress
•	LostFocus

The default value for validation mode is ‘LostFocus’.


{% tabs %}

{% highlight c# %}

SfMaskedEdit maskEdit = new SfMaskedEdit(); 
maskEdit.Mask = "000000";
maskEdit.MaskType = MaskType.Text;
maskEdit.ValidationMode = InputValidationMode.KeyPress;

{% endhighlight %}

{% endtabs %}

When the ValidationMode is LostFocus, the validation take place when the control get lost its focus. For KeyPress, the validation triggers for each key press.

### Prompt Character

Displays prompt character for the absence of user input in Mask and its default value is ‘_’

{% tabs %}

{% highlight c# %}

SfMaskedEdit maskededit = new SfMaskedEdit(); 
maskededit.Mask = "000000";
maskededit.MaskType = MaskType.Text;
maskededit.PromptChar = '*'; 

{% endhighlight %}

{% endtabs %}