---
layout: post
title: AutoComplete mode in Syncfusion® AutoComplete control in Xamarin.iOS
description: Learn how to change the AutoComplete mode in AutoComplete control to customize suggestion display behavior.
platform: xamarin.ios
control: AutoComplete
documentation: ug
---

# Suggestion Display Mode

The `AutoCompleteMode` property is used to determine the suggestion pattern for displaying the filtered data according to the text entered. The different types of patterns are described below:

* Suggest

* Append

* Suggest and Append

N> The default option is Suggest mode.

## Append

**Append** - Appends the first matching string to the entered characters.

{% tabs %}

{% highlight C# %}

countryAutoComplete.AutoCompleteMode=SFAutoCompleteAutoCompleteMode.SFAutoCompleteAutoCompleteModeAppend; 

{% endhighlight %}

{% endtabs %}


## Suggest in Dropdown

**Suggest** - Displays the suggestions in the dropdown.

{% tabs %}

{% highlight C# %}

countryAutoComplete.AutoCompleteMode=SFAutoCompleteAutoCompleteMode.SFAutoCompleteAutoCompleteModeSuggest; 

{% endhighlight %}

{% endtabs %}

## Both Append and Suggest in Dropdown

**SuggestAppend** - Displays the suggestions in the dropdown along with appending the first matching string.

{% tabs %}

{% highlight C# %}

countryAutoComplete.AutoCompleteMode=SFAutoCompleteAutoCompleteMode.SFAutoCompleteAutoCompleteModeSuggestAppend; 

{% endhighlight %}

{% endtabs %}
![Autocomplete display modes](images/autocompletemode.png)
