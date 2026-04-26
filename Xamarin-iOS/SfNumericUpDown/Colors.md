---
layout: post
title: Colors in Syncfusion® SfNumericUpDown control for Xamarin.iOS
description: Learn what are the color properties to customize the appearance of SfNumericUpDown in Xamarin.iOS platform.
platform: xamarin.ios
control: SfNumericUpDown
documentation: ug
---
# Colors in SfNumericUpDown

SfNumericUpDown is used to set custom background, text, and border colors through the following properties:

* `TextColor` - Sets the color of the SfNumericUpDown's value

* `BackgroundColor` - Sets the background color of the SfNumericUpDown.

* `BorderColor` - Sets the custom border color of the SfNumericUpDown

* `WatermarkColor` - Sets the custom color of the SfNumericUpDown's watermark text.

## TextColor

The following code sample demonstrates how to set the TextColor:

{% highlight c# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown()
{
	
	TextColor = Color.Green,
};

{% endhighlight %}

![Customized text color in SfNumericUpDown](images/textcolor.png)

## BackgroundColor

The following code sample demonstrates how to set the BackgroundColor:

{% highlight c# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown()
{
	
	BackgroundColor = Color.Red,
	TextColor = Color.White,
};

{% endhighlight %}

![Display the SfNumericUpDown with BackgroundColor](images/backgroundcolor.png)

## BorderColor

The following code sample demonstrates how to set the BorderColor:

{% highlight c# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown()
{
	
	BorderColor = UIColor.Blue,
};

{% endhighlight %}

![Display the SfNumericUpDown with BorderColor](images/bordercolor.png)

## WatermarkColor

The following code sample demonstrates how to set the WatermarkColor:

{% highlight c# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown()
{
	Watermark = (NSString)"Enter a Number",
	WatermarkColor = UIColor.Blue,
	AllowNull=true,
};

{% endhighlight %}

![Display the SfNumericUpDown watermark text with a color](images/watermarkcolor.png)
