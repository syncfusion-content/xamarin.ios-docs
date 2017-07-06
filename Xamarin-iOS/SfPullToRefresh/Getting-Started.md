---
layout: post
title: Getting Started | SfPullToRefresh | Xamarin.iOS | Syncfusion
description: getting started
platform: Xamarin.iOS
control: SfPullToRefresh
documentation: ug
---

# Getting Started

## Create your first PullToRefresh in Xamarin.iOS

This section explains you the steps to configure a PullToRefresh control in a real-time scenario and also provides a walk-through on some of the customization features available in PullToRefresh control.

## Creating your first PullToRefresh in Xamarin.iOS.

### Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:
{Syncfusion Installed location}\Essential Studio {version number}\lib
And below assembly reference to the iOS unified project.
ios-unifed\Syncfusion.SfPullToRefresh.iOS.dll

### Add and Configure the PullToRefresh

* Adding reference to PullToRefresh.

{% highlight c# %}

	using Syncfusion.SfPullToRefresh.iOS;; 

{% endhighlight %}

* Create an instance of PullToRefresh.

{% highlight c# %}
	
	public override void ViewDidLoad ()
    {
    base.ViewDidLoad ();

    //Initialize the PullToRefresh with required frame. This frame can be any rectangle, which bounds inside the view.
    SFPullToRefresh pullToRefresh = new SFPullTORefresh ();
    pullToRefresh.Frame   = this.View.Frame;
    }
	
{% endhighlight %}

## Customizing a simple SfPulToRefresh sample

To develop an application with Android PullToRefresh is simple. The following steps explains how to create and configure its properties.

* Create the `PullableContent` for the `SfPullToRefresh`

You can set the `PullableContent` for the `SfPullToRefresh` by adding the desired UIElement.

{% highlight c# %}
    
    UIView mainView= new UIView();
    mainView.Frame = new CGRect(Frame.Location.X, 0, Frame.Width, Frame.Height);
    mainView.BackgroundColor = UIColor.FromRGBA(0.012f,0.608f,0.898f,1);
    pullToRefresh.PullableContent = mainView;
{% endhighlight %}

## Delegate

`SFPullToRefresh.Delegate` is called once the refreshing will be completed.

{% tabs %}

{% highlight c# %}

    pullToRefresh.Delegate = new PullToRefreshDelegate(this);

    public class PullToRefreshDelegate : SFPullToRefreshDelegate
	{
		public PullToRefreshDelegate()
		{
		
		}
		public override void Refreshed(SFPullToRefresh pulltorefresh)
		{
			NSTimer.CreateScheduledTimer(TimeSpan.FromSeconds(2), new Action<NSTimer>(delegate {
			
				pullToRefresh.Refresh();

			}));


		 }
    }

{% endhighlight %}

{% endtabs %}

You can download the entire source code of this demo for Xamarin.iOS from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStarted85797611).          
