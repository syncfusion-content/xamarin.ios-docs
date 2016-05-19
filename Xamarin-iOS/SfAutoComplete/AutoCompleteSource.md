---
layout : post
title : AutoCompleteSource mode for Syncfusion AutoComplete control in Xamarin.iOS
description : Learn how to use AutoCompleteSource in AutoComplete
platform : Xamarin.iOS 
control : AutoComplete
documentation : ug
---

# AutoCompleteSource Mode

* The `AutoCompleteSource` property in the AutoComplete control is used to set the list of strings to the suggestions dropdown using dataAdapter.

* To create a Text Box that automatically completes input strings by comparing the prefix being entered to the prefixes of all strings in a maintained source. This is useful for Text Box controls in which URLs, addresses, file names, or commands will be frequently entered.

* The use of this is optional, but you must set this to Custom Source in order to use AutoCompleteCustomSource.

{% highlight C# %}

	NSMutableArray countryList=new NSMutableArray();
	countryList.Add((NSString)"Afghanistan");
	countryList.Add((NSString)"Akrotiri");
	countryList.Add((NSString)"Albania"); 
	countryAutoComplete.AutoCompleteSource=countryList;

{% endhighlight %}


![](images/autocompletesource.png)
