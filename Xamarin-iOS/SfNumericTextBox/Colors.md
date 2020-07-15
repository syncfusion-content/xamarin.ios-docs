---
layout: post
title: Colors in Syncfusion NumericTextBox control for Xamarin.iOS
description: Learn what are the color properties to customize the appearence of NumericTextBox in Xamarin.iOS platform.
platform: Xamarin.iOS
control: NumericTextBox
documentation: ug
---
# Colors in NumericTextBox

SfNumericTextBox is used to set custom background, text, and border colors through the following properties:

* `TextColor` - Sets the color of NumericTextBox's value

* `BackgroundColor` - Sets the background color of NumericTextBox.

* `BorderColor` - Sets the border custom color of NumericTextBox

* `WatermarkColor` - Sets the watermark custom color of NumericTextBox's watermark Text.

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

![Display the NumericTextBox with TextColor](images/textcolor.png)

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

![Display the NumericTextBox with BackgroundColor](images/backgroundcolor.png)

## BorderColor

The following code sample demonstrates how to set the BorderColor color:

{% highlight c# %}

[C#]

SfNumericTextBox numericTextBox = new SfNumericTextBox()
{
	BorderColor = UIColor.Blue
};

{% endhighlight %}

![Display the NumericTextBox with BorderColor](images/bordercolor.png)

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

![Display the NumericTextBox with WatermarkColor](images/watermarkcolor.png)
