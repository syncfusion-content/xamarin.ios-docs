---
layout : post
title : ComboBoxMode mode for Syncfusion ComboBox control in Xamarin.iOS
description : Learn how to change the ComboBoxMode in SfComboBox 
platform : Xamarin.iOS
control : SfComboBox
documentation : ug
---

# Suggestion display mode

The `ComboBoxMode` property is used to decide the suggestion pattern for displaying the dropdown list according to the text entered. The different types of patterns are, described below

* Suggest

* Append

* Suggest and Append

N> The default option is suggest mode.

## Suggest in drop-down 

* Suggest - Displays suggestions in the drop-down.

{% tabs %}

{% highlight C# %}
	
combobox.ComboBoxMode = ComboBoxMode.Suggest;	

{% endhighlight %}

{% endtabs %}

![](images/suggest.png)

## Append

* Append - Appends the first matching string with the entered character.

{% tabs %}

{% highlight C# %}
	
combobox.ComboBoxMode = ComboBoxMode.Append;

{% endhighlight %}

{% endtabs %}

![](images/append.png)

## Both append and suggest in drop-down
	
* SuggestAppend - Displays suggestions in the drop-down along with appending the first matching string.

{% tabs %}

{% highlight C# %}
	
combobox.ComboBoxMode = ComboBoxMode.SuggestAppend;

{% endhighlight %}

{% endtabs %}

![](images/suggestappend.png)
 
