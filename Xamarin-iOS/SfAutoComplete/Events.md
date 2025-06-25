---
layout : post
title : Events in Syncfusion® SfAutoComplete control for Xamarin.iOS
description :  Learn how to handle the Events in SfAutoComplete
platform : xamarin.ios 
control : AutoComplete
documentation : ug
---

# Events

The events in SfAutoComplete are:

* FocusChanged

* SelectionChanged

* SelectionChanging

* TextChanged

* FilterCollectionChanged

## FocusChanged

The `FocusChanged` event occurs when the control gains focus or loses focus. The event argument contains the following information:

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>HasFocus</td>
<td>Indicates whether the control is in a focused state or not.</td>
</tr>
</table>

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

The `SelectionChanged` event is triggered after selecting an item from the filtered suggestions in SfAutoComplete.

The SelectionChanged event returns the following arguments:

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>AddedItems</td>
<td>Shows the recently added item in AutoComplete.</td>
</tr>
<tr>
<td>RemovedItems</td>
<td>Shows the recently removed items in AutoComplete.</td>
</tr>
<tr>
<td>Value</td>
<td>Holds all selected items in AutoComplete.</td>
</tr>
</table>

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

The `SelectionChanging` event is triggered when you select an item from the filtered suggestions in SfAutoComplete.

The SelectionChanging event returns the following arguments:

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>Value</td>
<td>Holds all selecting items in AutoComplete.</td>
</tr>
<tr>
<td>Cancel</td>
<td>Restricts the item from being selected.</td>
</tr>
</table>

{% tabs %}

{% highlight c# %}

 autocomplete.SelectionChanging += Autocomplete_SelectionChanging;

 void Autocomplete_SelectionChanging(object sender,SelectionChanging EventArgs e) 
 {

 DisplayAlert("Alert", "Selection Changing", "Ok");

 }

{% endhighlight %}

{% endtabs %}

## TextChanged 

The `TextChanged` event is triggered when you change the text of SfAutoComplete.

The TextChanged event returns the following argument:

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>Value</td>
<td>Holds the text of AutoComplete.</td>
</tr>
</table>

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

The `FilterCollectionChanged` event is triggered whenever items are filtered in the suggestion list.

The FilterCollectionChanged event returns the following argument:

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>Value</td>
<td>Holds the filtered items in the suggestion list.</td>
</tr>
</table>

{% tabs %}

{% highlight c# %}

 autocomplete.FilterCollectionChanged += Autocomplete_FilterCollectionChanged;

 void Autocomplete_FilterCollectionChanged(object sender, FilterCollectionChangedEventArgs e)
 {
 
 DisplayAlert("Alert", "FilterCollectionChanged", "Ok");
  
 }

{% endhighlight %}

{% endtabs %}