---
layout: post
title: Colors in Syncfusion NumericUpDown control for Xamarin.iOS
description: Learn what are the color properties to customize the appearence of NumericUpDown in Xamarin.iOS platform.
platform: Xamarin.iOS
control: NumericUpDown
documentation: ug
---
# Colors in SfNumericUpDown

SfNumericUpDown is used to set custom background, text, and border colors through the following properties:

* `TextColor` - Sets the color of NumericUpDown's value

* `BackgroundColor` - Sets the background color of NumericUpDown.

* `BorderColor` - Sets the border custom color of NumericUpDown

* `WatermarkColor` - Sets the watermark custom color of NumericUpDown's watermark Text.

### TextColor

The following code sample demonstrates how to set the TextColor:

{% highlight c# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown()
{
	
	TextColor = Color.Green,
};

{% endhighlight %}

![Customized text color in NumericUpown](images/textcolor.png)

### BackgroundColor

The following code sample demonstrates how to set the BackgroundColor:

{% highlight c# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown()
{
	
	BackgroundColor = Color.Red,
	TextColor = Color.White,
};

{% endhighlight %}

![Display the NumericUpDown with BackgroundColor](images/backgroundcolor.png)

### BorderColor

The following code sample demonstrates how to set the BorderColor color:

{% highlight c# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown()
{
	
	BorderColor = UIColor.Blue,
};

{% endhighlight %}

![Display the NumericUpDown with BorderColor](images/bordercolor.png)

### WatermarkColor

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

![Display the NumericUpDown watermark text with a color](images/watermarkcolor.png)
