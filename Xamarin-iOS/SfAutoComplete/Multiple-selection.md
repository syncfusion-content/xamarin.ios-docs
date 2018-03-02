---
layout : post
title : Multi Selection in Syncfusion SfAutoComplete control for Xamarin.iOS
description :  Learn how to select multiple items in SfAutoComplete
platform : Xamarin.iOS 
control : AutoComplete
documentation : ug
---

# Multiple Selection

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

### Wrap Mode of Token

The selected item can be displayed as token inside SfAutoComplete in two ways. They are

* `Wrap` - When `TokensWrapMode` is set to `Wrap` the selected items will be wrap to the next line of the SfAutoComplete.

* `None` - When `TokensWrapMode` is set to `None` the selected item will be wrap in horizontal orientation.

{% tabs %}

{% highlight C# %}

	NSMutableArray countryList=new NSMutableArray();
	countryList.Add((NSString)"Afghanistan");
	countryList.Add((NSString)"Algeria");
	countryList.Add((NSString)"Albania"); 
	countryList.Add((NSString)"America"); 
	countryAutoComplete.AutoCompleteSource=countryList;
	countryAutoComplete.MultiSelectMode=MultiSelectMode.Token;
	countryAutoComplete.TokensWrapMode=TokensWrapMode.Wrap;
	countryAutoComplete.SuggestionMode=SuggestionMode.StartsWith;

{% endhighlight %}

{% endtabs %}

### Token Customization

Customization can be done for Token. There are various ways to customize the tokens. They are as follows.

* `TextColor` - sets the color of the text inside the token.

* `FontSize` - sets the size of the Font inside the token.

* `FontFamily` - sets the Font family for the text inside the token.

* `BackgroundColor` - sets the background color of the token.

* `SelectedBackgroundColor` - sets the background color of the token when it is selected.

* `IsCloseButtonVisible` - Enables and disables the close button inside SfAutoComplete.

* `DeleteButtonColor` - sets the color of the close button inside SfAutoComplete.

* `CornerRadius` - sets the corner radius for the token.

{% tabs %}

{% highlight C# %}



TokenSettings token = new TokenSettings();
        token.FontSize = 16;
        token.BackgroundColor = Color.FromHex("#d3d3d3");
        token.TextColor = Color.Red;
        token.SelectedBackgroundColor = Color.FromHex("#ffffe0");
        token.DeleteButtonColor = Color.Brown;
         token.FontFamily= "Times New Roman";
        token.IsCloseButtonVisible = true;
        token.CornerRadius = 3;
        countryAutoComplete.TokenSettings = token;
        

{% endhighlight %}

{% endtabs %}


![](images/Token_iOS.png)

## Delimiter

When selecting the multiple items, the selected items can be divided with a desired character given for a delimiter. We can set delmiter character with the `Delimiter` property.

{% tabs %}

{% highlight C# %}

	NSMutableArray countryList=new NSMutableArray();
	countryList.Add((NSString)"Afghanistan");
	countryList.Add((NSString)"Algeria");
	countryList.Add((NSString)"Andorra"); 
	countryList.Add((NSString)"Angola"); 
	countryList.Add((NSString)"Antarctica");
	countryList.Add((NSString)"Argentina");  
	countryList.Add((NSString)"America"); 
	countryAutoComplete.AutoCompleteSource=countryList;
	countryAutoComplete.MultiSelectMode=MultiSelectMode.Delimiter;
	countryAutoComplete.Delimiter="*";

{% endhighlight %}

{% endtabs %}

![](images/Delimiter.png)

