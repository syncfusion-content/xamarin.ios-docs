---
layout: post
title: Popup Events| SfPopupLayout |Xamarin| Syncfusion
description: How to use different events exposed in SfPopupLayout.
platform: Xamarin.iOS
control: SfPopupLayout
documentation: ug
--- 

# Events

There are four built-in events in the SfPopupLayout control namely,

* Opening
* Opened
* Closing
* Closed

## Opening Event

[SfPopupLayout.Opening](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpopuplayout/Syncfusion.SfPopupLayout.iOS~Syncfusion.iOS.PopupLayout.SfPopupLayout~Opening_EV.html) event will be fired whenever the PopupView is opening in the view. It provides support to cancel the opening of the popup with `CancelEventArgs` that contains the following property.

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true) - Based on this value, you can cancel the popup opening.

Refer to the following code example in which the pop-up will be canceled in `SfPopupLayout.Opening` event.

{% highlight c# %}

//MyViewController.cs

public MyViewController()
{
    ....
    popupLayout = new SfPopupLayout();
    popupLayout.Content = GetContentOfPopup();
    popupLayout.Opening += PopupLayout_Opening;
    this.View.AddSubview(popupLayout);
    ....
}

private void PopupLayout_Opening(object sender, System.ComponentModel.CancelEventArgs e)
{
     e.Cancel = true;
}

{% endhighlight %}

## Opened Event

[SfPopupLayout.Opened](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpopuplayout/Syncfusion.SfPopupLayout.iOS~Syncfusion.iOS.PopupLayout.SfPopupLayout~Opened_EV.html) event will be fired whenever the PopupView is shown in the view.
You can write your set of codes that needs to be executed once the popup is opened and visible in the application, in its respective event handler.

Refer to the following code example for using `SfPopupLayout.Opened` event.

{% highlight c# %}

//MyViewController.cs

public MyViewController()
{
    ....
    popupLayout = new SfPopupLayout();
    popupLayout.Content = GetContentOfPopup();
    popupLayout.Opened += PopupLayout_Opened;
    this.View.AddSubview(popupLayout);
    ....
}

private void PopupLayout_Opened(object sender, EventArgs e)
{
    // Codes that needs to be executed once popup is visible in the screen.        
}

{% endhighlight %}

## Closing Event

[SfPopupLayout.Closing](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpopuplayout/Syncfusion.SfPopupLayout.iOS~Syncfusion.iOS.PopupLayout.SfPopupLayout~Closing_EV.html) event will be fired whenever the PopupView is closing in the view.  It provides support to cancel closing of the popup with `CancelEventArgs` that contains the following property.

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true) - Based on this value, you can cancel the popup closing.

Refer to the following code example in which the pop-up will be canceled in `SfPopupLayout.Closing` event.

{% highlight c# %}

//MyViewController.cs

public MyViewController()
{
    ....
    popupLayout = new SfPopupLayout();
    popupLayout.Content = GetContentOfPopup();
    popupLayout.Closing += PopupLayout_Closing;
    this.View.AddSubview(popupLayout);
    ....
}

private void PopupLayout_Closing(object sender, System.ComponentModel.CancelEventArgs e)
{
    e.Cancel = true;
}

{% endhighlight %}

## Closed Event

[SfPopupLayout.Closed](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpopuplayout/Syncfusion.SfPopupLayout.iOS~Syncfusion.iOS.PopupLayout.SfPopupLayout~Closed_EV.html) event will be fired whenever the PopupView is dismissed from the view.
You can write your set of codes that needs to be executed once the popup is completely closed, in its respective event handler.

Refer to the following code example for using `SfPopupLayout.Closed` event.

{% highlight c# %}

//MyViewController.cs

public MyViewController()
{
    ....
    popupLayout = new SfPopupLayout();
    popupLayout.Content = GetContentOfPopup();
    popupLayout.Closed += PopupLayout_Closed;
    this.View.AddSubview(popupLayout);
    ....
}

private void PopupLayout_Closed(object sender, EventArgs e)
{
   // Codes that needs to be executed once popup is completly closed.    
}

{% endhighlight %}

## Footer Button Clicked Events

Following are the two events available in the Footer.

* AcceptButtonClicked
* DeclineButtonClicked

### AcceptButtonClicked

SfPopupLayout.PopupView.AcceptButtonClicked will be fired when the accept button in the footer of the popup is clicked. It provides support to cancel closing of the popup with `CancelEventArgs` that contains the following property.

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true) - Based on this value, you can cancel the popup closing.

Refer to the following code example in which the pop-up closing will be canceled based on the `e.Cancel` value.

{% highlight c# %}

//MyViewController.cs

public MyViewController()
{
    ....
    popupLayout = new SfPopupLayout();
    popupLayout.Content = GetContentOfPopup();
    popupLayout.PopupView.AcceptButtonClicked += PopupView_AcceptButtonClicked;
    this.View.AddSubview(popupLayout);
    ....
}

private void PopupView_AcceptButtonClicked(object sender, System.ComponentModel.CancelEventArgs e)
{
     e.Cancel = true;
}

{% endhighlight %}

### DeclineButtonClicked

SfPopupLayout.PopupView.DeclineButtonClicked will be fired when the decline button in the footer of the popup is clicked. It provides support to cancel closing of the popup with `CancelEventArgs` that contains the following property.

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true) - Based on this value, you can cancel the popup closing.

Refer to the following code example in which the pop-up closing will be canceled based on the `e.Cancel` value.

{% highlight c# %}

//MyViewController.cs

public MyViewController()
{
    ....
    popupLayout = new SfPopupLayout();
    popupLayout.Content = GetContentOfPopup();
    popupLayout.PopupView.DeclineButtonClicked += PopupView_DeclineButtonClicked;
    this.View.AddSubview(popupLayout);
    ....
}

private void PopupView_DeclineButtonClicked(object sender, System.ComponentModel.CancelEventArgs e)
{
    e.Cancel = true;
}

{% endhighlight %}