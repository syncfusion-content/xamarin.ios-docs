---
layout : post
title : Events in Syncfusion SfAutoComplete control for Xamarin.iOS
description :  Learn how to handle the Events in SfAutoComplete
platform : Xamarin.iOS 
control : AutoComplete
documentation : ug
---

# Events

The Events in SfAutoComplete are:

* FocusChanged

* SelectionChanged

* SelectionChanging

* TextChanged

* FilterCollectionChanged

## FocusChanged

The `FocusChanged` event occurs when the control gets the focus and loses the focus. The argument contains the following information.

* `HasFocus`: Indicates the control whether in focus state or not. HasFocus value is true while focusing the control. otherwise it becomes false.

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

The `SelectionChanged` event is triggered after selecting an item among the filtered suggestions in SfAutoComplete.

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

The `SelectionChanging` event is triggered when you select an item among the filtered suggestions in SfAutoComplete.

{% tabs %}

{% highlight c# %}

 autocomplete.SelectionChanging += Autocomplete_SelectionChanging;

 void Autocomplete_SelectionChanging(object sender,SelectionChanging EventArgse) 
 {

 DisplayAlert("Alert", "Selection Changing", "Ok");

 }

{% endhighlight %}

{% endtabs %}

## TextChanged 

The `TextChanged` event is triggered when you change the text of SfAutoComplete.

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

The `FilterCollectionChanged` event is triggered whenever the items gets filtered in the suggestion.

{% tabs %}

{% highlight c# %}

 autocomplete.FilterCollectionChanged += Autocomplete_FilterCollectionChanged;

 void Autocomplete_FilterCollectionChanged(object sender, TextEventArgs e)
 {

 DisplayAlert("Alert", "FilterCollectionChanged", "Ok");

 }

{% endhighlight %}

{% endtabs %}