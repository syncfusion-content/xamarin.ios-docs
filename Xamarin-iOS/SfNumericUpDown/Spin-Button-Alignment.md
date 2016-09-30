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

numericupdown.SpinButttonAlignment = SFNumericUpDownSpinButtonAlignment.Right;

{% endhighlight %}

{% endtabs %}

![](images/spinright.png)

### Left

Spin Buttons will get aligned to the left side of the control.

{% tabs %}

{% highlight C# %}

numericupdown.SpinButttonAlignment = SFNumericUpDownSpinButtonAlignment.Left;

{% endhighlight %}

{% endtabs %}

![](images/spinleft.png)

### Both

Spin Buttons will get aligned to the both side of the control.

{% tabs %}

{% highlight C# %}

numericupdown.SpinButttonAlignment = SFNumericUpDownSpinButtonAlignment.Both;

{% endhighlight %}

{% endtabs %}

![](images/spinboth.png)

N> By default the property value is Right.



