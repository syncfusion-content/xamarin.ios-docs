---
layout: post
title: Getting Started with Syncfusion® AutoComplete for Xamarin.iOS
description: Learn here about getting started with Syncfusion® Essential® Xamarin.iOS AutoComplete Control, its elements, and more.
platform: xamarin.ios
control: AutoComplete
documentation: ug
---

# Getting Started with Xamarin.iOS AutoComplete

This section explains the steps to configure an SfAutoComplete control in a real-time scenario and also provides a walk-through of some of the customization features available in the SfAutoComplete control.

## Referencing Essential Studio<sup>®</sup> Components in Your Solution

After installing Essential Studio<sup>®</sup> for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio {version number}\lib

Add the following assembly reference to the iOS unified project:

iOS-unifed\Syncfusion.SfAutoComplete.iOS.dll

## Add SfAutoComplete

* Add the namespace for the added assemblies.

{% tabs %}

{% highlight C# %}

	using Syncfusion.SfAutoComplete.iOS; 

{% endhighlight %}

{% endtabs %}

* Now add the SfAutoComplete control with a required optimal name using the included namespace.

{% tabs %}

{% highlight C# %}

SFAutoComplete countryAutoComplete=new SFAutoComplete(); 
this.AddSubview(countryAutoComplete); 

{% endhighlight %}

{% endtabs %}


## Add Items

A list of strings with country names is created and added to the AutoComplete source. This list will be populated as a suggestion list based on text entry.

{% tabs %}

{% highlight C# %}

NSMutableArray countryList=new NSMutableArray();
countryList.Add((NSString)"Uganda");
countryList.Add((NSString)"Ukraine");
countryList.Add((NSString)"United Arab Emirates"); 
countryList.Add((NSString)"United Kingdom");
countryList.Add((NSString)"United States"); 
countryAutoComplete.AutoCompleteSource= countryList;

{% endhighlight %}

{% endtabs %}

## Set Filter Mode

Filters can be applied to the displayed items based on the starting letter. You can also append the first item from the suggested list to the TextBox. This can be achieved by using the `SuggestionMode` and `AutoCompleteMode` properties in the SfAutoComplete control.

The following example shows the SfAutoComplete control which suggests countries from the list starting with the letter "U".

{% tabs %}

{% highlight C# %}

countryAutoComplete.SuggestionMode=SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeStartsWith;
countryAutoComplete.Watermark=(NSString)"Enter a country name";
countryAutoComplete.MaxDropDownHeight=90;
countryAutoComplete.AutoCompleteMode=SFAutoCompleteAutoCompleteMode.SFAutoCompleteAutoCompleteModeSuggest; 
countryAutoComplete.PopUpDelay = 100; 

{% endhighlight %}

{% endtabs %}

![Xamarin.iOS AutoComplete Getting Started Set Filter mode](images/gettingstarted.png)