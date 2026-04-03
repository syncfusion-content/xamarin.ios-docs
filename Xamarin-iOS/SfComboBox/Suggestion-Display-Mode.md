---
layout : post
title : ComboBoxMode for Syncfusion® ComboBox control in Xamarin.iOS
description : Learn how to change the ComboBoxMode in SfComboBox for different suggestion display patterns
platform : xamarin.ios
control : SfComboBox
documentation : ug
---

# Suggestion Display Mode

The `ComboBoxMode` property determines how suggestions are displayed in the dropdown list based on the text entered by the user. The different types of patterns are described below:

* Suggest

* Append

* Suggest and Append

N> The default option is suggest mode.

## Suggest Mode

The **Suggest** mode displays matching suggestions in the dropdown list.

{% tabs %}

{% highlight C# %}
	
combobox.ComboBoxMode = ComboBoxMode.Suggest;	

{% endhighlight %}

{% endtabs %}

![Suggest mode example](images/suggest.png)

## Append Mode

The **Append** mode automatically appends the first matching string to the entered text.

{% tabs %}

{% highlight C# %}
	
combobox.ComboBoxMode = ComboBoxMode.Append;

{% endhighlight %}

{% endtabs %}

![Append mode example](images/append.png)

## Suggest and Append Mode

The **SuggestAppend** mode combines both behaviors: it displays suggestions in the dropdown while also appending the first matching string to the entered text.
{% tabs %}

{% highlight C# %}
	
combobox.ComboBoxMode = ComboBoxMode.SuggestAppend;

{% endhighlight %}

{% endtabs %}

![SuggestAppend mode example](images/suggestappend.png)
