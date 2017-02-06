---
layout : post
title : Getting Started with Syncfusion NumericUpDown Control for Xamarin.iOS
description : A quick tour to initial users on Syncfusion NumericUpDown control for Xamarin.iOS platform 
platform : Xamarin.iOS
control : NumericUpDown 
documentation : ug
---

# Getting Started

This section provides overview for working with Essential NumericUpDown for Xamarin.iOS. You can walk through the entire process of creating a SfNumericUpDown.

## Referencing Essential Studio Components in Your Solution	

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio{version number}\lib

N> Assemblies are available in unzipped package location in Mac

and below assembly reference to the iOS unified project.

iOS-unifed\Syncfusion.SfNumericUpDown.iOS.dll

## Add SfNumericUpDown

The SfNumericUpDown control configured entirely in C# code. The following steps explain on how to create a SfNumericUpDown and configure its elements,

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight c# %}

	Using Syncfusion.SfNumericUpDown.iOS; 

{% endhighlight %}

{% endtabs %}

* Now add the SfNumericUpDown control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight c# %}

SFNumericUpDown numericupdown=new SFNumericUpDown();
this.AddSubview(numericupdown);

{% endhighlight %}

{% endtabs %}

## Set Value

The SfNumericUpDown control display value can be set using `Value` property. 

{% tabs %}

{% highlight C# %}

numericupdown.Value= 5;

{% endhighlight %}

{% endtabs %}

## Enable Parsing Mode

SfNumericTextBox provides option to display the value in double or decimal. Following code shows the Decimal parsing mode which can be set through `ParsingMode` property.

{% tabs %}

{% highlight c# %}

numericupdown.ParsingMode=SFNumericUpDownParsingMode.Decimal;
	
{% endhighlight %}

{% endtabs %}

## Add Format String

The `FormatString` property determines the format specifier by which the display text has to be formatted. 

It has three types,

* c - Display the value with currency notation.
* n – Display the value in number format.
* p – Display the value in Percentage.

N> The control displays the formatted text on lost focus. Default Value of `FormatString` is "n".

{% tabs %}

{% highlight C# %}

numericupdown.FormatString= @“c”;

{% endhighlight %}

{% endtabs %}

![](images/gettingstarted.png)



