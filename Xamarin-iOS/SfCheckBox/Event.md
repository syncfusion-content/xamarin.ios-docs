---
layout: post
title: Event in Syncfusion® SfCheckBox for Xamarin.iOS
description: Learn how to handle and customize events in SfCheckBox including state change, click, and validation event handling
platform: xamarin.ios
control: SfCheckBox
documentation: ug 
keywords: button, SfCheckBox, CheckBox

---

# Events

## StateChanged event
The `StateChanged` event occurs when the value (state) of the `IsChecked` property is changed by either touching the checkbox or setting the value to the `IsChecked` property using C# code. The event arguments are of type `StateChangedEventArgs` and expose the following property:

* `IsChecked`: The new value (state) of the `IsChecked` property.

{% tabs %}
{% highlight c# %}
SfCheckBox checkBox = new SfCheckBox();
checkBox.SetTitle("Unchecked State", UIControlState.Normal);
checkBox.IsThreeState = true;
checkBox.StateChanged += CheckBox_StateChanged;

private void CheckBox_StateChanged(object sender, StateChangedEventArgs e)
{
    if (e.IsChecked.HasValue && e.IsChecked.Value)
    {
         checkBox.SetTitle("Checked State", UIControlState.Normal);
    }
    else if(e.IsChecked.HasValue && !e.IsChecked.Value)
    {
         checkBox.SetTitle("Unchecked State", UIControlState.Normal);
    }
    else
    {
         checkBox.SetTitle("Indeterminate State", UIControlState.Normal);
    }
}
		
{% endhighlight %}
{% endtabs %}

![StateChanged event - Unchecked state](Images/Event1.png)
![StateChanged event - Checked state](Images/Event2.png)
![StateChanged event - Indeterminate state](Images/Event3.png)
This demo can be downloaded from this [link](http://files2.syncfusion.com/Xamarin.iOS/Samples/CheckBox_Event.zip).