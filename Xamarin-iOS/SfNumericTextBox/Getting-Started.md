---
layout: post
title: Getting Started with Syncfusion® SfNumericTextBox control for iOS.
description: A quick tour to initial users on Syncfusion® numeric textbox control and customization features available in Xamarin.iOS platform.
platform: xamarin.ios
control: SfNumericTextBox
documentation: ug
---

# Getting Started with Xamarin.iOS SfNumericTextBox

This section explains the steps to configure a numeric textbox control in a real-time scenario and also provides a walk-through on some of the customization features available in the numeric textbox control.
                        
## Reference Essential Studio<sup>®</sup> Components in your Solution

After installing Essential Studio<sup>®</sup> for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio{version number}\lib

N> Assemblies are available in unzipped package location in Mac.

Add the following assembly reference to the iOS unified project:

iOS-unifed\Syncfusion.SfNumericTextBox.iOS.dll

## Add SfNumericTextBox

* Add the namespace for the added assemblies:

{% capture codesnippet1 %}

{% highlight c# %}

[C#]

using Syncfusion.SfNumericTextBox.iOS; 

{% endhighlight %}

{% endcapture %}

{{ codesnippet1 | UnOrderList_Indent_Level_1 }} 

* Now add the SfNumericTextBox control with a required optimal name by using the included namespace.

{% capture codesnippet2 %}

{% highlight c# %}

[C#]

SfNumericTextBox numericTextBox = new SfNumericTextBox()
{
	Frame = new CGRect(10, 50, 350, 40),
};

this.Add(numericTextBox); 

{% endhighlight %}

{% endcapture %}

{{ codesnippet2 | UnOrderList_Indent_Level_1 }} 

## Enable Parsing Mode

SfNumericTextBox provides an option to display the value in double or decimal. The following code shows the Decimal parsing mode which can be set through the `ParserMode` property:

{% highlight c# %}

[C#]

numericTextBox.ParserMode = SFNumericTextBoxParsers.Decimal;
	
{% endhighlight %}

## Configuring properties

Format string, value, and maximum number of decimal digits can be customized in SfNumericTextBox as shown below:

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

![Display the SfNumericTextBox with customization features](images/NumericTextBox-iOS.png)

You can find the complete getting started sample from [this](https://github.com/SyncfusionExamples/Getting-Started-of-SfNumericTextBox-Xamarin-iOS) link.