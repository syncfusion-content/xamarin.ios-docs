---
layout: post
title: Various Features in Syncfusion NumericUpDown control for Xamarin.iOS
description: Learn how to decide maximum decimal digits to be displayed, nullable value support, autoreverse, setting range and configuring step value in NumericUpDown
platform: Xamarin.iOS
control: NumericUpDown
documentation: ug
---
# AutoReverse in NumericUpDown

While incrementing, the control will start from Minimum once it reaches the Maximum and vice-versa.

N> By default the property value is false.

{% highlight C# %}

[C#]

numeric.AutoReverse = true;

{% endhighlight %}

## Continuous Spinning Between Ranges

User can restrict the Values between a specific range by setting `Maximum` and `Minimum` property value.

N> By default the minimum property value is 0 and maximum property value is 100.

{% highlight C# %}

[C#]

numeric.Minimum = 10;

numeric.Maximum = 50

{% endhighlight %}

![Display the NumericUpDown with maximum range](images/maximum.png)

![Display the NumericUpDown with minimum range](images/minimum.png)

## Set Increment

Frequency in which values gets incremented can be decided using `StepValue` property.

N> By default the property value is 1.

{% highlight C# %}

[C#]

numeric.StepValue = 6;

{% endhighlight %}
