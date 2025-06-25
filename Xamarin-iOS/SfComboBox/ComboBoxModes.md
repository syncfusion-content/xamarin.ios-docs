---
layout : post
title: ComboBox Modes in Syncfusion® ComboBox control for Xamarin.iOS
description: Learn here about ComboBox modes in Syncfusion® Essential® Xamarin.iOS ComboBox control, its elements, and more.
platform: xamarin.ios
control: ComboBox
documentation: ug
---

# ComboBox Modes in Xamarin.iOS ComboBox

The control provides an option to show or select the dropdown items either by editing or non-editing the ComboBox text box. The two ComboBox modes are:

* Editable  

* Non-Editable 

## Editable 

In editable mode, the user can select an item from the dropdown list by either typing any string or clicking the dropdown button.

{% highlight C# %}

combobox.IsEditable = true;

{% endhighlight %}

![Xamarin.iOS ComboBox Editable](images/editable.png)

## Non-Editable

In non-editable mode, users can select an item from the dropdown list only by clicking the dropdown button.

N> The default ComboBox mode is Non-Editable.

{% highlight C# %}

combobox.IsEditable = false;

{% endhighlight %}

![Xamarin.iOS ComboBox Non editable](images/noneditable.png)