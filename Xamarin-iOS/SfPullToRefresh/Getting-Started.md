---
layout: post
title: Getting Started | SfPullToRefresh | Xamarin.iOS | Syncfusion
description: Getting Started with SfPullToRefresh
platform: Xamarin.iOS
control: SfPullToRefresh
documentation: ug
---

# Getting Started

This section provides a quick overview for working with SfPullToRefresh in Xamarin.iOS. You will walk through the entire process of creating a simple application with SfPullToRefresh.

## Assembly deployment

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Essential Studio Installed location}\Essential Studio\15.4.0.17\Xamarin\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\15.4.0.17\Xamarin\lib

N> Assemblies can be found in unzipped package location in Mac

### SfPullToRefresh for Xamarin.iOS

The following assembly need to be added as reference from the "lib" folder to use SfPullToRefresh in your application.

<table>
<tr>
<th> Project </th>
<th> Required assemblies </th>
</tr>
<tr>
<td> Xamarin.iOS </td>
<td> ios-unified\Syncfusion.SfPullToRefresh.iOS.dll </td>
</tr>
</table>

## NuGet installation

You need to configure the NuGet package of Syncfusion components, to install the SfPullToRefresh control in your application. Refer the below KB to configure the NuGet package of Syncfusion components. 

[How to configure package source and install Syncfusion NuGet packages in an existing project?](https://www.syncfusion.com/kb/7441/how-to-configure-package-source-and-install-syncfusion-nuget-packages-in-an-existing-project)

### SfPullToRefresh for Xamarin.iOS

The following NuGet package need to be added to use SfPullToRefresh control in your application.

<table>
<tr>
<th> Project </th>
<th> Required packages </th>
</tr>
<tr>
<td> Xamarin.iOS </td>
<td> Syncfusion.Xamarin.SfPullToRefresh.iOS </td>
</tr>
</table>

Refer the below screenshot in which the Syncfusion.Xamarin.SfPullToRefresh.iOS package is highlighted.

![](GettingStarted_images/NuGetInstall.png)

## Create a sample application with SfPullToRefresh

This section explains how to create a sample with SfPullToRefresh and configure it. The SfPullToRefresh control can be configured entirely in C# code. 

In this walk through, you will create a new application that contains the SfPullToRefresh which includes the below topics.

* [Creating the project](#creating-the-project)  
* [Adding SfPullToRefresh in Xamarin.iOS](#adding-sfpulltorefresh-in-xamarinios) 
* [Adding a simple view as the PullableContent](#adding-a-simple-view-as-the-pullablecontent) 
* [Refreshing the view](#refreshing-the-view) 
* [TransitionType Customization](#transitiontype-customization)
* [Final Output of the sample](#final-output-of-the-sample)
* [Sample Link](#sample-link)

### Creating the project

Create a new iOS application in Xamarin Studio or Visual Studio for Xamarin.iOS.

### Adding SfPullToRefresh in Xamarin.iOS

1. Add the required assembly references to the project as mentioned in the [Assembly deployment](#assembly-deployment) section or install the SfPullToRefresh NuGet as mentioned in the [NuGet installation](#nuget-installation) section.

2. Import SfPullToRefresh control under the namespace `Syncfusion.SfPullToRefresh`.

3. Create an instance of SfPullToRefresh control and add as the subview of the UIViewController. Refer the below code example to add the SfPullToRefresh control to the application.

{% highlight c# %}

using Syncfusion.SfPullToRefresh; 

public class MyViewController : UIViewController
{
    SfPullToRefresh pullToRefresh; 

    public MyViewController()
    {
        pullToRefresh = new SfPullToRefresh(); 
        this.View.AddSubview(pullToRefresh);
    } 
} 

{% endhighlight %}

### Adding a simple view as the PullableContent

You can add any view, as the pullable content of SfPullToRefresh using [SfPullToRefresh.PullableContent](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~PullableContent.html) property to refresh it. Refer the below code example in which a simple custom view is added as pullable content of SfPullToRefresh.

{% highlight c# %}

//MyViewController.cs

CustomView customView;
BaseView baseView;
UILabel label;
UIButton button;

public MyViewController()
{
	....
	InitializeViews();
    customView = new CustomView(label, baseView);
	//Setting the PullableContent of the SfPullToRefresh.
	pullToRefresh.PullableContent = customView;
	....
}

private void InitializeViews()
{
    ....
    baseView = new BaseView();
    label = new UILabel();
    ....
}

{% endhighlight %}

### Refreshing the view

To refresh the view, the user should hook the [SfPullToRefresh.Refreshing](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~Refreshing_EV.html) event. The [SfPullToRefresh.Refreshing](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~Refreshing_EV.html) event will be fired, once the pulling progress reaches 100% and the touch is released. The user can do the required operations to refresh the view and once the view is refreshed, set the [RefreshingEventArgs.Refreshed](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.RefreshingEventArgs~Refreshed.html) as <b>true</b> to stop the refreshing animation. 

Refer the below code example which illustrates hooking the [SfPullToRefresh.Refreshing](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~Refreshing_EV.html) event and refreshing the view.

{% highlight c# %}

//MyViewController.cs
public MyViewController()
{
    ....
    //Hooking the Refreshing event.
    pullToRefresh.Refreshing += PullToRefresh_Refreshing;
    ....
}

private void PullToRefresh_Refreshing(object sender, RefreshingEventArgs e)
{
    NSTimer.CreateScheduledTimer(TimeSpan.FromSeconds(3), new Action<NSTimer>(delegate {
        baseView.model.Temperature = (NSString)new Random().Next(10, 40).ToString();
        baseView.UpdateBaseView();
        e.Refreshed = true;
    }));
}

{% endhighlight %}

### TransitionType Customization

SfPullToRefresh supports two types of transition. By default, `TransitionType.SlideOnTop` is enabled. 

Refer the topic `TransitionType` under `Built-in Customization` section, for more details regarding [SfPullToRefresh.TransitionType](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpulltorefresh/Syncfusion.SfPullToRefresh.iOS~Syncfusion.SfPullToRefresh.SfPullToRefresh~TransitionType.html) property.

Refer the below code example to switch to the `TransitionType.Push` mode of transition.

{% highlight c# %}

public MyViewController()
{
	....
	pullToRefresh.TransitionType = TransitionType.Push;
	....
}

{% endhighlight %}

### Final output of the sample

The below image demonstrates the final output of the sample.

<div style="text-align:center" markdown="1">
![](GettingStarted_images/GettingStarted_SlideOnTop.png)
</div>

<div style="text-align:center" markdown="1">
![](GettingStarted_images/GettingStarted_Push.png)
</div>

### Sample Link

You can download the source code of this sample here.
