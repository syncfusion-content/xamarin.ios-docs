---
layout: post
title: Various Features in Syncfusion® SfNumericUpDown control for Xamarin.iOS
description: Learn how to decide maximum decimal digits to be displayed, nullable value support, autoreverse, setting range and configuring step value in SfNumericUpDown
platform: xamarin.ios
control: SfNumericUpDown
documentation: ug
---
# AutoReverse in SfNumericUpDown

When incrementing, the control will start from the Minimum value once it reaches the Maximum value, and vice versa.

N> By default, the property value is false.

{% highlight C# %}

[C#]

numeric.AutoReverse = true;

{% endhighlight %}

## Continuous Spinning Between Ranges

You can restrict the values within a specific range by setting the `Maximum` and `Minimum` property values.

N> By default, the minimum property value is 0 and the maximum property value is 100.

{% highlight C# %}

[C#]

numeric.Minimum = 10;

numeric.Maximum = 50

{% endhighlight %}

![Display the SfNumericUpDown with maximum range](images/maximum.png)

![Display the SfNumericUpDown with minimum range](images/minimum.png)

## Set Increment

The frequency at which values are incremented can be configured using the `StepValue` property.

N> By default, the property value is 1.

{% highlight C# %}

[C#]

numeric.StepValue = 6;

{% endhighlight %}
