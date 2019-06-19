---
layout : post
title : Events in Syncfusion SfAutoComplete control for Xamarin.iOS
description :  Learn how to handle the Events in SfComboBox
platform : Xamarin.iOS 
control : AutoComplete
documentation : ug
---

# Events

The Events in SfAutoComplete are,

* FocusChanged

* SelectionChanged

* SelectionChanging

* TextChanged

* FilterCollectionChanged

## FocusChanged

`FocusChanged` event is triggered when we either focus or unfocus the control. The argument contains the following information.

* `HasFocus` - It indicates the control whether in focus state or not. HasFocus value is true while focusing the control. otherwise it becomes false.

Code snippet of FocusChanged event:

{% tabs %}

{% highlight c# %}

 autocomplete.FocusChanged += Autocomplete_FocusChanged;

 void Autocomplete_FocusChanged(object sender, FocusEventArgs e)
        {
            if (e.HasFocus)
            {
                DisplayAlert("Alert", "Focus", "Ok");
            }
            else
            {
                DisplayAlert("Alert", "UnFocus", "Ok");
            }
        }
 

{% endhighlight %}

{% endtabs %}
 

## SelectionChanged

`SelectionChanged` event is triggered after selecting an item among the filtered suggestions in SfAutoComplete.

Code snippet of SelectionChanged event:

{% tabs %}

{% highlight c# %}

 autocomplete.SelectionChanged += Autocomplete_SelectionChanged;

 void Autocomplete_SelectionChanged(object sender, SelectionEventArgs e)
 {

 DisplayAlert("Alert", "Item Selected", "Ok");

 }

{% endhighlight %}

{% endtabs %}
 

## SelectionChanging

`SelectionChanging` event is triggered when we selecting an item among the filtered suggestions in SfAutoComplete.

Code snippet of SelectionChanged event:

{% tabs %}

{% highlight c# %}

 autocomplete.SelectionChanging+=Autocomplete_SelectionChanging;

 void Autocomplete_SelectionChanging(object sender,SelectionChanging EventArgse) 
 {

 DisplayAlert("Alert", "Selection Changing", "Ok");

 }

{% endhighlight %}

{% endtabs %}

## TextChanged 

`TextChanged` event is triggered when we changing the text of SfAutoComplete.

Code snippet of TextChanged event:

{% tabs %}

{% highlight c# %}

 autocomplete.TextChanged += Autocomplete_TextChanged;

 void Autocomplete_TextChanged(object sender, TextEventArgs e)
 {

 DisplayAlert("Alert", "Text Changed", "Ok");

 }

{% endhighlight %}

{% endtabs %}

## FilterCollectionChanged

`FilterCollectionChanged` event is triggered whenever the items gets filtered in the suggestion.

Code snippet of FilterCollectionChanged event:

{% tabs %}

{% highlight c# %}

 autocomplete.FilterCollectionChanged += Autocomplete_FilterCollectionChanged;

 void Autocomplete_FilterCollectionChanged(object sender, TextEventArgs e)
 {

 DisplayAlert("Alert", "FilterCollectionChanged", "Ok");

 }

{% endhighlight %}

{% endtabs %}