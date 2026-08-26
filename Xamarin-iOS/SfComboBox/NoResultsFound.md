---
layout : post
title : No Results Found Text in Syncfusion® SfComboBox control for Xamarin.iOS
description : Learn how to display the no results found text in SfComboBox
platform : xamarin.ios
control : ComboBox
documentation : ug
---

# No Results Found

When the entered item is not in the suggestion list, SfComboBox displays text indicating that no search results were found. You can set the desired text to be displayed for indicating no results found using the `NoResultsFoundText` property.

{% tabs %}

{% highlight C# %}

comboBox.NoResultsFoundText = "No Results Found";
comboBox.SuggestionMode = SuggestionMode.StartsWith;

{% endhighlight %}

{% endtabs %}

![NoResultsFound](images/NoResultsFound.png)

## Customizing NoResultsFoundText

The `NoResultsFoundTextColor` and `NoResultsFoundFont` properties are used to customize the foreground color and font of the NoResultsFoundText.

{% tabs %}

{% highlight c# %}

comboBox.SuggestionMode = SuggestionMode.StartsWith;
comboBox.NoResultsFoundText = "No Results Found";
comboBox.NoResultsFoundTextColor = UIColor.Blue;
comboBox.NoResultsFoundFont = UIFont.FromName("Pacifico", 20);

{% endhighlight %}

{% endtabs %}

![NoResultsFound_Customization](images/NoResultsFound_Customization.png)
