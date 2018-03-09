---
layout : post
title : MatchHighlighting in Syncfusion SfAutoComplete control for Xamarin.iOS
description : Learn how to highlight the matched text in SfAutoComplete
platform : Xamarin.iOS 
control : AutoComplete
documentation : ug
---

# Maximum Display Item with Expander

Restrict the number of suggestions displayed and have the remaining items loaded by selecting LoadMore.We can restrict maximum suggestion to be displayed with the `MaximumSuggestion` property. We can set the desire text for the displaying the Load more text with the property `LoadMoreText`.

{% tabs %}

{% highlight C# %}

countryAutoComplete.MaximumSuggestion="4";
countryAutoComplete.LoadMoreText = "LOAD MORE";
countryAutoComplete.SuggestionMode=SuggestionMode.StartsWith;

{% endhighlight %}

{% endtabs %}
### Restricting the maximum display of item dynamically

We can restrict the maximum display of items dynamically by calling `LoadMore` method. The user can dynamically change the maximum suggestion count by calling LoadMore method by giving the maximum suggestion as the argument inside.
 
{% tabs %}
{% highlight c# %}
 
// without passing arguments
countryAutoComplete.LoadMore();
 
// with passing arguments
countryAutoComplete.LoadMore(5);
 
{% endhighlight %}
{% endtabs %}

![](images/loadmore.png)

## No Results Found

When the entered item is not in the suggestion list, SfAutoComplete displays a text indicating there is no search results found. We can set the desire text to be displayed for indicating no results found with the `NoResultsFoundText` property.

{% tabs %}

{% highlight C# %}

countryAutoComplete.NoResultsFoundText= "No Results Found";
countryAutoComplete.SuggestionMode=SuggestionMode.StartsWith;

{% endhighlight %}

{% endtabs %}

![](images/NoResultsFound.png)