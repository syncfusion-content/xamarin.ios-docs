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

## Events


The pulling event will be notified whenever the swipe gesture is started. This event will notify the listener each and every time until the refresh content height exceeds. When we release the gesture from pullable content, Refreshing event will be triggered. Now user can proceed to fetching the data from web or database. Once the data is fetched, we should call Refresh to method to complete all animations.

There are three built-in events in the PullToRefresh control namely:

1. `Pulling`
2. `Refreshing`
3. `Refreshed`

### Pulling

`Pulling` event is triggered when we start pulling down the PullableContent. It is triggered as long as the pointer or finger is pressed and the progress is less than 100 and not equal to 0 . The arguments for the event are:

* SfPullToRefresh
* Progress

{% tabs %}


{% highlight c# %}

    pullToRefresh.Pulling+= (object sender, SfPullToRefresh.PullingEventArgs e) => {
				
			};
            
{% endhighlight %}

{% endtabs %}

### Refreshing

`Refreshing` event is triggered once the content is pulled through the PullingThreshold or Progress reaches 100. This event is triggered till the Refresh() method is called.

{% tabs %}

{% highlight c# %}

    pullToRefresh.Refreshing += (object sender, EventArgs e) => {
				
			};

{% endhighlight %}

{% endtabs %}

### Refreshed

`Refreshed` event is triggered once the refreshing and all the animations associated with the control are completed.

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
