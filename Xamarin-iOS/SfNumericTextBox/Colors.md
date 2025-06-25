---
layout: post
title: Colors in Syncfusion® SfNumericTextBox control for Xamarin.iOS
description: Learn what are the color properties to customize the appearance of SfNumericTextBox in Xamarin.iOS platform.
platform: xamarin.ios
control: SfNumericTextBox
documentation: ug
---
# Color Customization in SfNumericTextBox

SfNumericTextBox allows you to set custom background, text, and border colors through the following properties:

* `TextColor` - Sets the color of the numeric textbox's value.

* `BackgroundColor` - Sets the background color of the numeric textbox.

* `BorderColor` - Sets the border color of the numeric textbox.

* `WatermarkColor` - Sets the watermark color of the numeric textbox's watermark text.

## TextColor

The following code sample demonstrates how to set the TextColor:

{% highlight c# %}

[C#]

SfNumericTextBox numericTextBox = new SfNumericTextBox()
{
	TextColor = Color.Green,
	Value = 123
};

{% endhighlight %}

![Display the SfNumericTextBox with TextColor](images/textcolor.png)

## BackgroundColor

The following code sample demonstrates how to set the BackgroundColor:

{% highlight c# %}

[C#]

SfNumericTextBox numericTextBox = new SfNumericTextBox()
{
	BackgroundColor = Color.Red,
	TextColor = Color.White
};

{% endhighlight %}

![Display the SfNumericTextBox with BackgroundColor](images/backgroundcolor.png)

## BorderColor

The following code sample demonstrates how to set the BorderColor:

{% highlight c# %}

[C#]

SfNumericTextBox numericTextBox = new SfNumericTextBox()
{
	BorderColor = UIColor.Blue
};

{% endhighlight %}

![Display the SfNumericTextBox with BorderColor](images/bordercolor.png)

## WatermarkColor

The following code sample demonstrates how to set the WatermarkColor:

{% highlight c# %}

[C#]

SfNumericTextBox numericTextBox = new SfNumericTextBox()
{
	Watermark = (NSString)"NumericTextBox",
	WatermarkColor = UIColor.Blue,
	AllowNull=true
};

{% endhighlight %}

![Display the SfNumericTextBox with WatermarkColor](images/watermarkcolor.png)
