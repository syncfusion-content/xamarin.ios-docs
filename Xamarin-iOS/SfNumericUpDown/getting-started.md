---
layout : post
title : Getting Started with Syncfusion NumericUpDown Control for Xamarin.iOS
description : A quick tour to initial users on Syncfusion NumericUpDown control for Xamarin.iOS platform 
platform : Xamarin.iOS
control : NumericUpDown 
documentation : ug
---

# Getting Started

This section provides overview for working with Essential NumericUpDown for Xamarin.iOS. You can walk through the entire process of creating a NumericUpDown.

![](images/gettingstarted.png)

## Create your first NumericUpDown control in Xamarin.iOS

## Referencing Essential Studio Components in Your Solution	

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:
{Syncfusion Installed location}\Essential Studio{version number}\lib

N> Assemblies are available in unzipped package location in Mac

and below assembly reference to the iOS unified project.
ios-unifed\Syncfusion.SfNumericUpDown.iOS.dll

## Initializing NumericUpDown

The NumericUpDown control configured entirely in C# code or by using XAML markup. The following steps explain on how to create a NumericUpDown and configure its elements,

* Adding reference to NumericUpDown.

{% highlight c# %}

	Using Syncfusion.SfNumericUpDown.iOS; 

{% endhighlight %}


* Create an instance of NumericUpDown.

{% highlight c# %}

	SfNumericUpDown numericupdown=new SfNumericUpDown(this);
	SetContentView(numericupdown);

{% endhighlight %}

## Setting Value

The NumericUpDown control display value can be set using `Value` property. 

{% highlight C# %}

	numericupdown.Value= 5;

{% endhighlight %}

## Enable Parsing Mode

The value of the NumericUpDown can be parsed based on the `ParsingMode` property. 

N> The `ParsingMode` is of type Parsers containing enum values of Double and Decimal.

{% highlight c# %}

	numericupdown.ParsingMode=Parsers.Decimal;
	
{% endhighlight %}

## Add Format String

The `FormatString` property determines the format specifier by which the display text has to be formatted. 

It has three types,

* c - Display the value with currency notation.
* n – Display the value in number format.
* p – Display the value in Percentage.

N> The control displays the formatted text on lost focus. Default Value of `FormatString` is "n".

{% highlight C# %}

	numericupdown.FormatString= “c”;

{% endhighlight %}





