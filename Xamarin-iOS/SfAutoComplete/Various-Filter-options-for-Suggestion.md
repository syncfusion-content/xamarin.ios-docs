---
layout : post
title : Suggestion mode for Syncfusion AutoComplete control in Xamarin.iOS
description : Learn how to display suggestion mode in AutoComplete
platform : Xamarin.iOS
control : AutoComplete
documentation : ug
---

# Various Filter options for Suggestion

By default, the items that matches with the starting letter will be displayed as suggestion. This phenomenon can be changed using  `SuggestionMode` property, which provides various option to filter the data according to the text entered. There are eight types of suggestion modes and are described as follows.

## Words that Starts with Input Text

Displays the list of suggestions based on starting letter.

{% tabs %}

{% highlight C# %}

countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeStartsWith;

{% endhighlight %}

{% endtabs %}

![](images/startswith.png)

### Filter with Character Casing

Displays the list of suggestions based on starting letter with case sensitive.

{% tabs %}

{% highlight C# %}

countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeStartsWithCaseSensitive;

{% endhighlight %}

{% endtabs %}

![](images/startswithcasesensitive.png)

## Words that Contains the Input Text

Displays the list of suggestions, if autocomplete list contains that words.
	
{% tabs %}

{% highlight C# %}

countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeContains;

{% endhighlight %}

{% endtabs %}

![](images/contains.png)

### Filter with Character Casing

Displays the list of suggestions, if autocomplete list contains that words with case sensitive.

{% tabs %}

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeContainsWithCaseSensitive;

{% endhighlight %}

{% endtabs %}

![](images/containswithcasesensitive.png)

## Words that Equals to the Input Text

Displays the word that matches.
	
{% tabs %}

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeEquals;

{% endhighlight %}

{% endtabs %}

![](images/equals.png)

### Filter with Character Casing

Displays the word that matches with case sensitive.
	
{% tabs %}

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeEqualsWithCaseSensitive;

{% endhighlight %}

{% endtabs %}

![](images/equalswithcasesensitive.png)

## Words that Ends with Input Text

Displays the list of suggestions based on ending word.

{% tabs %}

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeEndsWith;

{% endhighlight %}

{% endtabs %}

![](images/endswith.png)

### Filter with Character Casing

Displays the list of suggestions based on the ending word with case sensitive.
	
{% tabs %}

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeEndsWithCaseSensitive;

{% endhighlight %}

{% endtabs %}

![](images/endswithcasesensitive.png)

## Custom Filtering

Displays the suggestion based on the custom words in SfAutoComplete Control.

{% tabs %}

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeCustom;

{% endhighlight %}

{% endtabs %}

![](images/custom.png)
