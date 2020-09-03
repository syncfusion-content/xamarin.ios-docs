---
layout: post
title: Getting Started | SfPopupLayout | Xamarin.iOS | Syncfusion
description: Getting Started with SfPopupLayout
platform: Xamarin.iOS
control: SfPopupLayout
documentation: ug
---

# Getting Started

This section provides a quick overview for working with SfPopupLayout in Xamarin.iOS. Walk through the entire process of creating a simple application with this control.

## Assembly deployment

After installing Essential Studio for Xamarin, all the required assemblies can be found in the {Syncfusion Essential Studio Installed location}\Essential Studio\{{ site.releaseversion }}\Xamarin\lib installation folder. E.g. C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\Xamarin\lib installation folder.

N> Assemblies can be found in an unzipped package location in Mac.

## NuGet configuration

To install the required NuGet for the SfPopupLayout control in the application, configure the NuGet packages of the Syncfusion components.

[How to configure package source and install Syncfusion NuGet packages in an existing project?](https://www.syncfusion.com/kb/7441/how-to-configure-package-source-and-install-syncfusion-nuget-packages-in-an-existing-project)

The following NuGet package should be installed to use the SfPopupLayout control in the application.

<table>
<tr>
<th> Project </th>
<th> Required package </th>
</tr>
<tr>
<td> Xamarin.iOS </td>
<td> Syncfusion.Xamarin.SfPopupLayout.iOS </td>
</tr>
</table>


### Adding SfPopupLayout Reference

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfPopupLayout to your project, open the NuGet package manager in Visual Studio, and search for [Syncfusion.Xamarin.SfPopupLayout.IOS](https://www.nuget.org/packages/Syncfusion.Xamarin.SfPopUpLayout.IOS), and then install it.

![SfPopupLayout in nuget.org](GettingStarted_images/NuGetInstall.png)

To know more about obtaining our components, refer to this [link](https://help.syncfusion.com/xamarin-android/introduction/download-and-installation). Also, if you prefer to manually refer the assemblies instead of NuGet, refer the list of assemblies mentioned in the table below.

<table>
<tr>
<th> Project </th>
<th> Required assembly </th>
</tr>
<tr>
<td> Xamarin.iOS </td>
<td> ios-unified\Syncfusion.SfPopupLayout.iOS.dll </td>
</tr>
</table>

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Create a sample application with SfPopupLayout

The SfPopupLayout control can be configured entirely in C# code or using story board. To create a sample application for this control, follow the topics:  

* [Adding SfPopupLayout in Xamarin.iOS](#adding-sfpopuplayout-in-xamarin.iOS) 
* [Customize positioning](# Customize-positioning) 
* [Customizing layouts](#Customizing-layouts) 
* [Customizing animations](#Customizing-animations)

Create a new iOS application in Xamarin Studio or Visual Studio for Xamarin.iOS.

## Adding SfPopupLayout using story board

To add SfPopupLayout using story board, follow the steps:

1. Add a new story board inside the project.
2. Drag the SfPopupLayout control from toolbox and drop into story board. Preview will not be shown since this is a hosting control. You can only see the pop-up when deployed in the device.
3. Open the properties window of SfPopupLayout and set the required properties.

![SfPopupLayout properties via story board](PopupLayout_images/storyboard_staysopen_sfpopup_ios.png)

The following code illustrates displaying the SfPopupLayout when set as a root view using storyboard.

{% tabs %}
{% highlight c# %}
using UIKit;

namespace Storyboard_SfPopupLayout_ios
{
    public partial class MyViewController : UIViewController
    {
        partial void ButtonClicked(UIButton sender)
        {
            sfPopup.Show();
        }

        public MyViewController() : base("MyViewController", null)
        {
        }

        public override void ViewDidLoad()
        {
            base.ViewDidLoad();
            // Perform any additional setup after loading the view, typically from a nib.
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

You can download the entire source code of this sample [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Storyboard_SfpopupLayout_ios-779309500).

Refer to this link to know the properties that can be configured using story board for SfPopupLayout.

## Adding SfPopupLayout in Xamarin.iOS using C# code

1. Add the required assembly references to the project as mentioned in the [Assembly deployment](#assembly-deployment) section or install the NuGet as mentioned in the [NuGet installation](#nuget-installation) section.

2. Import the SfPopupLayout control under the namespace `Syncfusion.iOS.PopupLayout`.

3. The SfPopupLayout can be displayed by the following cases:
 
### Displaying pop-up when the SfPopupLayout is set as root view 

The SfPopupLayout can be displayed by making it as the base view or content view of the activity. For the first case, set the view over which the SfPopupLayout should be displayed as the content of the SfPopupLayout using the [SfPopupLayout.Content](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.SfPopupLayout.html#Syncfusion_iOS_PopupLayout_SfPopupLayout_Content) property. Create an instance of the SfPopupLayout control and add as subview of the UIViewController. 

Refer to the following code example for displaying popup.

{% tabs %}
{% highlight c# %}

using Syncfusion.iOS.PopupLayout;

namespace GettingStarted
{
    public class MyViewController:UIViewController
    {
        SfPopupLayout popupLayout;
        CustomView customView;
        UIButton showPopupButton;
       
        public MyViewController()
        {
            popupLayout = new SfPopupLayout();
            popupLayout.Content = GetContentOfPopup();
            this.View.AddSubview(popupLayout);
        }
        private UIView GetContentOfPopup()
        {
            customView = new CustomView();
            customView.BackgroundColor = UIColor.White;

            showPopupButton = new UIButton();
            showPopupButton.SetTitle("Click to show Popup", UIControlState.Normal);
            showPopupButton.SetTitleColor(UIColor.White, UIControlState.Normal);
            showPopupButton.BackgroundColor = UIColor.Gray;
            showPopupButton.TouchDown += ShowPopupButton_TouchDown;
			
            customView.AddSubview(showPopupButton);
            return customView;
        }
        private void ShowPopupButton_TouchDown(object sender, EventArgs e)
        {
            popupLayout.Show();
        }
        public override void ViewDidLayoutSubviews()
        {
            base.ViewDidLayoutSubviews();
            popupLayout.Frame = new CGRect(0, 20, this.View.Frame.Width, this.View.Frame.Height - 20);
        }
    }
}
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
// CustomView.cs

public class CustomView : UIView
{
    public CustomView() : base()
    {
    }
    public override void LayoutSubviews()
    {
        base.LayoutSubviews();
        this.Subviews[0].Frame = new CGRect(0, 20, this.Frame.Right, 50);
    }
}
{% endhighlight %}   
{% endtabs %}

### Displaying pop-up when SfPopupLayout is not set as root view 

You can continue to keep your view as the content view of the activity and still display pop-up over your view by simply calling the SfPopupLayout.Show() method. 

Refer to the following code example for displaying popup.

{% tabs %}
{% highlight c# %}

using Syncfusion.iOS.PopupLayout;

namespace GettingStarted
{
    public class MyViewController:UIViewController
    {
        SfPopupLayout popupLayout;
        UIView rootView;
        CustomView customView;
        UIButton showPopupButton;
       
        public MyViewController()
        {
            popupLayout = new SfPopupLayout();
            rootView = new UIView();
            rootView= GetContentOfPopup();
            this.View.AddSubview(rootView);
        }
        private UIView GetContentOfPopup()
        {
            customView = new CustomView();
            customView.BackgroundColor = UIColor.White;

            showPopupButton = new UIButton();
            showPopupButton.SetTitle("Click to show Popup", UIControlState.Normal);
            showPopupButton.SetTitleColor(UIColor.White, UIControlState.Normal);
            showPopupButton.BackgroundColor = UIColor.Gray;
            showPopupButton.TouchDown += ShowPopupButton_TouchDown;

            customView.AddSubview(showPopupButton);
            return customView;
        }
        private void ShowPopupButton_TouchDown(object sender, EventArgs e)
        {
            popupLayout.Show();
        }
        public override void ViewDidLayoutSubviews()
        {
            base.ViewDidLayoutSubviews();
            rootView.Frame = new CGRect(0, 20, this.View.Frame.Width, this.View.Frame.Height - 20);
        }
    }
}

{% endhighlight %}
{% endtabs %}

Executing the above codes renders the following output in an iOS device.

![SfPopupLayout default appearance](GettingStarted_images/DefaultAppearance.png)

You can download the source code of this sample [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStarted1822336781).

## Customize positioning

The SfPopupLayout allows showing the pop-up content at various positions.

The following list of options are available to position the SfPopupLayout in the desired position.

* `Center Positioning`: Use the [SfPopupLayout.IsOpen](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.SfPopupLayout.html#Syncfusion_iOS_PopupLayout_SfPopupLayout_IsOpen) property or [SfPopupLayout.Show()](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.SfPopupLayout.html#Syncfusion_iOS_PopupLayout_SfPopupLayout_Show) to display the SfPopupLayout at the center.
* `Absolute Positioning`: Use the [SfPopupLayout.Show(x-position, y-position)](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.SfPopupLayout.html#Syncfusion_iOS_PopupLayout_SfPopupLayout_Show)to display the SfPopupLayout at the specified X and y position.
* `OnTouch`: Use the [SfPopupLayout.ShowAtTouchPoint()](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.SfPopupLayout.html#Syncfusion_iOS_PopupLayout_SfPopupLayout_ShowAtTouchPoint) to display the SfPopupLayout at the touch point.
* `Relative Positioning`: Use the [SfPopupLayout.ShowRelativeToView(View, RelativePosition)](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.SfPopupLayout.html#Syncfusion_iOS_PopupLayout_SfPopupLayout_ShowRelativeToView_UIKit_UIView_Syncfusion_iOS_PopupLayout_RelativePosition_System_Double_System_Double_) to display the SfPopupLayout at any of the 8 positions relative to the specified view.
* `Absolute relative positioning`: Use the [SfPopupLayout.ShowRelativeToView(View, RelativePosition,x position,y position)](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.SfPopupLayout.html#Syncfusion_iOS_PopupLayout_SfPopupLayout_ShowRelativeToView_UIKit_UIView_Syncfusion_iOS_PopupLayout_RelativePosition_System_Double_System_Double_) to display the SfPopupLayout at an absolute x,y coordinate from the relative position of the specified view.

More information for pop-up positioning is in this [link](https://help.syncfusion.com/xamarin-ios/sfpopuplayout/popup-positioning).

## Customizing layouts

By default, you can choose from the following available layouts in the SfPopupLayout using the property [SfPopupLayout.AppearanceMode](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.AppearanceMode.html).

* [OneButton](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.AppearanceMode.html): Shows the SfPopupLayout with one button in the footer view. This is the default value.
* [TwoButton](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.AppearanceMode.html): Shows the SfPopupLayout with two buttons in the footer view.

You can also customize the entire view of the pop-up by loading the templates or custom views for the header, body, and footer.

###  Load your custom view in the popup body

Any view can be added as the pop-up content using the [SfPopupLayout.PopupView.ContentView](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.PopupView.html#Syncfusion_iOS_PopupLayout_PopupView_ContentView) property to refresh it. Refer to the following code example in which a UILabel is added as pop-up content.

{% tabs %}
{% highlight c# %}

using Syncfusion.iOS.PopupLayout;

namespace GettingStarted
{
    public class MyViewController:UIViewController
    {
        SfPopupLayout popupLayout;
        CustomView customView;
        UIButton showPopupButton;
        UILabel popupContentView;

        public MyViewController()
        {
            popupLayout = new SfPopupLayout();

            popupContentView = new UILabel();
            popupContentView.Text = "This is the Customized view for SfPopupLayout";
            popupContentView.TextColor = UIColor.Black;
            popupContentView.BackgroundColor = UIColor.Cyan;
            popupContentView.TextAlignment = UITextAlignment.Center;

            // Adding ContentView of the SfPopupLayout
            popupLayout.PopupView.ContentView = popupContentView;
            popupLayout.Content = GetContentOfPopup();
            this.View.AddSubview(popupLayout);
        }
        private UIView GetContentOfPopup()
        {
            customView = new CustomView();
            customView.BackgroundColor = UIColor.White;

            showPopupButton = new UIButton();
            showPopupButton.SetTitle("Click to show Popup", UIControlState.Normal);
            showPopupButton.SetTitleColor(UIColor.White, UIControlState.Normal);
            showPopupButton.BackgroundColor = UIColor.Gray;
            showPopupButton.TouchDown += ShowPopupButton_TouchDown;

            customView.AddSubview(showPopupButton);
            return customView;
        }
        private void ShowPopupButton_TouchDown(object sender, EventArgs e)
        {
            popupLayout.Show();
        }
        public override void ViewDidLayoutSubviews()
        {
            base.ViewDidLayoutSubviews();
            popupLayout.Frame = new CGRect(0, 20, this.View.Frame.Width, this.View.Frame.Height - 20);
        }
    }
}
{% endhighlight %}
{% endtabs %}

Executing the above codes renders the following output in an iOS device.

![Popup with custom view](GettingStarted_images/ContentView.png)

N> Setting the content view is same for both cases i.e. displaying pop-up when the SfPopupLayout is set as root view and vice versa.

## Customizing animations

Built-in animations are available in the SfPopupLayout applied when the PopupView opens and closes in the screen.

By default, you can choose from the following available animations in the SfPopupLayout using the property [SfPopupLayout.AnimationMode](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.AnimationMode.html).

* [Zoom](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.AnimationMode.html): Zoom-out animation will be applied when the PopupView opens, and zoom-in animation will be applied when the PopupView closes. This is the default AnimationMode
* [Fade](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.AnimationMode.html): Fade-out animation will be applied when the PopupView opens, and fade-in animation will be applied when the PopupView closes.
* [SlideOnLeft](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.AnimationMode.html): PopupView will be animated from left-to-right, when it opens and from right-to-left when the PopupView closes.
* [SlideOnRight](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.AnimationMode.html): PopupView will be animated from right-to-left, when it opens and from left-to-right when the PopupView closes.
* [SlideOnTop](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.AnimationMode.html): PopupView will be animated from top-to-bottom, when it opens and from bottom-to-top when the PopupView closes.
* [SlideOnBottom](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.AnimationMode.html): PopupView will be animated from bottom-to-top, when it opens and from top-to-bottom when the PopupView closes
* [None](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.PopupLayout.AnimationMode.html): Animation will not be applied.

More information for pop-up animations is in this [link](https://help.syncfusion.com/xamarin-ios/sfpopuplayout/popup-animations).

## Properties configured using story board

<table>
<tr>
<th> Properties</th>
<th> Attribute Name</th>
</tr>
<tr><td>IsOpen</td> <td>popupIsOpen</td></tr>
<tr><td>StaysOpen</td><td>Stays Open</td></tr>
</table>
