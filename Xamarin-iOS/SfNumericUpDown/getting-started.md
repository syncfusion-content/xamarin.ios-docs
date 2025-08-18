---
layout: post
title: Getting Started with Syncfusion® SfNumericUpDown Control for Xamarin.iOS
description: A quick tour to initial users on Syncfusion® SfNumericUpDown control and customization features available in Xamarin.iOS platform
platform: xamarin.ios
control: SfNumericUpDown
documentation: ug
---

# Getting Started with SfNumericUpDown

This section provides an overview for working with Essential<sup>®</sup> SfNumericUpDown for Xamarin.iOS. You can walk through the entire process of creating a SfNumericUpDown.

## Referencing Essential Studio<sup>®</sup> Components in Your Solution	

After installing Essential Studio<sup>®</sup> for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio{version number}\lib

N> Assemblies are available in unzipped package location in Mac

and below assembly reference to the iOS unified project.

iOS-unifed\Syncfusion.SfNumericUpDown.iOS.dll

## Add SfNumericUpDown

The SfNumericUpDown control is configured entirely in C# code. The following steps explain how to create a SfNumericUpDown and configure its elements:

* Add the namespace for the added assemblies.

{% capture codesnippet1 %}

{% highlight c# %}

using Syncfusion.SfNumericUpDown.iOS; 

{% endhighlight %}

{% endcapture %}

{{ codesnippet1 | UnOrderList_Indent_Level_1 }} 

*  Now add the SfNumericUpDown control using the included namespace.

{% capture codesnippet2 %}

{% highlight c# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown()
{
	
	Frame = new CGRect(10, 50, 350, 40),
};

this.Add(numeric);

{% endhighlight %}

{% endcapture %}

{{ codesnippet2 | UnOrderList_Indent_Level_1 }} 

## Set Value

The SfNumericUpDown control's display value can be set using the `Value` property.

{% highlight C# %}

[C#]

numeric.Value = 100;

{% endhighlight %}

![Display the SfNumericUpDown with value](images/gettingstarted.png)

You can find the complete getting started sample from [this](https://github.com/SyncfusionExamples/Getting-Started-SfNumericUpDown-in-Xamarin-iOS) link.