---
layout: post
title: Events and Interactivity in Syncfusion NumericUpDown for Xamarin.iOS
description: Learn how to get the value changed event and some interactivity for NumericUpDown in Xamarin.iOS platform.
platform: Xamarin.iOS
control: NumericUpDown
documentation: ug
---
# Events and Interactivity

## Events

### ValueChanged 

You can perform any operation when changing the value of NumericUpDown using the ValueChanged event. The ValueChanged event returns the changed value in NumericUpDown.

For example you can restrict the NumericUpDown value if it exceed's greater than 3 digits using following code.

{% highlight c# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown()
{
	
    Value = 123,
	ValueChangeMode = SFNumericUpDownValueChangeMode.OnKeyFocus,
};

string updateValue = "";

numeric.ValueChanged += (object sender, Syncfusion.SfNumericUpDown.iOS.ValueEventArgs e) =>
{
    
    if (e.Value.ToString().Length <= 3 && e.Value != null)
    {
        updateValue = e.Value.ToString();
    }
    else
    {
        numeric.Value = updateValue;
    }
};

this.Add(numeric);

{% endhighlight %}

## Interactivity : ValueChangeMode

The ValueChangeMode property is used to mention when value needs to update, either in key pressed or focus lost state. When ValueChangeMode is set to OnKeyFocus, the value will be updated on each key press. When ValueChangeMode is set to OnLostFocus, the value is updated when the control lose the focus or the focus is moved to the next control. ValueChangeMode includes the following options:

1. OnKeyFocus
2. OnLostFocus

### OnKeyFocus

{% highlight c# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown()
{
	
    Value = 123,
	ValueChangeMode = SFNumericUpDownValueChangeMode.OnKeyFocus,
};

{% endhighlight %}

### OnLostFocus

{% highlight c# %}

[C#]

SfNumericUpDown numeric = new SfNumericUpDown()
{
	
    Value = 123,
	ValueChangeMode = SFNumericUpDownValueChangeMode.OnLostFocus,
};

{% endhighlight %}
