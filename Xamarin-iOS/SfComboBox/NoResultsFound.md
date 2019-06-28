---
layout : post
title : No Result Found Text in Syncfusion SfComboBox control for Xamarin.iOS
description : Learn how to display the no result found text in SfComboBox
platform : Xamarin.iOS 
control : ComboBox
documentation : ug
---

# No Results Found

When the entered item is not in the suggestion list, SfComboBox displays a text indicating there is no search results found. We can set the desire text to be displayed for indicating no results found with the `NoResultsFoundText` property.

{% tabs %}

{% highlight C# %}

comboBox.NoResultsFoundText = "No Results Found";
comboBox.SuggestionMode = SuggestionMode.StartsWith;

{% endhighlight %}

{% endtabs %}

![NoResultsFound](images/NoResultsFound.png)

## Customizing NoResultsFoundText

The `NoResultsFoundTextColor` and `NoResultsFoundFont` are the properties used to customize the foreground color and font of the NoResultsFoundText.

{% tabs %}

{% highlight c# %}

comboBox.SuggestionMode = SuggestionMode.StartsWith;
comboBox.NoResultsFoundText = "No Results Found";
comboBox.NoResultsFoundTextColor = UIColor.Blue;
comboBox.NoResultsFoundFont = UIFont.FromName("Pacifico", 20);

{% endhighlight %}

{% endtabs %}

![NoResultsFound_Customization](images/NoResultsFound_Customization.png)
