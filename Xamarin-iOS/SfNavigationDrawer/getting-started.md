---
layout: post
title: Getting Started with Syncfusion NavigationDrawer control for Xamarin.iOS
description: A quick tour to initial users on Syncfusion NavigationDrawer control for Xamarin.iOS platform
platform: Xamarin.iOS
control: NavigationDrawer
documentation: ug
---

# Getting Started

This section provides overview for working with Essential NavigationDrawer for Xamarin.iOS. You can walk through the entire process of creating an NavigationDrawer.

![](images/getting-started.png)

## Create your first NavigationDrawer control in Xamarin.iOS

### Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly references to the iOS project,

android\Syncfusion.SfNavigationDrawer.iOS.dll

### Initializing NavigationDrawer

* Adding reference to navigationDrawer.

{% highlight c# %}

	using Com.Syncfusion.NavigationDrawer; 

{% endhighlight %}

* Create an instance of SfNavigationDrawer.

{% highlight c# %}

	SfNavigationDrawer navigationDrawer = new SfNavigationDrawer(this);
	SetContentView(navigationDrawer);
	
{% endhighlight %}


### Setting Content View

The main view of the NavigationDrawer can be set using `ContentView` property with desired views.

{% highlight c# %}

	FrameLayout ContentFrame=new FrameLayout(this); 
	ContentFrame.SetBackgroundColor(Color.WHITE);
	ImageView img1 = new ImageView(this);
	img1.SetImageResource(R.drawable.menu);
	img1.SetScaleType(ImageView.ScaleType._FIT_XY_);
	ContentFrame.SetBackgroundColor(Color.WHITE);
	ContentFrame.AddView(img1);
	navigationDrawer.ContentView=ContentFrame;

{% endhighlight %}

### Setting DrawerContent View

The sliding main content of the NavigationDrawer which is a part of DrawerPanel can be set using `DrawerContentView` property with desired views.

{% highlight c# %}

	List<String> list = new List<String>();
	list.Add("Home");
	list.Add("Profile");
	list.Add("Inbox");
	list.Add("Outbox");
	list.Add("Sent Items");
	list.Add("Trash");
	ArrayAdapter<String> arrayAdapter =new ArrayAdapter<String>(this, Android.Resource.Layout.SimpleListItem1,list);
	listView.Adapter=arrayAdapter;
	listView.SetBackgroundColor(Color.White);
	listView.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent,ViewGroup.LayoutParams.MatchParent);
	contentLayout.AddView(listView);
	contentLayout.Orientation=Orientation.Vertical;
	FrameLayout frame = new FrameLayout (this);
	frame.LayoutParameters = new ViewGroup.LayoutParams (ViewGroup.LayoutParams.MatchParent, ViewGroup.LayoutParams.MatchParent);
	frame.SetBackgroundColor(Color.White);
	frame.AddView (contentLayout);
	//Add Drawer content view to Navigation
	navigationDrawer.DrawerContentView=frame;	

{% endhighlight %}