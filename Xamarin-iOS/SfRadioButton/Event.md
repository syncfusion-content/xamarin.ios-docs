---
layout: post
title: Event in Syncfusion SfRadioButton for Xamarin.iOS platform
description: Learn how to invoke the available event to notify the selection changes in Xamarin.iOS SfRadioButton
platform: Xamarin.iOS
control: SfRadioButton
documentation: ug 
keywords: button, SfRadioButton, RadioButton

---

# Event Xamarin.iOS RadioButton(SfRadioButton)

## StateChanged event

Occurs when the value(state) of the `IsChecked` property is changed by either touching the radio button or setting the value to the `IsChecked` property using the C# code. The event arguments are of type `StateChangedEventArgs` and expose the following property.

* `IsChecked`: The new value(state) of the `IsChecked` property.

{% tabs %}
{% highlight c# %}
 SfRadioGroup radioGroup = new SfRadioGroup();
SfRadioButton check = new SfRadioButton();
check.SetTitle("Checked State",UIControlState.Normal);
check.IsChecked = true;
check.StateChanged += RadioButton_StateChanged;
SfRadioButton uncheck = new SfRadioButton();
uncheck.SetTitle("Unchecked State",UIControlState.Normal);
uncheck.StateChanged += RadioButton_StateChanged;
radioGroup.AddArrangedSubview(check);
radioGroup.AddArrangedSubview(uncheck);

private void RadioButton_StateChanged(object sender, StateChangedEventArgs e)
{
    if (e.IsChecked.HasValue && e.IsChecked.Value)
    {
        (sender as SfRadioButton).SetTitle("Checked State",UIControlState.Normal);
    }
    else if (e.IsChecked.HasValue && !e.IsChecked.Value)
    {
       (sender as SfRadioButton).SetTitle("Unchecked State",UIControlState.Normal);
    }
}
 
{% endhighlight %}
{% endtabs %}

![RadioButton Event1](Images/Event1.png)
![RadioButton Event2](Images/Event2.png)