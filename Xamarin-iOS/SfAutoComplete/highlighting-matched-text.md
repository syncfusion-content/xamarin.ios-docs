---
layout: post
title: Syncfusion® SfAutoComplete Match Highlighting for iOS
description: Learn how to enable and customize text highlighting for matched text in SfAutoComplete control to enhance user search experience.
platform: xamarin.ios
control: AutoComplete
documentation: ug
---

# Highlighting Matched Text

Highlight matching characters in a suggestion list to pick an item with more clarity. There are two ways to highlight the matching text:


* FirstOccurrence

* MultipleOccurrence

The text highlight can be customized with various styling options by configuring the following properties:

* **HighlightedTextColor** - Sets the color of the highlighted text for differentiating the highlighted characters.
* **HighlightTextFontAttributes** - Sets the FontAttributes of the highlighted text.

N> The default color of HighlightedTextColor is Blue and the default FontAttribute of HighlightTextFontAttributes is None.

## FirstOccurrence

This mode highlights the first position of the matching characters in the suggestion list.

{% tabs %}

{% highlight C# %}

countryAutoComplete.TextHighlightMode=OccurrenceMode.FirstOccurrence;
countryAutoComplete.SuggestionMode=SuggestionMode.StartsWith;
countryAutoComplete.HighlightedTextColor = UIColor.Red;
countryAutoComplete.AutoCompleteSource=countryList;

{% endhighlight %}

{% endtabs %}

![First occurrence of matched text highlighted](images/FirstOccurrence.png)

## MultipleOccurrence

This mode highlights all matching characters that are present throughout the suggestion list when using the Contains mode in SuggestionMode.

{% tabs %}

{% highlight C# %}

countryAutoComplete.TextHighlightMode=OccurrenceMode.MultipleOccurrence;
countryAutoComplete.HighlightedTextColor = UIColor.Red;
countryAutoComplete.SuggestionMode=SuggestionMode.Contains;
countryAutoComplete.AutoCompleteSource=countryList;

{% endhighlight %}

{% endtabs %}

![Multiple occurrences of matched text highlighted](images/MultipleOccurrence.png)

