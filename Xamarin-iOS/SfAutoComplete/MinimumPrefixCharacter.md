---
layout : post
title : MinimumPrefixCharacters for Syncfusion AutoComplete control in Xamarin.iOS
description : Learn how to set the MinimumPrefixCharacter in AutoComplete
platform : Xamarin.iOS
control : AutoComplete
documentation : ug
---

# MinimumPrefixCharacter

* The minimum number of characters to be entered in the text box before the suggestion box displays possible matches. 

* The SfAutoCompete suggestion box will not provide possible matches if the `MinimumPrefixCharacter` property value is -1. There is no maximum value, but setting MinimumPrefixCharacter to value that is too large will prevent the suggestion box from providing possible matches as well.

N> Population of the suggestion box does not occur until the conditions specified by the `MinimumPrefixCharacter` property values are met.The default value is 1.

{% highlight C# %}

	countryAutocomplete.MinimumPrefixCharacters=2;

{% endhighlight %}

![](images/minimumprefixcharacter.png)
