---
layout: post
title: Getting Started with Syncfusion NumericTextBox control for iOS.
description: A quick tour to initial users on Syncfusion numerictextbox control and customization features available in Xamarin.iOS platform.
platform: Xamarin.iOS
control: NumericTextBox
documentation: ug
---

# Getting Started with Xamarin.iOS NumericTextBox

This section explains you the steps to configure a NumericTextBox control in a real-time scenario and also provides a walk-through on some of the customization features available in NumericTextBox control.
                        
## Reference Essential Studio Components in your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio{version number}\lib

N> Assemblies are available in unzipped package location in Mac

and below assembly reference to the iOS unified project.

iOS-unifed\Syncfusion.SfNumericTextBox.iOS.dll

## Add SfNumericTextBox

* Adding namespace for the added assemblies. 

{% highlight c# %}

[C#]

using Syncfusion.SfNumericTextBox.iOS; 

{% endhighlight %}

* Now add the SfNumericTextBox control with a required optimal name by using the included namespace.

{% highlight c# %}

[C#]

SfNumericTextBox numericTextBox = new SfNumericTextBox()
{
	Frame = new CGRect(10, 50, 350, 40),
};

this.Add(numericTextBox); 

{% endhighlight %}

## Enable Parsing Mode

SfNumericTextBox provides option to display the value in double or decimal. Following code shows the Decimal parsing mode which can be set through `ParserMode` property.

{% highlight c# %}

[C#]

numericTextBox.ParserMode = SFNumericTextBoxParsers.Decimal;
	
{% endhighlight %}

## Configuring properties

Format string, value and maximum number of decimal digits can be customized in SfNumericTextBox as below.

{% highlight c# %}

[C#]

SfNumericTextBox numericTextBox = new SfNumericTextBox()
{
	Value = 1000,
	Watermark = "Principal Amount",
	MaximumNumberDecimalDigits = 2,
	FormatString = "c",
	AllowNull = true,
	CultureInfo = new NSLocale("en_us"),
	PercentDisplayMode = SFNumericTextBoxPercentDisplayMode.Compute
};

{% endhighlight %}

![Display the NumericTextBox with customization features](images/NumericTextBox-iOS.png)

You can find the complete getting started sample from [this](https://github.com/SyncfusionExamples/Getting-Started-of-SfNumericTextBox-Xamarin-iOS) link.