---
layout : post
title : Maximum Display Item with Expander in Syncfusion® SfAutoComplete control for Xamarin.iOS
description : Learn how to restrict the number of suggestions displayed and load remaining items using LoadMore functionality in SfAutoComplete
platform : xamarin.ios 
control : AutoComplete
documentation : ug
---

# Maximum Display Item with Expander

Restrict the number of suggestions displayed and load the remaining items by selecting LoadMore. You can restrict the maximum number of suggestions to be displayed using the `MaximumSuggestion` property. You can set the desired text for displaying the Load More option using the `LoadMoreText` property.

{% tabs %}

{% highlight C# %}

countryAutoComplete.MaximumSuggestion="4";
countryAutoComplete.LoadMoreText = "LOAD MORE";
countryAutoComplete.SuggestionMode=SuggestionMode.StartsWith;

{% endhighlight %}

{% endtabs %}
## Restricting the Maximum Display of Items Dynamically

You can restrict the maximum display of items dynamically by calling the `LoadMore` method. The maximum suggestion count can be changed dynamically by calling the LoadMore method with the maximum suggestion count as an argument.
 
{% tabs %}
{% highlight c# %}
 
// Without passing arguments
countryAutoComplete.LoadMore();
 
// With passing arguments
countryAutoComplete.LoadMore(5);
 
{% endhighlight %}
{% endtabs %}

![](images/loadmore.png)