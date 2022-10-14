---
layout: post
title: Number Formatting in Syncfusion NumericUpDown control for Xamarin.iOS
description: Learn how to add format String, enable parser mode and percent display mode for NumericUpDown control.
platform: Xamarin.iOS
control: NumericUpDown
documentation: ug
---
# Number Formatting in NumericUpDown

## Format String

The `FormatString` property determines the format specifier by which the display text has to be formatted. 

N> The control displays the formatted text on lost focus. Default Value of `FormatString` is "n".

It has three types,

* `c` - Display the value with currency notation.

{% capture codesnippet1 %}
	
{% highlight C# %}

[C#]
	
numeric.FormatString = "c";
	 
{% endhighlight %}

{% endcapture %}

{{ codesnippet1 | UnOrderList_Indent_Level_1 }} 	

* `n` – Display the value in number format.

{% capture codesnippet2 %}
	
{% highlight C# %}

[C#]
	
numeric.FormatString = "n";
	 
{% endhighlight %}

{% endcapture %}

{{ codesnippet2 | UnOrderList_Indent_Level_1 }} 	

* `p` – Display the value in Percentage.

{% capture codesnippet3 %}

{% highlight C# %}

[C#]

numeric.FormatString = "p";
	 
{% endhighlight %}

{% endcapture %}

{{ codesnippet3 | UnOrderList_Indent_Level_1 }} 	

N> Instead of using above `FormatString` types, we can provide any symbol or value as string in `FormatString` property which will be appended with the value in NumericUpDown.

![Display the NumericUpDown with number formating](images/format.png)

## Parser Mode

The value of the NumericUpDown can be parsed based on the `ParsingMode` property. 

N> The `ParsingMode` is of type Parsers containing enum values of Double and Decimal. The default Value for `ParsingMode` is Double.

{% highlight C# %}

[C#]

numeric.ParsingMode = SFNumericUpDownParsingMode.Decimal;
	  
{% endhighlight %}

![Display the NumericUpDown with parser mode](images/ParserMode.png)

## Percent Display Mode

The `PercentDisplayMode` property can be used to display numeric data in Percent mode. 

N> The control displays the percent value on lost focus. 

It provides the following options:

* `Value`: Displays the value with percentage symbol.

{% capture codesnippet4 %}

{% highlight C# %}

[C#]

numeric.PercentDisplayMode = SFNumericUpDownPercentDisplayMode.Value;

{% endhighlight %}

{% endcapture %}

{{ codesnippet4 | UnOrderList_Indent_Level_1 }} 

* `Compute`: Displays the computed value with percentage symbol.

{% capture codesnippet5 %}

{% highlight C# %}

[C#]

numeric.PercentDisplayMode = SFNumericUpDownPercentDisplayMode.Compute;

{% endhighlight %}

{% endcapture %}

{{ codesnippet5 | UnOrderList_Indent_Level_1 }} 

![Display the NumericUpDown with percent mode](images/percent.png)