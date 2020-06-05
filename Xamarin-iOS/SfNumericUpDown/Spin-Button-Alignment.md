---
layout: post
title: Appearance in Syncfusion NumericUpDown control for Xamarin.iOS
description: Learn how to add customize spin buttons position in NumericUpDown.
platform: Xamarin.iOS
control: NumericUpDown
documentation: ug
---

# Spin Button Alignment

Spin Button position in the NumericUpDown control can be changed relative to the TextBox based on `SpinButtonAlignment` property. 

There are three built-in modes.

### Right

Spin Buttons will get aligned to the right side of the control.

{% tabs %}

{% highlight C# %}

[C#]

numeric.SpinButtonAlignment = SFNumericUpDownSpinButtonAlignment.Right;

{% endhighlight %}

{% endtabs %}

![Display the NumericUpDown spin button with right](images/spinright.png)

### Left

Spin Buttons will get aligned to the left side of the control.

{% tabs %}

{% highlight C# %}

[C#]

numeric.SpinButtonAlignment = SFNumericUpDownSpinButtonAlignment.Left;

{% endhighlight %}

{% endtabs %}

![Display the NumericUpDown spin button with left](images/spinleft.png)

### Both

Spin Buttons will get aligned to the both side of the control.

{% tabs %}

{% highlight C# %}

[C#]

numeric.SpinButtonAlignment = SFNumericUpDownSpinButtonAlignment.Both;

{% endhighlight %}

{% endtabs %}

![Display the NumericUpDown spin button with both side](images/spinboth.png)

N> By default the property value is Right.

## UpDownButtonSetting customization

You can customize the UpDownButton of `SfNumericUpDown` control by using any of the following ways:

1. View
2. Image
3. FontIconText

### By using the View

{% tabs %}

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

{% endtabs %}

### By using the Image with ButtonHeight and ButtonWidth

{% tabs %}

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

{% endtabs %}


### By using the FontIconText

{% tabs %}

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

{% endtabs %}


## Additional customization properties of UpDownButtonSettings

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

{% endtabs %}

![Display the value with maximum](images/buttonbackground.png)

### HighlightedBackgroundColor

This property is used to change the background color of the increment or decrement button.

{% tabs %}

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

{% endtabs %}

### ButtonFontColor

This property is used to change the text color of the increment and decrement buttons.

{% tabs %}

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

{% endtabs %}

### HighlightedFontColor

This property is used to change the text color of the button by clicking the increment or decrement button.

{% tabs %}

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

{% endtabs %}




