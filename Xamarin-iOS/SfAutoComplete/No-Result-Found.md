---
layout: post
title: No Results Found Text in Syncfusion® SfAutoComplete control for Xamarin.iOS
description: Learn how to display the no results found text in SfAutoComplete
platform: xamarin.ios
control: AutoComplete
documentation: ug
---

# No Results Found

When the entered item is not in the suggestion list, SfAutoComplete displays text indicating that no search results were found. You can set the desired text to be displayed for indicating no results found using the `NoResultsFoundText` property.

{% tabs %}

{% highlight C# %}

countryAutoComplete.NoResultsFoundText = "No Results Found";
countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;

{% endhighlight %}

{% endtabs %}

![NoResultsFound](images/NoResultsFound.png)

## Customizing NoResultsFoundText

The `NoResultsFoundTextColor` and `NoResultsFoundFont` properties are used to customize the foreground color and font of the NoResultsFoundText.

{% tabs %}

{% highlight c# %}

countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
countryAutoComplete.NoResultsFoundText = "No Results Found";
countryAutoComplete.NoResultsFoundTextColor = UIColor.FromRGB(128,0,0);
countryAutoComplete.NoResultsFoundFont = UIFont.FromName("Pacifico", 20);

{% endhighlight %}

{% endtabs %}

![NoResultsFound_Customization](images/NoResultsFound_Customization.png)
