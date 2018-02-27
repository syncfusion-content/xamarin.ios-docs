---
layout : post
title : MatchHighlighting in Syncfusion SfAutoComplete control for Xamarin.iOS
description : Learn how to highlight the matched text in SfAutoComplete
platform : Xamarin.iOS 
control : AutoComplete
documentation : ug
---

# Highlighting matched text

Highlight matching characters in a suggestion list to pick an item with more clarity. There are two ways to highlight the matching text:


* FirstOccurrence

* MultipleOccurrence

## FirstOccurrence

{% tabs %}

{% highlight C# %}

	NSMutableArray countryList=new NSMutableArray();
	countryList.Add((NSString)"Afghanistan");
	countryList.Add((NSString)"Akrotiri");
	countryList.Add((NSString)"Albania"); 
	countryAutoComplete.AutoCompleteSource=countryList;
	countryAutoComplete.TextHighlightMode=OccurrenceMode.FirstOccurrence;
	countryAutoComplete.SuggestionMode=SuggestionMode.StartsWith;

{% endhighlight %}

{% endtabs %}

![](images/FirstOccurrence.png)

## MultipleOccurrence

{% tabs %}

{% highlight C# %}

	NSMutableArray countryList=new NSMutableArray();
	countryList.Add((NSString)"Afghanistan");
	countryList.Add((NSString)"Akrotiri");
	countryList.Add((NSString)"Albania"); 
	countryAutoComplete.AutoCompleteSource=countryList;
	countryAutoComplete.TextHighlightMode=OccurrenceMode.MultipleOccurrence;
	countryAutoComplete.SuggestionMode=SuggestionMode.Contains;

{% endhighlight %}

{% endtabs %}

![](images/MultipleOccurrence.png)

