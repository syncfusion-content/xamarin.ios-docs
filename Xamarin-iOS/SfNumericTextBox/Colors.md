---
layout: post
title: Colors in Syncfusion SfNumericTextBox control for Xamarin.iOS
description: Learn what are the color properties to customize the appearence of SfNumericTextBox in Xamarin.iOS platform.
platform: Xamarin.iOS
control: SfNumericTextBox
documentation: ug
---
# Color Customization in SfNumericTextBox

SfNumericTextBox is used to set custom background, text, and border colors through the following properties:

* `TextColor` - Sets the color of numeric textBox's value

* `BackgroundColor` - Sets the background color of numeric textBox.

* `BorderColor` - Sets the border custom color of numeric textBox

* `WatermarkColor` - Sets the watermark custom color of numeric textBox's watermark Text.

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

The following code sample demonstrates how to set the BorderColor color:

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
