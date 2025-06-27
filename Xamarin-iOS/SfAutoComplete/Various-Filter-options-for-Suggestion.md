---
layout: post
title: Suggestion mode for Syncfusion® AutoComplete control in Xamarin.iOS
description: Learn how to display suggestion mode in AutoComplete control with various filter options for enhanced user experience.
platform: xamarin.ios
control: AutoComplete
documentation: ug
---

# Various Filter Options for Suggestion

By default, items that match the starting letter will be displayed as suggestions. This behavior can be changed using the `SuggestionMode` property, which provides various options to filter the data according to the text entered. There are eight types of suggestion modes described as follows:

## Words that Start with Input Text

Displays the list of suggestions based on the starting letter.

{% tabs %}

{% highlight C# %}

countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeStartsWith;

{% endhighlight %}

{% endtabs %}

![Filter results starting with typed text](images/startswith.png)

### Filter with Character Casing

Displays the list of suggestions based on the starting letter with case sensitivity.

{% tabs %}

{% highlight C# %}

countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeStartsWithCaseSensitive;

{% endhighlight %}

{% endtabs %}

![Filter results starting with typed text case sensitive](images/startswithcasesensitive.png)

## Words that Contain the Input Text

Displays the list of suggestions if the AutoComplete list contains those words.
	
{% tabs %}

{% highlight C# %}

countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeContains;

{% endhighlight %}

{% endtabs %}

![Filter results containing typed text](images/contains.png)

### Filter with Character Casing

Displays the list of suggestions if the AutoComplete list contains those words with case sensitivity.

{% tabs %}

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeContainsWithCaseSensitive;

{% endhighlight %}

{% endtabs %}

![Filter results containing typed text case sensitive](images/containswithcasesensitive.png)

## Words that Equal the Input Text

Displays the word that matches exactly.
	
{% tabs %}

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeEquals;

{% endhighlight %}

{% endtabs %}

![Filter results matching exact text](images/equals.png)

### Filter with Character Casing

Displays the word that matches exactly with case sensitivity.
	
{% tabs %}

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeEqualsWithCaseSensitive;

{% endhighlight %}

{% endtabs %}

![Filter results matching exact text case sensitive](images/equalswithcasesensitive.png)

## Words that End with Input Text

Displays the list of suggestions based on the ending characters.

{% tabs %}

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeEndsWith;

{% endhighlight %}

{% endtabs %}

![Filter results ending with typed text](images/endswith.png)

### Filter with Character Casing

Displays the list of suggestions based on the ending characters with case sensitivity.
	
{% tabs %}

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeEndsWithCaseSensitive;

{% endhighlight %}

{% endtabs %}

![Filter results ending with typed text case sensitive](images/endswithcasesensitive.png)

## Custom Filtering

Displays suggestions based on custom filtering logic in the SfAutoComplete control.

{% tabs %}

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeCustom;

{% endhighlight %}

{% endtabs %}

![Custom filter results](images/custom.png)
