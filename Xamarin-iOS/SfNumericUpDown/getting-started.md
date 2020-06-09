---
layout: post
title: Getting Started with Syncfusion NumericUpDown Control for Xamarin.iOS
description: A quick tour to initial users on Syncfusion NumericUpDown control and customization features available in Xamarin.iOS platform 
platform: Xamarin.iOS
control: NumericUpDown 
documentation: ug
---

# Getting Started with SfNumericUpDown

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

{% highlight c# %}

using Syncfusion.SfNumericUpDown.iOS; 

{% endhighlight %}

* Now add the SfNumericUpDown control with a required optimal name by using the included namespace.

{% highlight c# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown()
{
	
	Frame = new CGRect(10, 50, 350, 40),
};

this.Add(numeric);

{% endhighlight %}

## Set Value

The SfNumericUpDown control display value can be set using `Value` property. 

{% highlight C# %}

[C#]

numeric.Value = 100;

{% endhighlight %}

![Display the NumericUpDown with value](images/gettingstarted.png)

You can find the complete getting started sample from [this](https://github.com/SyncfusionExamples/Getting-Started-SfNumericUpDown-in-Xamarin-iOS) link.