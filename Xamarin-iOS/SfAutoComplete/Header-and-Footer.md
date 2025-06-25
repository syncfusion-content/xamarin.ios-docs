---
layout : post
title : Header and Footer in Syncfusion® SfAutoComplete control for Xamarin.iOS
description : Learn how to enable Header and Footer in SfAutoComplete
platform : xamarin.ios 
control : AutoComplete
documentation : ug
---

# Header and Footer

You can provide header and footer views in the suggestion list in SfAutoComplete by enabling `ShowDropDownHeaderView` and `ShowDropDownFooterView`.

## Header Content

You can provide header content at the top of the AutoComplete's suggestion box. The `DropDownHeaderView` property is used to set the content of the header. The following code example illustrates how to set header content in SfAutoComplete. The height of the header in the SfAutoComplete can be adjusted using the `DropDownHeaderViewHeight` property.

{% tabs %}

{% highlight C# %}

// Shows the header view
countryAutoComplete.ShowDropDownHeaderView = true;

// Set height of the header view
countryAutoComplete.DropDownHeaderViewHeight = 50;
UILabel label = new UILabel();
label.Text = "Search for U";
label.TextColor = UIColor.Blue;
countryAutoComplete.DropDownHeaderView = label;


{% endhighlight %}

{% endtabs %}

![Header view in AutoComplete](images/Header.png)
## Footer Content

You can provide footer content at the bottom of the AutoComplete's suggestion box. The `DropDownFooterView` property is used to set the content of the footer. The following code example illustrates how to set footer content in SfAutoComplete. The height of the footer in the SfAutoComplete can be adjusted using the `DropDownFooterViewHeight` property.


{% tabs %}

{% highlight C# %}

// Shows the footer view
countryAutoComplete.ShowDropDownFooterView = true;

// Set height of the footer view
countryAutoComplete.DropDownFooterViewHeight = 50;
UILabel label = new UILabel();
label.Text = "Add New";
label.TextColor = UIColor.Blue;
countryAutoComplete.DropDownFooterView = label;

{% endhighlight %}

{% endtabs %}

![Footer view in AutoComplete](images/Footer.png)
