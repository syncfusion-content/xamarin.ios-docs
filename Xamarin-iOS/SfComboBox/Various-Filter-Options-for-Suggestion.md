---
layout : post
title : Filtering options for Syncfusion® SfComboBox Control in Xamarin.iOS
description : Learn how to configure various filter options for suggestions in ComboBox
platform : xamarin.ios
control : SfComboBox
documentation : ug
---

# Various Filter Options for Suggestions

The ComboBox control provides filtering options to filter suggestions displayed in the dropdown list.

{% tabs %}

{% highlight C# %}
	
  combobox.AllowFiltering = true;
  combobox.IsEditableMode = true;
	 
{% endhighlight %}

{% endtabs %}

## Types of Filtering

The string comparison method for filtering suggestions can be configured using the `SuggestionMode` property. The default filtering strategy is `StartsWith` and it is case insensitive. The available filtering modes are:

* StartsWith
* StartsWithCaseSensitive
* Contains
* ContainsWithCaseSensitive
* Equals
* EqualsWithCaseSensitive
* EndsWith
* EndsWithCaseSensitive
* Custom

## StartsWith Mode

### Words that start with input text

Displays a list of suggestions based on items that start with the entered text.

{% tabs %}

{% highlight C# %}

    combobox.SuggestionMode = SuggestionMode.StartsWith;   	
	 
{% endhighlight %}

{% endtabs %}
	
![StartsWith filtering example](images/startswith.png)

### Case-sensitive filtering

Displays a list of suggestions based on items that start with the entered text, with case-sensitive matching.
{% tabs %}

{% highlight C# %}
	
	combobox.SuggestionMode = SuggestionMode.StartsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![StartsWith case-sensitive filtering example](images/startswithcasesensitive.png)

## Contains Mode
### Words that contain the input text

Displays a list of suggestions if the ComboBox items contain the entered text.

{% tabs %}

{% highlight C# %}
	
	combobox.SuggestionMode = SuggestionMode.Contains;
	 
{% endhighlight %}

{% endtabs %}
	
![Contains filtering example](images/contains.png)

### Case-sensitive filtering

Displays a list of suggestions if the ComboBox items contain the entered text, with case-sensitive matching.
{% tabs %}

{% highlight C# %}
	
	combobox.SuggestionMode = SuggestionMode.ContainsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![Contains case-sensitive filtering example](images/containswithcasesensitive.png)

## Equals Mode
### Words that equal the input text

Displays suggestions that exactly match the entered text.

{% tabs %}

{% highlight C# %}
	
	combobox.SuggestionMode = SuggestionMode.Equals;
	 
{% endhighlight %}

{% endtabs %}
	
![Equals filtering example](images/equals.png)

### Case-sensitive filtering

Displays suggestions that exactly match the entered text, with case-sensitive matching.
{% tabs %}

{% highlight C# %}
	
	combobox.SuggestionMode = SuggestionMode.EqualsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![Equals case-sensitive filtering example](images/equalswithcasesensitive.png)

## EndsWith Mode
### Words that end with input text

Displays a list of suggestions based on items that end with the entered text.

{% tabs %}

{% highlight C# %}
	
	combobox.SuggestionMode = SuggestionMode.EndsWith;
	 
{% endhighlight %}

{% endtabs %}
	
![EndsWith filtering example](images/endswith.png)

### Case-sensitive filtering

Displays a list of suggestions based on items that end with the entered text, with case-sensitive matching.
{% tabs %}

{% highlight C# %}
	
combobox.SuggestionMode = SuggestionMode.EndsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![EndsWith case-sensitive filtering example](images/endswithcasesensitive.png)

## Custom Filter Mode

Enables custom filtering logic for displaying suggestions based on your specific requirements.
{% tabs %}

{% highlight C# %}
	
combobox.SuggestionMode = SuggestionMode.Custom;
	 
{% endhighlight %}

{% endtabs %}
	




