---
layout : post
title : ComboBoxModes in Syncfusion ComboBox control for Xamarin.iOS
description : Various ComboBoxModes in ComboBox
platform : Xamarin.iOS
control : ComboBox
documentation : ug
---

# ComboBoxModes

The control provides you an option to show or select the dropdown items either by editing or non-editing the combobox textbox. The two combo box modes are, 

* Editable  

* Non-Editable 

## Editable 

In editable mode the user can select an item from the dropdown list by either typing any string or clicking the dropdown button.

{% highlight C# %}

sfCombo.IsEditable = true;

{% endhighlight %}

![](images/editable.png)

## Non-editable 

In non-editable mode users can select an item from the dropdown list only by clicking the drop-down button. 

N> The default ComboBoxModes is Non-Editable

{% highlight C# %}

sfCombo.IsEditable = false;

{% endhighlight %}

![](images/noneditable.png)