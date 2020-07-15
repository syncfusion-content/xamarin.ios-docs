---
title: Number Formatting in Syncfusion NumericTextBox control for Xamarin.iOS
description: Learn how to add format String, enable parser mode and percent display mode for NumericTextBox control.
platform: Xamarin.iOS
control: NumericTextBox
documentation: ug
---

# Number Formatting in NumericTextBox

The values of the SfNumericTextBox can be configured to display different formats like currency format, percent format etc. 

## Format String

The `FormatString` property determines the format specifier by which the display text has to be formatted. 

N> The control displays the formatted text on lost focus. Default Value of `FormatString` is "n".

### Display Currency Notation

`c` - Displays the value with currency notation.
	
{% highlight c# %}

[C#]
	
numericTextBox.FormatString = "c";
	 
{% endhighlight %}
	
### Display Number Notation

`n` – Display the value in number format.
	
{% highlight c# %}

[C#]
	
numericTextBox.FormatString = "n";
	 
{% endhighlight %}
	
### Display Percentage Notation

`p` – Display the value in percentage.
	
{% highlight c# %}

[C#]

numericTextBox.FormatString = "p";
	 
{% endhighlight %}
	
N> Instead of using above `FormatString` types, we can provide any symbol or value as string in `FormatString` property which will be appended with the value in SfNumericTextBox. 

![Display the NumericTextBox with FormatString](images/FormatString.png)

## Parser Input Value

The value of the SfNumericTextBox can be parsed based on the `ParserMode ` property. 

N> The `ParserMode` is of type Parsers containing enum values of Double and Decimal. The default Value for `ParserMode` is Double.

{% highlight c# %}

[C#]

numericTextBox.ParserMode = SFNumericTextBoxParsers.Decimal;
	  
{% endhighlight %}

![Display the NumericTextBox with ParserMode](images/ParserMode.png)

## Compute to Percentage

The `PercentDisplayMode` property can be used to display numeric data in Percent mode. 

N> The control displays the percent value on lost focus. 

It provides the following options:

* `Value`: Displays the value with percentage symbol.

{% highlight c# %}

[C#]

numericTextBox.PercentDisplayMode = SFNumericTextBoxPercentDisplayMode.Value;

{% endhighlight %}

* `Compute`: Displays the computed value with percentage symbol.

{% highlight c# %}

[C#]

numericTextBox.PercentDisplayMode = SFNumerictextBoxPercentDisplayMode.Compute;

{% endhighlight %}

![Display the NumericTextBox with PercentDisplayMode](images/PercentDisplayMode.png)


