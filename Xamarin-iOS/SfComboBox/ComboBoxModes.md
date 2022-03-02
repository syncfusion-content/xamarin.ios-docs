---
layout : post
title: ComboBoxModes in Syncfusion ComboBox control for Xamarin.iOS
description: Learn here about ComboBoxModes in Syncfusion Essential Xamarin.iOS ComboBox control, its elements, and more.
platform: Xamarin.iOS
control: ComboBox
documentation: ug
---

# ComboBoxModes in Xamarin.iOS ComboBox

The control provides you an option to show or select the dropdown items either by editing or non-editing the combobox textbox. The two combo box modes are, 

* Editable  

* Non-Editable 

## Editable 

In editable mode the user can select an item from the dropdown list by either typing any string or clicking the dropdown button.

{% highlight C# %}

combobox.IsEditable = true;

{% endhighlight %}

![Xamarin.iOS ComboBox Editable](images/editable.png)

## Non-editable 

In non-editable mode users can select an item from the dropdown list only by clicking the drop-down button. 

N> The default ComboBoxModes is Non-Editable

{% highlight C# %}

combobox.IsEditable = false;

{% endhighlight %}

![Xamarin.iOS ComboBox Non editable](images/noneditable.png)