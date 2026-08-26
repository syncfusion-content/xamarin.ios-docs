---
layout: post
title: Getting started in Syncfusion® CheckBox for Xamarin.iOS platform
description: Learn how to create a simple CheckBox and its customization options with its available basic features in Xamarin.iOS
platform: xamarin.ios
control: SfCheckBox
documentation: ug 
keywords: button, SfCheckBox, CheckBox

---

# Getting Started with Xamarin.iOS CheckBox (SfCheckBox)
This section explains the steps required to configure the `SfCheckBox` control in a real-time scenario and provides a walk-through on some of the customization features available in the `SfCheckBox` control.

## Add SfCheckBox reference
Syncfusion® Xamarin components are available in [nuget.org](https://www.nuget.org/). To add CheckBox to your project, open the NuGet package manager in Visual Studio, and search for "[syncfusion.xamarin.buttons.ios](https://www.nuget.org/packages/Syncfusion.Xamarin.Buttons.IOS)", and then install it.

![Xamarin.iOS CheckBox NuGet](Images/nuget.png)

N>Starting with v16.2.0.x, if you reference Syncfusion® assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to learn about registering Syncfusion® license key in your Xamarin application to use our components.

## Create a Simple SfCheckBox
The `SfCheckBox` control is configured entirely in C# code. The following steps explain how to create a `SfCheckBox` and configure its elements:

### Add namespace for referenced assemblies

{% tabs %}
{% highlight c# %}
using Syncfusion.iOS.Buttons;
{% endhighlight %}
{% endtabs %}

### Reference SfCheckBox control with declared suffix name for Namespace

{% tabs %}
{% highlight c# %}
using CoreGraphics;
using Syncfusion.iOS.Buttons;
using System;
using UIKit;

namespace CheckBox_Sample
{
    public partial class ViewController : UIViewController
    {
        public ViewController(IntPtr handle) : base(handle)
        {
        }

        public override void ViewDidLoad()
        {
            base.ViewDidLoad();
            SfCheckBox checkBox = new SfCheckBox();
            checkBox.Frame = new CGRect(10, 50, 350, 40);
            View.AddSubview(checkBox);
        }

        public override void DidReceiveMemoryWarning()
        {
            base.DidReceiveMemoryWarning();
            // Release any cached data, images, etc that aren't in use.
        }
    }
}
{% endhighlight %}
{% endtabs %}

## Setting caption
The CheckBox caption can be defined using the `SetTitle` method of `SfCheckBox`. This caption normally describes the meaning of the CheckBox and displays next to the CheckBox.

{% tabs %}
{% highlight c# %}
SfCheckBox checkBox = new SfCheckBox();
checkBox.IsChecked = true;
checkBox.SetTitle("CheckBox",UIControlState.Normal);
{% endhighlight %}
{% endtabs %}

![Xamarin.iOS CheckBox caption text](Images/Caption.png) 

## Change the CheckBox state

The three visual states of `SfCheckBox` are: 

* Checked
* Unchecked
* Indeterminate

![Xamarin.iOS CheckBox visual states](Images/States.png) 

You can change the state of the CheckBox using the `IsChecked` property of `SfCheckBox`. In the checked state, a tick mark is added to the visualization of the CheckBox.

<table>
<tr>
<td>
<b>State</b>
</td>
<td>
<b>Property</b>
</td>
<td>
<b>Value</b>
</td>
</tr>
<tr>
<td>
Checked
</td>
<td>
IsChecked
</td>
<td>
true
</td>
</tr>
<tr>
<td>
Unchecked
</td>
<td>
IsChecked
</td>
<td>
false
</td>
</tr>
<tr>
<td>
Indeterminate
</td>
<td>
IsChecked
</td>
<td>
null
</td>
</tr>
</table>

N>For the CheckBox to report the indeterminate state, set the `IsThreeState` property to true.

CheckBox can be used as a single control or as a group. A single CheckBox is mostly used for a binary yes/no choice, such as "Remember me?", login scenario, or a terms of service agreement.

{% tabs %}
{% highlight c# %}
SfCheckBox checkBox = new SfCheckBox();
checkBox.SetTitle("I agree to the terms of services for this site", UIControlState.Normal);
checkBox.IsChecked = true;
{% endhighlight %}
{% endtabs %}

![Xamarin.iOS CheckBox tri-state](Images/Agree.png)

Multiple CheckBoxes can be used as a group for multi-select scenarios in which a user chooses one or more items from the group of choices that are not mutually exclusive.

{% tabs %}
{% highlight c# %}
UITextView label = new UITextView();
label.Text = "Pizza Toppings";
SfCheckBox pepperoni = new SfCheckBox();
pepperoni.SetTitle("Pepperoni", UIControlState.Normal);
SfCheckBox beef = new SfCheckBox();
beef.SetTitle("Beef", UIControlState.Normal);
beef.IsChecked = true;
SfCheckBox mushroom = new SfCheckBox();
mushroom.SetTitle("Mushrooms", UIControlState.Normal);
SfCheckBox onion = new SfCheckBox();
onion.SetTitle("Onions", UIControlState.Normal);
onion.IsChecked = true;
{% endhighlight %}
{% endtabs %}

![Xamarin.iOS CheckBox states changes](Images/StateChange.png)


## Indeterminate

The `SfCheckBox` allows an indeterminate state in addition to the checked and unchecked states. The indeterminate state of the CheckBox is enabled by setting the `IsThreeState` property of the control to `true`.

N>When the `IsThreeState` property is set to `false` and the `IsChecked` property is set to `null`, then the CheckBox will be in the unchecked state.

The indeterminate state is used when a group of sub-choices has both checked and unchecked states. In the following example, the "Select all" CheckBox has the `IsThreeState` property set to `true`. The "Select all" CheckBox is checked if all child elements are checked, unchecked if all the child elements are unchecked, and indeterminate otherwise.

{% tabs %}
{% highlight c# %}

bool skip = false;
SfCheckBox selectAll, pepperoni, beef, mushroom, onion;

public override void ViewDidLoad()
{
            
base.ViewDidLoad();
...

selectAll = new SfCheckBox();
selectAll.StateChanged += SelectAll_StateChanged;
selectAll.SetTitle("Select All",UIControlState.Normal);
pepperoni = new SfCheckBox();
pepperoni.StateChanged += CheckBox_StateChanged;
pepperoni.SetTitle("Pepperoni", UIControlState.Normal);
beef = new SfCheckBox();
beef.StateChanged += CheckBox_StateChanged;
beef.SetTitle("Beef", UIControlState.Normal);
beef.IsChecked = true;
mushroom = new SfCheckBox();
mushroom.StateChanged += CheckBox_StateChanged;
mushroom.SetTitle("Mushrooms", UIControlState.Normal);
onion = new SfCheckBox();
onion.StateChanged += CheckBox_StateChanged;
onion.SetTitle("Onions", UIControlState.Normal);
onion.IsChecked = true;

...

}

private void SelectAll_StateChanged(object sender, StateChangedEventArgs e)
{
    if (!skip)
    {
       skip = true;
       pepperoni.IsChecked = beef.IsChecked = mushroom.IsChecked = onion.IsChecked = e.IsChecked;
       skip = false;
    }
}

private void CheckBox_StateChanged(object sender, StateChangedEventArgs e)
{
    if (!skip)
    {
       skip = true;
       if (pepperoni.IsChecked.Value && beef.IsChecked.Value && mushroom.IsChecked.Value && onion.IsChecked.Value)
           selectAll.IsChecked = true;
       else if (!pepperoni.IsChecked.Value && !beef.IsChecked.Value && !mushroom.IsChecked.Value && !onion.IsChecked.Value)
	       selectAll.IsChecked = false;
       else
           selectAll.IsChecked = null;
       skip = false;
    }
}
		
{% endhighlight %}
{% endtabs %}

![Xamarin.iOS CheckBox intermediate state](Images/Inter1.png) ![Xamarin.iOS CheckBox intermediate state](Images/Inter2.png)

This demo can be downloaded from this [link](https://github.com/SyncfusionExamples/GettingStarted-Sample-CheckBox-Xamarin.iOS/).