---
layout : post
title : Suggestionbox Placement in Syncfusion SfComboBox control for Xamarin.iOS
description : Learn how to place the Suggestion Box in SfComboBox
platform : Xamarin.iOS 
control : ComboBox
documentation : ug
---

# Dealing with suggestion box 
In the combobox control, the DropDown Box can placed in the following two positions:

* Bottom 

* Top 

Using the Suggestion box placement property, you can place the suggestion box at the top or bottom. 

## SuggestionBox placement at bottom

Displays the suggestion box at the bottom of the combo box control. 
 
{% tabs %}
{% highlight c# %}

combobox.SuggestionBoxPlacement = SuggestionBoxPlacement.Bottom; 
 
{% endhighlight %}
{% endtabs %}

![](images/bottom.png)

## SuggestionBox placement at top

Displays the suggestion box at the top of the combo box control. 
 
{% tabs %}
{% highlight c# %}

combobox.SuggestionBoxPlacement = SuggestionBoxPlacement.Top; 
 
{% endhighlight %}
{% endtabs %}

![](images/top.png)