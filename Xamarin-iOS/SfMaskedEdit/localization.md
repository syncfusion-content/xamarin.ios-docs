---
layout: post
title: Getting Started with Syncfusion SfMaskedEdit control for Xamarin.IOS
description: A quick tour to initial users on Syncfusion SfMaskedEdit control for Xamarin.IOS platform 
platform: Xamarin.IOS
control: SfMaskedEdit
documentation: ug
---

# Localization

The special symbols such as currency symbol, date separator, decimal separator etc., can be localized to any specific culture using the **Culture** property.

<table>
<tr>
<td>
{{'**Characters**'| markdownify }}
</td>
<td>
{{'**Description**'| markdownify }}
</td>
</tr>
<tr>
<td>
.
</td>
<td>
Decimal separator determined by current culture.
</td>
</tr>
<tr>
<td>
,
</td>
<td>
Group separator determined by current culture.
</td>
</tr>
<tr>
<td>
/
</td>
<td>
Date separator determined by current culture.
</td>
</tr>
<tr>
<td>
:
</td>
<td>
Time separator determined by current culture.
</td>
</tr>
<tr>
<td>
$
</td>
<td>
Currency symbol determined by current culture.
</td>
</tr>
</table>

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.Mask = "$ 0,000.00";
maskedEdit.Culture = new CultureInfo("fr-FR");
{% endhighlight %}
{% endtabs %}

Now the ‘$’ will be localized to ‘€’;‘.’ will be localized to ‘,’ and ‘,’ will be localized to ‘ ‘(single white space).

![](SfMaskedEditImages/Localisation.png)

You can find the runnable localization sample from this [link](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Localization104850867.zip).
