---
layout : post
title : Suggestion mode for Syncfusion AutoComplete control in Xamarin.iOS
description : Learn how to display suggestion mode in AutoComplete
platform : Xamarin.iOS
control : AutoComplete
documentation : ug
---

# Suggestion Mode

`SuggestionMode` property provides various option to filter the data according to the text entered. They are,

* StartsWith - It begins to search with the starting letter.

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeStartsWith;

{% endhighlight %}

![](images/startswith.png)

* StartsWithCaseSensitive - This mode is used to display the suggestions based on the starting letter with case sensitive in SfAutoComplete.

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeStartsWithCaseSensitive;

{% endhighlight %}

![](images/startswithcasesensitive.png)

* Contains - It displays suggestions if SfAutoComplete contains that words.

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeContains;

{% endhighlight %}

![](images/contains.png)

* ContainsWithCaseSensitive - It displays the suggestions if SfAutoComplete contains that words with case sensitive.

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeContainsWithCaseSensitive;

{% endhighlight %}

![](images/containswithcasesensitive.png)

* Equals - It displays the word that matches.

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeEquals;

{% endhighlight %}

![](images/equals.png)

* EqualsWithCaseSensitive - It displays the word that matches with case sensitive.

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeEqualsWithCaseSensitive;

{% endhighlight %}

![](images/equalswithcasesensitive.png)

* EndsWith - It displays the suggestion based on ending word in SfAutoComplete control.

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeEndsWith;

{% endhighlight %}

![](images/endswith.png)

* EndsWithCaseSensitive - It displays the suggestion based on the ending words with case sensitive in SfAutoComplete Control.

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeEndsWithCaseSensitive;

{% endhighlight %}

![](images/endswithcasesensitive.png)

* Custom - It displays the suggestion based on the custom words in SfAutoComplete Control.

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeCustom;

{% endhighlight %}

![](images/endswith.png)
