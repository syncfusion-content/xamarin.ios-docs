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

{Syncfusion Installed location}\Essential Studio {version number}\lib

Add the following assembly references to the iOS project,

android\Syncfusion.SfNavigationDrawer.iOS.dll

### Initializing NavigationDrawer

* Adding reference to navigationDrawer.

{% highlight c# %}

	using Syncfusion.SFNavigationDrawer.iOS;
	
{% endhighlight %}

* Create an instance of SfNavigationDrawer.

{% highlight c# %}

	SFNavigationDrawer navigationDrawer = new SFNavigationDrawer(this);
	this.AddSubview(navigationDrawer);
	
{% endhighlight %}


### Setting Content View

The main view of the NavigationDrawer can be set using `ContentView` property with desired views.

{% highlight c# %}

	UIView background=new UIView(new CGRect(0,50,this.Frame.Width,this.Frame.Height+72));
	background.BackgroundColor = UIColor.White;
	setvalue1 (0);
	this.Add(background);
	UIImageView userImgLabel=new UIImageView();
	userImgLabel.Frame =new CGRect ((this.Frame.Width/2)-100, 10, 80, 80);
	userImgLabel.Image = new UIImage ("Images/User.png");
	content.Add (userImgLabel);
	background.Add(content);

{% endhighlight %}

### Setting DrawerContent View

The sliding main content of the NavigationDrawer which is a part of DrawerPanel can be set using `DrawerContentView` property with desired views.

{% highlight c# %}

	UITableView table = new UITableView(new CGRect(0, 0, sideMenuController.DrawerWidth, this.Frame.Height)); // defaults to Plain style
	tableItems = new string[] {"Home","Profile","Inbox","Outbox","Sent Items","Trash"};
	TableSource tablesource = new TableSource(tableItems);
	tablesource.customise = false;
	table.Source = tablesource;
	this.BackgroundColor = UIColor.FromRGB(63,134,246);
	HeaderView = new UIView ();
	HeaderView.Frame = new CGRect (0, 0, sideMenuController.DrawerWidth, 100);
	HeaderView.BackgroundColor = UIColor.FromRGB (49, 173, 225);
	UIView centerview = new UIView ();
	centerview.Frame = new CGRect (0, 100, sideMenuController.DrawerWidth, 500);
	centerview.Add (table);
	usernameLabel = new UILabel ();
	usernameLabel.Frame =new CGRect (0, 70, sideMenuController.DrawerWidth, 30);
	usernameLabel.Text=(NSString)"James Pollock";
	usernameLabel.TextColor = UIColor.White;
	usernameLabel.TextAlignment = UITextAlignment.Center;
	HeaderView.AddSubview (usernameLabel);

	userImg=new UIImageView();
	userImg.Frame =new CGRect ((sideMenuController.DrawerWidth/2)-25, 15, 50, 50);
	userImg.Image = new UIImage ("Images/User.png");

	HeaderView.AddSubview (userImg);

	sideMenuController.DrawerHeaderView = HeaderView;
	sideMenuController.DrawerContentView = centerview;
	sideMenuController.Position = SFNavigationDrawerPosition.SFNavigationDrawerPositionLeft;

	this.AddSubview (sideMenuController);

{% endhighlight %}