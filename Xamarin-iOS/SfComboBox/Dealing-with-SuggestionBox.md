---
layout : post
title : Suggestion Box Placement in Syncfusion® SfComboBox control for Xamarin.iOS
description : Learn how to place the suggestion box in SfComboBox
platform : xamarin.ios 
control : ComboBox
documentation : ug
---

# Dealing with Suggestion Box
In the ComboBox control, the dropdown box can be placed in the following two positions:

* Bottom 

* Top 

Using the `SuggestionBoxPlacement` property, you can place the suggestion box at the top or bottom.

## Suggestion Box Placement at Bottom

Displays the suggestion box at the bottom of the ComboBox control.
 
{% tabs %}
{% highlight c# %}

combobox.SuggestionBoxPlacement = SuggestionBoxPlacement.Bottom; 
 
{% endhighlight %}
{% endtabs %}

![](images/bottom.png)

## Suggestion Box Placement at Top

Displays the suggestion box at the top of the ComboBox control.
 
{% tabs %}
{% highlight c# %}

combobox.SuggestionBoxPlacement = SuggestionBoxPlacement.Top; 
 
{% endhighlight %}
{% endtabs %}

![](images/top.png)