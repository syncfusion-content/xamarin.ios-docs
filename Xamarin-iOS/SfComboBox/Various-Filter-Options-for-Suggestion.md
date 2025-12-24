---
layout : post
title : Suggestion mode for Syncfusion® SfComboBox Control in Xamarin.iOS
description : Learn how to display suggestion mode in ComboBox
platform : xamarin.ios
control : SfComboBox
documentation : ug
---

# Various filter options for suggestion

The combo box enables filer option for filtering the suggestions in the drop-down. 

{% tabs %}

{% highlight C# %}
	
  combobox.AllowFiltering = true;
  combobox.IsEditableMode = true;
	 
{% endhighlight %}

{% endtabs %}

## Types Of filtering

The phenomenon of string comparison for filtering suggestions can be changed using the `SuggestionMode `property. The default filtering strategy is `StartsWith` and it is case insensitive. The available filtering modes are,

*	StartsWith

*	StartsWithCaseSensitive

*	Contains

*	ContainsWithCaseSensitive

*	Equals

*	EqualsWithCaseSensitive

*	EndsWith

*	EndsWithCaseSensitive

*	Custom


## Words that starts with input text

Displays a list of suggestions based on the starting letter.

{% tabs %}

{% highlight C# %}

    combobox.SuggestionMode = SuggestionMode.StartsWith;   	
	 
{% endhighlight %}

{% endtabs %}
	
![Start words with input text in Xamarin.Ios ComboBox.](images/startswith.png)

### Filter with character casing

Displays a list of suggestions based on the starting letter with case sensitive.

{% tabs %}

{% highlight C# %}
	
	combobox.SuggestionMode = SuggestionMode.StartsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![Starting letter with case sensitive in Xamarin.Ios ComboBox.](images/startswithcasesensitive.png)

## Words that contain the input text

Displays a list of suggestions if the combo box list contains that words.

{% tabs %}

{% highlight C# %}
	
	combobox.SuggestionMode = SuggestionMode.Contains;
	 
{% endhighlight %}

{% endtabs %}
	
![Words that contains input text in Xamarin.Ios ComboBox.](images/contains.png)

### Filter with character casing

Displays a list of suggestions if the combo box list contains that words with case sensitive.

{% tabs %}

{% highlight C# %}
	
	combobox.SuggestionMode = SuggestionMode.ContainsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![Words that contains case sensitive in Xamarin.Ios ComboBox.](images/containswithcasesensitive.png)

## Words that equals to input text

Displays the word that matches the input text.

{% tabs %}

{% highlight C# %}
	
	combobox.SuggestionMode = SuggestionMode.Equals;
	 
{% endhighlight %}

{% endtabs %}
	
![Equal words to input text in Xamarin.Ios ComboBox.](images/equals.png)

### Filter with character casing

Displays the word that matches the input text with case sensitive.

{% tabs %}

{% highlight C# %}
	
	combobox.SuggestionMode = SuggestionMode.EqualsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![Equal word with case sensitive in Xamarin.Ios ComboBox.](images/equalswithcasesensitive.png)

## Words that ends with input text

Displays a list of suggestions based on the ending word.

{% tabs %}

{% highlight C# %}
	
	combobox.SuggestionMode = SuggestionMode.EndsWith;
	 
{% endhighlight %}

{% endtabs %}
	
![Ending word with input text in Xamarin.Ios ComboBox](images/endswith.png)

### Filter with character casing

Displays a list of suggestions based on the ending word with case sensitive.

{% tabs %}

{% highlight C# %}
	
combobox.SuggestionMode = SuggestionMode.EndsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![Ending word with case sensitive in Xamarin.Ios ComboBox.](images/endswithcasesensitive.png)


### Custom filter

Displays a list of suggestions based on the custom words in the combo box.
{% tabs %}

{% highlight C# %}
	
combobox.SuggestionMode = SuggestionMode.Custom;
	 
{% endhighlight %}

{% endtabs %}
	



