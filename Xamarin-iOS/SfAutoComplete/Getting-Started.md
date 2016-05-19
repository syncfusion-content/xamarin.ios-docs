---
layout : post
title : Getting Started with Syncfusion AutoComplete control for Xamarin.iOS
description : A quick tour to initial users on Syncfusion autocomplete control for Xamarin.iOS platform 
platform : Xamarin.iOS
control : AutoComplete
documentation : ug
---

# Getting Started

This section explains you the steps to configure a AutoComplete control in a real-time scenario and also provides a walk-through on some of the customization features available in AutoComplete control.

![](images/gettingstarted.png)

## Creating your first AutoComplete in Xamarin.iOS.

### Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio {version number}\lib

And below assembly reference to the iOS unified project.

ios-unifed\Syncfusion.SfAutoComplete.iOS.dll

### Add and configure the AutoComplete control

* Adding reference to Autocomplete.

{% highlight C# %}

	using Syncfusion.SfAutoComplete.iOS; 

{% endhighlight %}

* Create an instance of AutoComplete

{% highlight C# %}

	SFAutoComplete countryAutoComplete=new SFAutoComplete(); 
	this.AddSubview(countryAutoComplete); 

{% endhighlight %}


### Add the AutoCompleteSource for the AutoComplete. 

{% highlight C# %}

	NSMutableArray countryList=new NSMutableArray();
	countryList.Add((NSString)"Afghanistan");
	countryList.Add((NSString)"Akrotiri");
	countryList.Add((NSString)"Albania"); 
	countryAutoComplete.AutoCompleteSource= countryList;

{% endhighlight %}

### Customization of SfAutoComplete Properties

{% highlight C# %}

	countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeStartsWith;
	countryAutoComplete.Watermark=(NSString)"Enter a country name";
	countryAutoComplete.MaxDropDownHeight=90;
	countryAutoComplete.AutoCompleteMode=SFAutoCompleteAutoCompleteMode.SFAutoCompleteAutoCompleteModeSuggest; 
	countryAutoComplete.PopUpDelay = 100; 

{% endhighlight %}

