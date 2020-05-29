---
layout: post
title: Looping support in Syncfusion pikcer control for Xamarin.iOS
description: This section will explain about how to enable looping in Syncfusion Picker control for Xamarin.iOS platform.
platform: Xamarin.iOS
control: Picker
documentation: ug
---

# Looping support in SfPicker

Looping support in SfPicker control.

## EnableLooping

The looping support is used to automatically navigate the first item to repeat the list of items after reached the last item. Each forward iteration is followed by a backward iteration in the picker control. This can be achieved by `EnableLooping` property.

{% tabs %}

{% highlight C# %}

picker.EnableLooping = true;

{% endhighlight %}

{% endtabs %}

## How to restrict Looping in 

The looping support can be restricted in a particular column of the picker by setting the `EnableLooping` of ColumnLoaded event argument to false.

{% tabs %}

{% highlight C# %}

private void Picker_OnColumnLoaded(object sender, ColumnLoadedEventArgs e)
{
    if (e.Column == 0)
    {
        e.EnableLooping = true;
    }
    else
        e.EnableLooping = false;
}

{% endhighlight %}

{% endtabs %}

You can find the sample from the following [link.](https://www.syncfusion.com/downloads/support/directtrac/general/ze/EnableLooping-2017939801.zip)