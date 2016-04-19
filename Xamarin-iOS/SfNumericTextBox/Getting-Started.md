---
layout: post
title: Getting Started with Syncfusion NumericTextBox control for Xamarin.iOS.
description:  A quick tour to initial users on Syncfusion numerictextbox control for Xamarin.iOS platform 
platform: Xamarin.iOS.
control: NumericTextBox
documentation: ug
---

# Getting Started

This section explains you the steps to configure a NumericTextBox control in a real-time scenario and also provides a walk-through on some of the customization features available in NumericTextBox control.

![](images/NumericTextBox-iOS.png) 

## Creating your first NumericTextBox in Xamarin.iOS                                   

### Reference Essential Studio Components in your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:
{Syncfusion Installed location}\Essential Studio{version number}\lib

N> Assemblies are available in unzipped package location in Mac

and below assembly reference to the iOS unified project.
ios-unifed\Syncfusion.SfNumericTextBox.iOS.dll

### Initializing NumericTextBox

* Adding reference to NumericTextBox.

{% highlight c# %}

	Using Syncfusion.SfNumericTextBox.iOS; 

{% endhighlight %}

* Create an instance for NumericTextBox control and adding to application.

{% highlight c# %}

	SfNumericTextBox SfNumericTextBox =new SfNumericTextBox();
	SetContentView(SfNumericTextBox); 

{% endhighlight %}

### Add Parsing Mode

Value of the NumericTextBox gets parsed based on the ParsingMode property. ParsingMode is of type Parsers, that is, enum of Double and Decimal.

{% highlight c# %}

	sfNumericTextBox.ParsingMode=Parsers.Decimal;
	
{% endhighlight %}

### Configure the properties for NumericTextBox.

{% highlight c# %}

	sfNumericTextBox.Value=1000;
	sfNumericTextBox.Watermark="Principal Amount";
	sfNumericTextBox.MaximumNumberDecimalDigits=2;
	sfNumericTextBox.FormatString="c";
	sfNumericTextBox.AllowNull= true;
	sfNumericTextBox.CultureInfo= new NSLocale("en_us");
	sfNumericTextBox.PercentDisplayMode = SFNumericTextBoxPercentDisplayMode.Compute;

{% endhighlight %}

