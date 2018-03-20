---
layout: post
title: Popup Events| SfPopupLayout |Xamarin| Syncfusion
description: How to use different events exposed in SfPopupLayout.
platform: Xamarin
control: SfPopupLayout
documentation: ug
--- 

# Events

There are four built-in events in the SfPopupLayout control namely:

* Opening
* Opened
* Closing
* Closed

## Opening Event

[SfPopupLayout.Opening](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~Opening_EV.html) event will be fired whenever the PopupView is opening in the view with `CancelEventArgs` that contains the following property.

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true) - Based on this value, you can cancel the popup opening.

Refer to the following code example in which the pop-up will be canceled in `SfPopupLayout.Opening` event.

{% tabs %}
{%highlight Xaml%}
<sfPopup:SfPopupLayout x:Name="popupLayout" Opening="PopupLayout_Opening"/>
{%endhighlight%}

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.Opening += PopupLayout_Opening;
    ....
}

private void PopupLayout_Opening(object sender, System.ComponentModel.CancelEventArgs e)
{
    e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

## Opened Event

[SfPopupLayout.Opened](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~Opened_EV.html) event will be fired whenever the PopupView is shown in the view.
You can customize your requirement by using this event.

Refer to the following code example in which the "Popup Opened" message is shown in output window in `SfPopupLayout.Opened` event.

{% tabs %}
{%highlight Xaml%}
<sfPopup:SfPopupLayout x:Name="popupLayout" Opened="PopupLayout_Opened"/>
{%endhighlight%}

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.Opened += PopupLayout_Opened;
    ....
}

private void PopupLayout_Opened(object sender, EventArgs e)
{
    System.Diagnostics.Debug.WriteLine("Popup is Opened");
}
{% endhighlight %}
{% endtabs %}

## Closing Event

[SfPopupLayout.Closing](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~Opening_EV.html) event will be fired whenever the PopupView is closing in the view with `CancelEventArgs` that contains the following property.

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true) - Based on this value, you can cancel the popup closing.

Refer to the following code example in which the pop-up will be canceled in `SfPopupLayout.Closing` event.

{% tabs %}
{%highlight Xaml%}
<sfPopup:SfPopupLayout x:Name="popupLayout"  Closing="PopupLayout_Closing"/>
{%endhighlight%}

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.Closing += PopupLayout_Closing;
    ....
}

private void PopupLayout_Closing(object sender, System.ComponentModel.CancelEventArgs e)
{
    e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

## Closed Event

[SfPopupLayout.Closed](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~Closed_EV.html) event will be fired whenever the PopupView is dismissed from the view.
You can customize your requirement by using this event.

Refer to the following code example in which the "Popup closed" message is shown in output window in `SfPopupLayout.Closed` event.

{% tabs %}
{%highlight Xaml%}
<sfPopup:SfPopupLayout x:Name="popupLayout" Closed="PopupLayout_Closed"/>
{%endhighlight%}

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.Closed += PopupLayout_Closed;
    ....
}

private void PopupLayout_Closed(object sender, EventArgs e)
{
    System.Diagnostics.Debug.WriteLine("Popup is closed");
}
{% endhighlight %}
{% endtabs %}

## Footer Button Commands

Following are the two commands available in the Footer.

* AcceptCommand
* DeclineCommand

### Accept Command

[SfPopupLayout.PopupView.AcceptCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~AcceptCommand.html) will be fired when the accept button in the footer is clicked. 

Derive a class from `ICommand` and implement the neccessary interface. Return true in the `CanExecute()` method to close the popup and return false to prevent popup from closing.

Refer to the following code example in which the pop-up closing will be canceled based on the return value of `CanExecute()` method.

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.PopupView.AppearanceMode = AppearanceMode.TwoButton;
    popupLayout.PopupView.AcceptCommand = new AcceptButtonCustomCommand();
    ....
}
{% endhighlight %}

{% highlight c# %}
//Accept Button Event handler

public class AcceptButtonCustomCommand : ICommand
{
    public event EventHandler CanExecuteChanged;

    public bool CanExecute(object parameter)
    {
        return true;
    }

    public void Execute(object parameter)
    {
       
    }
}
{% endhighlight %}

### Decline Command

[SfPopupLayout.PopupView.DeclineCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~DeclineCommand.html) will be fired when the decline button in the footer is clicked.  

Derive a class from `ICommand` and implement the neccessary interface. Return true in the `CanExecute()` method to close the popup and return false to prevent popup from closing.

Refer to the following code example in which the pop-up closing will be canceled based on the return value of `CanExecute()` method.

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.PopupView.AppearanceMode = AppearanceMode.TwoButton;
    popupLayout.PopupView.DeclineCommand = new DeclineButtonCustomCommand();
    ....
}
{% endhighlight %}

{% highlight c# %}
//Decline Button Event handler

public class DeclineButtonCustomCommand : ICommand
{
    public event EventHandler CanExecuteChanged;

    public bool CanExecute(object parameter)
    {
        return true;
    }

    public void Execute(object parameter)
    {
       
    }
}
{% endhighlight %}