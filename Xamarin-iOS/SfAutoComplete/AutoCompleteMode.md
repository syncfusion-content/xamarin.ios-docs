---
layout : post
title : AutoComplete mode in Syncfusion AutoComplete control in Xamarin.iOS
description : Learn how to change the AutoComplete mode in AutoComplete
platform : Xamarin.iOS
control : AutoComplete
documentation : ug
---

# AutoCompleteMode

The `AutocompleteMode` property is used to customize the behavior of the suggestions that are filtered according to the text entered. By default there are three AutoComplete modes provided. They are:

* Append - Appends the first matching string with the entered character.

{% highlight C# %}

	countryAutoComplete.AutoCompleteMode=SFAutoCompleteAutoCompleteMode.SFAutoCompleteAutoCompleteModeAppend; 

{% endhighlight %}

* Suggest - Displays the suggestion in the dropdown.

{% highlight C# %}

	countryAutoComplete.AutoCompleteMode=SFAutoCompleteAutoCompleteMode.SFAutoCompleteAutoCompleteModeSuggest; 

{% endhighlight %}

* SuggestAppend - Displays the suggestion in the dropdown along with appending the first matching string.

{% highlight C# %}

	countryAutoComplete.AutoCompleteMode=SFAutoCompleteAutoCompleteMode.SFAutoCompleteAutoCompleteModeSuggestAppend; 

{% endhighlight %}

![](images/autocompletemode.png)
