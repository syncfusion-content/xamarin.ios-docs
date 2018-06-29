---
layout: post
title: Event in SfCheckBox for Xamarin.iOS platform
description: Learn how to customize the basic features of SfCheckBox
platform: Xamarin.iOS
control: SfCheckBox
documentation: ug 
keywords: button, SfCheckBox, CheckBox

---

# Event

## StateChanged event
Occurs when the value(state) of the `IsChecked` property is changed by either touching the check box or setting the value to the `IsChecked` property using C# code. The event arguments are of type `StateChangedEventArgs` and expose the following property:

* `IsChecked`: The new value(state) of the `IsChecked` property.

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

![](Images/Event1.png)
![](Images/Event2.png)
![](Images/Event3.png)

This demo can be downloaded from this [link](http://files2.syncfusion.com/Xamarin.iOS/Samples/CheckBox_Event.zip).