---
layout: post
title: Various Features in Syncfusion NumericUpDown control for Xamarin.iOS
description: Learn how to decide maximum decimal digits to be displayed, nullable value support, autoreverse, setting range and configuring step value in NumericUpDown
platform: Xamarin.iOS
control: NumericUpDown
documentation: ug
---
# AutoReverse

While incrementing, the control will start from Minimum once it reaches the Maximum and vice-versa.

N> By default the property value is false.

{% tabs %}

{% highlight C# %}

numericupdown.AutoReverse = true;

{% endhighlight %}

{% endtabs %}

## Continuous Spinning Between Ranges

User can restrict the Values between a specific range by setting `Maximum` and `Minimum` property value.

N> By default the minimum property value is 0 and maximum property value is 100.

{% tabs %}

{% highlight C# %}

	numericupdown.Minimum = 10;
	numericupdown.Maximum = 50

{% endhighlight %}

{% endtabs %}

![](images/maximum.png)

![](images/minimum.png)

## Set Increment

Frequency in which values gets incremented can be decided using `StepValue` property.

N> By default the property value is 1.

{% tabs %}

{% highlight C# %}

	numericupdown.StepValue = 6;

{% endhighlight %}

{% endtabs %}
