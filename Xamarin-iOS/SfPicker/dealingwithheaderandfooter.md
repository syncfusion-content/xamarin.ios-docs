---
layout: post
title: Header and Footer for Syncfusion Picker control in Xamarin.iOS
description: This section will explain about how to customizes the header and footer of Syncfusion Picker control for Xamarin.iOS platform.
platform: Xamarin.iOS
control: Picker
documentation: ug
---

# Dealing with Custom Header and Footer

This section will explain about the header and footer customization of SfPicker.


## Enable or Disable Header

SfPicker allows enabling or disabling the header section by setting `SfPicker.ShowHeader` property to True or False. Default property of `SfPicker.ShowHeader` property is True.

{% tabs %}

{% highlight c# %}

public override void ViewDidLoad()
{
    base.ViewDidLoad();

    SfPicker picker = new SfPicker();
    picker.ShowHeader = false;
    this.View.AddSubview(picker);
}

{% endhighlight %}

{% endtabs %}

## Set Custom Header

SfPicker allows providing custom text to header of SfPicker by setting `SfPicker.HeaderText` property. Default value of `SfPicker.HeaderText` property is Null.

{% tabs %}

{% highlight c# %}

public override void ViewDidLoad()
{
    base.ViewDidLoad();

    SfPicker picker = new SfPicker();
    picker.HeaderText = "Selecte a Date";
    this.View.AddSubview(picker);
}

{% endhighlight %}

{% endtabs %}

## Header Customization

SfPicker allows customizing Background, TextColor and Fonts.

### Background

Header background color can be customized by setting `SfPicker.HeaderBackgroundColor` property of SfPicker.

{% tabs %}

{% highlight c# %}

public override void ViewDidLoad()
{
    base.ViewDidLoad();

    SfPicker picker = new SfPicker();
    picker.HeaderBackgroundColor = UIColor.Green;
    this.View.AddSubview(picker);
}

{% endhighlight %}

{% endtabs %}

### Text Color

Header text color can be customized by setting `SfPicker.HeaderTextColor` property of SfPicker

{% tabs %}

{% highlight c# %}

public override void ViewDidLoad()
{
    base.ViewDidLoad();

    SfPicker picker = new SfPicker();
    picker.HeaderTextColor = UIColor.Red;
    this.View.AddSubview(picker);
}

{% endhighlight %}

{% endtabs %}

### Font

This section will explains about the customization of Header text of Font

#### FontFamily

Header text FontFamily can be customized by setting `SfPicker.HeaderFont` property of SfPicker.

{% tabs %}

{% highlight c# %}

public override void ViewDidLoad()
{
    base.ViewDidLoad();

    SfPicker picker = new SfPicker();
    picker.HeaderFont = UIFont.FromName("sans-serif", 12f);
    this.View.AddSubview(picker);
}

{% endhighlight %}

{% endtabs %}

## Enable or Disable Footer

SfPicker allows enabling or disabling the footer section by setting `SfPicker.ShowFooter` property to True or False. Default value of `SfPicker.ShowFooter` property is False.

{% tabs %}

{% highlight c# %}

public override void ViewDidLoad()
{
    base.ViewDidLoad();

    SfPicker picker = new SfPicker();
    picker.ShowFooter = true;
    this.View.AddSubview(picker);
}

{% endhighlight %}

{% endtabs %}

### Set Custom Footer

SfPicker allows providing custom view to Footer of SfPicker by setting `SfPicker.FooterView` property. Default value of `SfPicker.FooterView` property is Null.

{% tabs %}

{% highlight c# %}

public override void ViewDidLoad()
{
    base.ViewDidLoad();

    SfPicker picker = new SfPicker();
    UIStackView stackView = new UIStackView();
    UIButton button = new UIButton();
    button.SetTitle("Button", UIControlState.Normal);
    stackView.AddSubview(button);
    picker.FooterView = stackView;
    picker.ShowFooter = true;
    this.View.AddSubview(picker);
}

{% endhighlight %}

{% endtabs %}

## Perform validation with default validation button

SfPicker allows performing validation based on OK or Cancel button by hooking `SfPicker.OkButtonClicked` and `SfPicker.CancelButtonClicked`. In this event from the `SelectionChangedEvent` Argument current selected items can be obtained.

{% tabs %}

{% highlight c# %}

public override void ViewDidLoad()
{
    base.ViewDidLoad();

    SfPicker picker = new SfPicker();
    picker.CancelButtonClicked += Picker_CancelButtonClicked;
    picker.OkButtonClicked += Picker_OkButtonClicked;
    this.View.AddSubview(picker);
}

{% endhighlight %}

{% endtabs %}