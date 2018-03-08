---
layout : post
title : Header and Footer in Syncfusion SfAutoComplete control for Xamarin.iOS
description :   Learn how to enable Header and Footer in SfAutoComplete
platform : Xamarin.iOS 
control : AutoComplete
documentation : ug
---

# Header and Footer

We can provide Header and Footer view in the suggestion list in SfAutoComplete by enabling `ShowDropDownHeaderView` and `ShowDropDownFooterView`. 

## Header Content

We can provide Header Content at the top of the AutoComplete's Suggestion box. `DropDownHeaderView` property is used to set the content of the header. The following code example illustrate how to set Header content in SfAutoComplete. The height of the Header in the SfAutoComplete can be adjusted by the property `DropDownHeaderViewHeight`.

{% tabs %}

{% highlight C# %}

	NSMutableArray country=new NSMutableArray();
	country.Add((NSString)"Ukraine");
	country.Add((NSString)"Uganda");
	country.Add((NSString)"United Arab Emirates");
	country.Add((NSString)"United Kingdom"); 
	country.Add((NSString)"United States"); 
	countryAutoComplete.AutoCompleteSource=country;
	countryAutoComplete.SuggestionMode=SuggestionMode.StartsWith;
	countryAutoComplete.ShowDropDownHeaderView = true;

	//Set height of the Header view

	countryAutoComplete.DropDownHeaderViewHeight = 50;
	UILabel label = new UILabel();
	label.Text = "Search for U";
	label.TextColor = UIColor.Blue;
	countryAutoComplete.DropDownHeaderView = label;


{% endhighlight %}

{% endtabs %}

![](images/Header.png)

## Footer Content

We can provide Footer Content at the bottom of the AutoComplete's Suggestion box. `DropDownFooterView` property is used to set the content of the footer. The following code example illustrate how to set Footer content in SfAutoComplete. The height of the Header in the SfAutoComplete can be adjusted by the property `DropDownFooterViewHeight`.


{% tabs %}

{% highlight C# %}

	NSMutableArray country=new NSMutableArray();
	country.Add((NSString)"Uganda");
	country.Add((NSString)"Ukraine");
	country.Add((NSString)"United Arab Emirates");
	country.Add((NSString)"United Kingdom"); 
	country.Add((NSString)"United States"); 
	countryAutoComplete.AutoCompleteSource=country;
	countryAutoComplete.SuggestionMode=SuggestionMode.StartsWith;
	countryAutoComplete.ShowDropDownFooterView = true;

   //Set height of the Footer view
	countryAutoComplete.DropDownFooterViewHeight = 50;
   
	UILabel label = new UILabel();
	label.Text = "Add New";
	label.TextColor = UIColor.Blue;
	countryAutoComplete.DropDownFooterView = label;


{% endhighlight %}

{% endtabs %}

![](images/Footer.png)
