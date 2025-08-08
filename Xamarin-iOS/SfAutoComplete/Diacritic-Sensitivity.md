---
layout: post
title: Diacritic Sensitivity in Syncfusion® SfAutoComplete iOS
description: Learn how to enable and disable Diacritic sensitivity in SfAutoComplete control to handle accented characters.
platform: xamarin.ios 
control: AutoComplete
documentation: ug
---

# Diacritic Sensitivity

The control is not restricted to one type of keyboard, so you can populate items from a language with letters containing diacritics and search for them with English characters from an en-US keyboard. Users can enable or disable diacritic sensitivity using the `IgnoreDiacritic` property. In the code example below, we demonstrate how to enable diacritic sensitivity so that items in the suggestion list are populated by entering any diacritic character of that alphabet.

{% tabs %}

{% highlight C# %}

NSMutableArray diacritic=new NSMutableArray();
diacritic.Add((NSString)"Hów tó drâw ân éléphânt?");
diacritic.Add((NSString)"Whéré cân I buy â câmérâ?"); 
diacritic.Add((NSString)"Guidé mé âll thé wây"); 
diacritic.Add((NSString)"Sây, Hélló Wórld!"); 
diacritic.Add((NSString)"Hów tó mâké â róbót?"); 
diacritic.Add((NSString)"Whât timé nów in Indiâ?"); 
diacritic.Add((NSString)"Whó is whó in thé wórld?"); 

countryAutoComplete.AutoCompleteSource=diacritic;
countryAutoComplete.TextHighlightMode=OccurrenceMode.MultipleOccurrence;
countryAutoComplete.SuggestionMode=SuggestionMode.Contains;
countryAutoComplete.HighlightedTextColor = UIColor.Red;
countryAutoComplete.IgnoreDiacritic = false;

{% endhighlight %}

{% endtabs %}

![Diacritic sensitivity example](images/Diacritic.png)
