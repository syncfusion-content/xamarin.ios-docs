---
layout: post
title: Appearance in Syncfusion NumericUpDown control for Xamarin.iOS
description: Learn how to add customize spin buttons position and its appearance in Xamarin.iOS NumericUpDown control.
platform: Xamarin.iOS
control: NumericUpDown
documentation: ug
---

# Spin Button Alignment

Spin Button position in the NumericUpDown control can be changed relative to the TextBox based on `SpinButtonAlignment` property. 

There are three built-in modes.

### Right

Spin Buttons will get aligned to the right side of the control.

{% highlight C# %}

[C#]

numeric.SpinButtonAlignment = SFNumericUpDownSpinButtonAlignment.Right;

{% endhighlight %}

![Display the NumericUpDown spin button with right](images/spinright.png)

### Left

Spin Buttons will get aligned to the left side of the control.

{% highlight C# %}

[C#]

numeric.SpinButtonAlignment = SFNumericUpDownSpinButtonAlignment.Left;

{% endhighlight %}

![Display the NumericUpDown spin button with left](images/spinleft.png)

### Both

Spin Buttons will get aligned to the both side of the control.

{% highlight C# %}

[C#]

numeric.SpinButtonAlignment = SFNumericUpDownSpinButtonAlignment.Both;

{% endhighlight %}

![Display the NumericUpDown spin button with both side](images/spinboth.png)

N> By default the property value is Right.

## UpDownButtonSetting customization

You can customize the UpDownButton of `SfNumericUpDown` control by using any of the following ways:

1. View
2. Image
3. FontIconText

### By using the View

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

### By using the Image with ButtonHeight and ButtonWidth

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

### By using the FontIconText

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

## Additional customization on spin buttons

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

![Display the value with maximum](images/buttonbackground.png)

### HighlightedBackgroundColor

This property is used to change the background color of tapped spin button

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

This property is used to change the text color of tapped spin button.

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




