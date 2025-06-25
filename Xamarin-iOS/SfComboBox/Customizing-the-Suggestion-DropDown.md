---
layout: post
title: Customizing the Syncfusion® ComboBox control in Xamarin.iOS
description: Learn how to customize the ComboBox
platform: xamarin.ios
control: ComboBox
documentation: ug
---

# Customization

The ComboBox control provides multiple customization options. The following topics deal with different forms of customization in the SfComboBox control.

## Dropdown Items Customization

The dropdown list displaying behavior can be customized based on the entered text and delays in displaying the items. 

## Selected Dropdown Item Color

You can set the color for the selected item in the dropdown using the `SelectedDropDownItemColor` property.

{% tabs %}

{% highlight C# %}

combobox.SelectedDropDownItemColor = UIColor.FromRGB(0, 173, 255);

{% endhighlight %}

{% endtabs %}

![Selected dropdown item color](images/selecteddropdownitemcolor.png)

## Set Maximum Height to the Dropdown

The height of the dropdown portion of the ComboBox control can be adjusted using the `MaximumDropDownHeight` property.

N> The value of the `MaximumDropDownHeight` property can be any positive integer value.

{% tabs %}

{% highlight C# %}

combobox.MaxDropDownHeight = 60;

{% endhighlight %}

{% endtabs %}

![Maximum dropdown height](images/maximumdropdownheight.png)

## Set Border Color to the Dropdown

The `DropDownBorderColor` property is used to change the border color of the dropdown. The following code example demonstrates how to change the border color of the dropdown.

{% tabs %}

{% highlight C# %}
    
SfComboBox countryComboBox = new SfComboBox();
countryComboBox.Frame = new CGRect(10, 20, 250, 30);
NSMutableArray countryList = new NSMutableArray();
countryList.Add((NSString)"Afghanistan");
countryList.Add((NSString)"Akrotiri");
countryList.Add((NSString)"Albania");
countryComboBox.ComboBoxSource = countryList;
countryComboBox.DropDownBorderColor = UIColor.Red;
this.View.AddSubview(countryComboBox);

{% endhighlight %}

{% endtabs %}

![Dropdown border color](images/drop-down-border-color.png)

## Dropdown Button Customization

The dropdown button can be customized using the `DropDownButtonSettings` property in the following ways:

* **Width** – Sets the width for the dropdown button.
* **Height** - Sets the height for the dropdown button.
* **FontIcon** - Sets different FontIcon for the dropdown button.
* **FontColor** - Sets different FontColor for the dropdown button.
* **FontSize** - Sets different FontSize for the dropdown button.
* **FontFamily** - Sets the different FontFamily for the dropdown button.
* **BackgroundColor** - Sets the background color for the dropdown button.
* **HighlightedBackgroundColor** - Sets the background color for the dropdown button when it is pressed.
* **HighlightedFontColor** - Sets the font color for the dropdown button when it is pressed.
* **Image** - Sets the image to the dropdown button.
* **View** – Sets a custom view to the dropdown button.

{% tabs %}

{% highlight C# %}

DropDownButtonSettings dropDownButtonSettings = new DropDownButtonSettings(); 
dropDownButtonSettings.Image = "calendar.png"; 
combobox.DropDownButtonSettings = dropDownButtonSettings; 

{% endhighlight %}

{% endtabs %}

![Dropdown button customization](images/buttoncustomization.png)

## Watermark

The watermark text is used to display placeholder information regarding the ComboBox. This watermark is visible only when the text box is empty or null. The watermark text disappears when users begin to type or select any item from the dropdown list in the ComboBox control.

{% tabs %}

{% highlight C# %}

combobox.Watermark = (NSString)"Select any Countries name"; 

{% endhighlight %}

{% endtabs %}

![Watermark](images/watermark.png)