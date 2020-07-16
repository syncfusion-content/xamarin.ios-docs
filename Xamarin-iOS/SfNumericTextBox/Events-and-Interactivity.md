---
layout: post
title: Events and Interactivity in Syncfusion NumericTextBox for Xamarin.iOS
description: Learn how to get the value changed event and some interactivity for SfNumericTextBox in Xamarin.iOS platform.
platform: Xamarin.iOS
control: SfNumericTextBox
documentation: ug
---
# Events and Interactivity

## Events

### ValueChanged 

You can perform any operation when changing the value of NumericTextBox using the ValueChanged event. The ValueChanged event returns the changed value in NumericTextBox.

For example you can restrict the NumericTextBox value if it exceed's greater than 3 digits using following code.

{% highlight c# %}

[C#]

SfNumericTextBox numericTextBox = new SfNumericTextBox()
{
    Value = 123,
	ValueChangeMode = SFNumericUpDownValueChangeMode.OnKeyFocus,
};


numericTextBox.ValueChanged += (object sender, Syncfusion.SfNumericTextBox.iOS.ValueEventArgs e) =>
{
    //Do the action when changed the value property.
};

this.Add(numericTextBox);

{% endhighlight %}

## Interactivity : ValueChangeMode

The ValueChangeMode property is used to mention when value needs to update, either in key pressed or focus lost state. When ValueChangeMode is set to OnKeyFocus, the value will be updated on each key press. When ValueChangeMode is set to OnLostFocus, the value is updated when the control lose the focus or the focus is moved to the next control. ValueChangeMode includes the following options:

1. OnKeyFocus
2. OnLostFocus

### OnKeyFocus

{% highlight c# %}

[C#]

SfNumericTextBox numericTextBox = new SfNumericTextBox()
{
    Value = 123,
	ValueChangeMode = SFNumericTextBoxValueChangeMode.OnKeyFocus,
};

{% endhighlight %}

### OnLostFocus

{% highlight c# %}

[C#]

SfNumericTextBox numericTextBox = new SfNumericTextBox()
{
	
    Value = 123,
	ValueChangeMode = SFNumericTextBoxValueChangeMode.OnLostFocus,
};

{% endhighlight %}

## Selection Support in NumericTextBox

The `SelectAllOnFocus` property is used to specify whether the text should be selected when the control gets focus.

{% highlight c# %}

[C#]

numericTextBox.SelectAllOnFocus = true;
 
{% endhighlight %}
