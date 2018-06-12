---
layout : post
title : Getting Started with Syncfusion ComboBox control for Xamarin.iOS
description : A quick tour to initial users on Syncfusion combobox control for Xamarin.iOS platform 
platform : Xamarin.iOS
control : ComboBox
documentation : ug
---

# Getting started

This section explains how to create a simple ComboBox component and configure its available functionalities in Xamarin.iOS. 

## Referencing Essential Studio components in your solution

After installing Essential Studio for Xamarin, find all the required assemblies in the installation folders, 

{Syncfusion Installed location}\Essential Studio {version number}\lib

The assembly reference to the iOS unified project is follows.

iOS-unifed\Syncfusion.SfComboBox.iOS.dll

## Adding SfComboBox

* Add namespace for the added assemblies.

{% tabs %}

{% highlight C# %}

using Syncfusion.iOS.ComboBox; 

{% endhighlight %}

{% endtabs %}

* Then add the SfComboBox control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight C# %}

SfComboBox sfCombo = new SfComboBox(); 
this.Add(sfCombo); 
 
{% endhighlight %}

{% endtabs %}


## Adding items

A list of string with country names are created and added to combobox source. This list will be populated as dropdown list.

{% tabs %}

{% highlight C# %}

NSMutableArray countryList = new NSMutableArray();          
countryList.Add((NSString)"Argentina"); 
countryList.Add((NSString)"Australia"); 
countryList.Add((NSString)"Belgium"); 
countryList.Add((NSString)"Brazil"); 
countryList.Add((NSString)"Canada"); 
countryList.Add((NSString)"China"); 
countryList.Add((NSString)"Denmark"); 
countryList.Add((NSString)"Dominica"); 
sfCombo.ComboBoxSource = countryList; 

{% endhighlight %}

{% endtabs %}

![](images/gettingstarted.png)