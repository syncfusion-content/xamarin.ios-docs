---
layout: post
title: Appearance in Syncfusion® NumericUpDown control for Xamarin.iOS
description: Learn how to customize spin button position and appearance in Xamarin.iOS NumericUpDown control.
platform: xamarin.ios
control: NumericUpDown
documentation: ug
---

# Spin Button Alignment

The spin button position in the NumericUpDown control can be changed relative to the TextBox based on the `SpinButtonAlignment` property.

There are three built-in modes:

## Right

Spin buttons will be aligned to the right side of the control.

{% highlight C# %}

[C#]

numeric.SpinButtonAlignment = SFNumericUpDownSpinButtonAlignment.Right;

{% endhighlight %}

![Display the NumericUpDown spin button with right alignment](images/spinright.png)

## Left

Spin buttons will be aligned to the left side of the control.

{% highlight C# %}

[C#]

numeric.SpinButtonAlignment = SFNumericUpDownSpinButtonAlignment.Left;

{% endhighlight %}

![Display the NumericUpDown spin button with left alignment](images/spinleft.png)

## Both

Spin buttons will be aligned to both sides of the control.

{% highlight C# %}

[C#]

numeric.SpinButtonAlignment = SFNumericUpDownSpinButtonAlignment.Both;

{% endhighlight %}

![Display the NumericUpDown spin button with both sides alignment](images/spinboth.png)

N> By default, the property value is Right.

## UpDownButtonSettings Customization

You can customize the UpDownButton of the `SfNumericUpDown` control using any of the following methods:

1. View
2. Image
3. FontIconText

### Using View

{% highlight C# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown();

UITextField increment = new UITextField()
{
   
    Text = "Add",
    TextColor = UIColor.Blue,
};

numeric.IncrementButtonSettings = new UpDownButtonSettings()
{
    
    ButtonView = increment,        
};

UITextField decrement = new UITextField()
{
    
    Text = "Reduce",
    TextColor = UIColor.Blue,
};

numeric.DecrementButtonSettings = new UpDownButtonSettings()
{
   
    ButtonView = decrement,        
};

{% endhighlight %}

### Using Image with ButtonHeight and ButtonWidth

{% highlight C# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown();

numeric.IncrementButtonSettings = new UpDownButtonSettings()
{
    
    ButtonImage = "up.png",    
    ButtonHeight = 50,
	ButtonWidth = 50,
};

numeric.DecrementButtonSettings = new UpDownButtonSettings()
{
   
    ButtonImage = "down.png", 
	ButtonHeight = 50,
	ButtonWidth = 50,	
};

this.Add(numeric);

{% endhighlight %}

### Using FontIconText

{% highlight C# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown();

numeric.IncrementButtonSettings = new UpDownButtonSettings()
{
    
    ButtonFontIconFontFamily = "SegoeMDL2Assets",
    ButtonFontIcon = "\xE710",
};

numeric.DecrementButtonSettings = new UpDownButtonSettings()
{
   
    ButtonFontIconFontFamily = "SegoeMDL2Assets",
    ButtonFontIcon = "\xE732",
};

this.Add(numeric);

{% endhighlight %}

## Additional Spin Button Customization
### BackgroundColor

This property is used to change the background color of the increment and decrement buttons.

{% highlight C# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown();

numeric.IncrementButtonSettings = new UpDownButtonSettings()
{
    
    BackgroundColor = UIColor.Red,
};

numeric.DecrementButtonSettings = new UpDownButtonSettings()
{
    
    BackgroundColor = UIColor.Green,
};

{% endhighlight %}

![Display the spin buttons with background color](images/buttonbackground.png)

### HighlightedBackgroundColor

This property is used to change the background color of the tapped spin button.

{% highlight C# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown();
 
numeric.IncrementButtonSettings = new UpDownButtonSettings()
{
    
    HighlightedBackgroundColor = UIColor.Red,
};

numeric.DecrementButtonSettings = new UpDownButtonSettings()
{
    
    HighlightedBackgroundColor = UIColor.Green,
};
 

{% endhighlight %}

### ButtonFontColor

This property is used to change the text color of the increment and decrement buttons.

{% highlight C# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown();
 
numeric.IncrementButtonSettings = new UpDownButtonSettings()
{
    
    ButtonFontColor = UIColor.Blue,
};

numeric.DecrementButtonSettings = new UpDownButtonSettings()
{
    
    ButtonFontColor = UIColor.Yellow,
};

{% endhighlight %}

### HighlightedFontColor

This property is used to change the text color of the tapped spin button.

{% highlight C# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown();
 
numeric.IncrementButtonSettings = new UpDownButtonSettings()
{
    
    HighlightedFontColor = UIColor.Blue,
};

numeric.DecrementButtonSettings = new UpDownButtonSettings()
{
    
    HighlightedFontColor = UIColor.Yellow,
};

{% endhighlight %}




