---
title: Number Formatting in Syncfusion numeric textbox in Xamarin.iOS
description: Learn how to add format String, enable parser mode and percent display mode for SfNumericTextBox control.
platform: Xamarin.iOS
control: SfNumericTextBox
documentation: ug
---

# Number Formatting in SfNumericTextBox

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

![Display the SfNumericTextBox with FormatString](images/FormatString.png)

## Parser Input Value

The value of the SfNumericTextBox can be parsed based on the `ParserMode ` property. 

N> The `ParserMode` is of type Parsers containing enum values of Double and Decimal. The default Value for `ParserMode` is Double.

{% highlight c# %}

[C#]

numericTextBox.ParserMode = SFNumericTextBoxParsers.Decimal;
	  
{% endhighlight %}

![Display the SfNumericTextBox with ParserMode](images/ParserMode.png)

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

![Display the SfNumericTextBox with PercentDisplayMode](images/PercentDisplayMode.png)

## Group separator modes

[`GroupSeparatorMode`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfNumericTextBox.iOS.SfNumericTextBox_1.html#Syncfusion_SfNumericTextBox_iOS_SfNumericTextBox_GroupSeparatorMode) provides 2 states to display the group separator. 
When the mode is set as `Always`, it will display separator while typing itself on the other hand when the mode is set as `LostFocus` it will enable the separator when the control lost its focus.

N> [`EnableGroupSeparator`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfNumericTextBox.iOS.SfNumericTextBox_1.html#Syncfusion_SfNumericTextBox_iOS_SfNumericTextBox_EnableGroupSeparator) property must be enabled to use the [`GroupSeparatorMode`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfNumericTextBox.iOS.SfNumericTextBox_1.html#Syncfusion_SfNumericTextBox_iOS_SfNumericTextBox_GroupSeparatorMode).

{% tabs %}

{% highlight c# %}

      SfNumericTextBox numericTextBox = new SfNumericTextBox();
            numericTextBox.Frame = this.View.Frame;
            numericTextBox.Value = 123456;
            numericTextBox.FormatString = "n";
            numericTextBox.GroupSeparatorMode = GroupSeparatorMode.Always;
            numericTextBox.EnableGroupSeparator = true;
            this.Add(numericTextBox);

{% endhighlight %}

{% endtabs %}

![Display the value with enable group separator](images/SeparatorMode.png)

