---
layout: post
title: Events in Syncfusion® NumericUpDown for Xamarin.iOS
description: Learn how to get the value changed event and some interactivity for SfNumericUpDown in Xamarin.iOS platform.
platform: xamarin.ios
control: SfNumericUpDown
documentation: ug
---
# Events and Interactivity

## Events

### ValueChanged 

You can perform operations when the value of SfNumericUpDown changes using the ValueChanged event. The ValueChanged event returns the changed value in the SfNumericUpDown.

For example, you can restrict the SfNumericUpDown value if it exceeds 3 digits using the following code:

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

The ValueChangeMode property is used to specify when the value needs to be updated, either on key press or when focus is lost. When ValueChangeMode is set to OnKeyFocus, the value will be updated on each key press. When ValueChangeMode is set to OnLostFocus, the value is updated when the control loses focus or when focus is moved to the next control.

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

## Selection Support

The `SelectAllOnFocus` property is used to specify whether the text should be selected when the control gets focus.

{% highlight c# %}

[C#]

numeric.SelectAllOnFocus = true;
  
{% endhighlight %}
