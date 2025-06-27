---
layout: post
title: Syncfusion® SfComboBox Suggestion Box Placement
description: Learn how to configure and customize the suggestion box placement in Syncfusion® SfComboBox for Xamarin.iOS applications with various positioning options.
platform: xamarin.ios 
control: ComboBox
documentation: ug
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

![Suggestion box positioned at bottom](images/bottom.png)

## Suggestion Box Placement at Top

Displays the suggestion box at the top of the ComboBox control.
 
{% tabs %}
{% highlight c# %}

combobox.SuggestionBoxPlacement = SuggestionBoxPlacement.Top; 
 
{% endhighlight %}
{% endtabs %}

![Suggestion box positioned at top](images/top.png)