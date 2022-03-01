---
layout : post
title : AutoComplete mode in Syncfusion AutoComplete control in Xamarin.iOS
description : Learn how to change the AutoComplete mode in AutoComplete
platform : Xamarin.iOS
control : AutoComplete
documentation : ug
---

# Suggestion Display Mode

The `AutocompleteMode` property is used to decide the suggestion pattern for displaying the filtered data according to the text entered. The different types of pattern are described below

* Suggest

* Append

* Suggest and Append

N> The default option is suggest mode.

## Append

Append - Appends the first matching string with the entered character.

{% tabs %}

{% highlight C# %}

countryAutoComplete.AutoCompleteMode=SFAutoCompleteAutoCompleteMode.SFAutoCompleteAutoCompleteModeAppend; 

{% endhighlight %}

{% endtabs %}


## Suggest in Dropdown

Suggest - Displays the suggestion in the dropdown.

{% tabs %}

{% highlight C# %}

countryAutoComplete.AutoCompleteMode=SFAutoCompleteAutoCompleteMode.SFAutoCompleteAutoCompleteModeSuggest; 

{% endhighlight %}

{% endtabs %}

## Both Append and Suggest in DropDown

SuggestAppend - Displays the suggestion in the dropdown along with appending the first matching string.

{% tabs %}

{% highlight C# %}

countryAutoComplete.AutoCompleteMode=SFAutoCompleteAutoCompleteMode.SFAutoCompleteAutoCompleteModeSuggestAppend; 

{% endhighlight %}

{% endtabs %}

![](images/autocompletemode.png)
