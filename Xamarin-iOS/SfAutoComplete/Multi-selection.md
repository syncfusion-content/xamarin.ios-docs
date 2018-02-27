---
layout : post
title : Multi Selection in Syncfusion SfAutoComplete control for Xamarin.iOS
description :  Learn how to select multiple items in SfAutoComplete
platform : Xamarin.iOS 
control : AutoComplete
documentation : ug
---

# Multi Selection

Select multiple items from a suggestion list. There are two ways to perform multi selection in autocomplete.

* Token Representation

* Delimiter

## Token Representation

Selected items will be displayed with a customizable token representation and the users can remove each tokenized item with the close button.

{% tabs %}

{% highlight C# %}

	NSMutableArray countryList=new NSMutableArray();
	countryList.Add((NSString)"Afghanistan");
	countryList.Add((NSString)"Akrotiri");
	countryList.Add((NSString)"Albania"); 
	countryList.Add((NSString)"America"); 
	countryAutoComplete.AutoCompleteSource=countryList;
	countryAutoComplete.MultiSelectMode=MultiSelectMode.Token;
	countryAutoComplete.TokensWrapMode=TokensWrapMode.Wrap;
	countryAutoComplete.SuggestionMode=SuggestionMode.StartsWith;

{% endhighlight %}

{% endtabs %}

![](images/TokenRepresentation.png)

## Delimiter

{% tabs %}

{% highlight C# %}

	NSMutableArray countryList=new NSMutableArray();
	countryList.Add((NSString)"Afghanistan");
	countryList.Add((NSString)"Akrotiri");
	countryList.Add((NSString)"Albania"); 
	countryList.Add((NSString)"America"); 
	countryAutoComplete.AutoCompleteSource=countryList;
	countryAutoComplete.MultiSelectMode=MultiSelectMode.Delimiter;
	countryAutoComplete.Delimiter="*";

{% endhighlight %}

{% endtabs %}

![](images/Delimiter.png)

