---
layout: post
title: Various features of Syncfusion NavigationDrawer control for Xamarin.iOS
description: Learn how to set content view, drawer content view, footer view, header view, drawer size in NavigationDrawer.
platform: Xamarin.iOS
control: NavigationDrawer
documentation: ug
---

# Sliding Panel Contents

The sliding panel contents are divided into three parts and they are as follows
	
* [Drawer Content](#drawer-main-content)
* [Header Content](#drawer-header-content) 
* [Footer Content](#drawer-footer-content)

## Drawer Main Content

The sliding main content of the SfNavigationDrawer can be set with any view using `DrawerContentView`. This part mostly holds the list of menus that has to be selected to display the Main content.

{% tabs %}

{% highlight c# %}

	//DrawerView
	SFNavigationDrawer navigation = new SFNavigationDrawer();
			UIView headerView = new UIView(new CGRect(0, 0, 100, 100));

			UIView HeaderView = new UIView();
			HeaderView.Frame = new CGRect(0, 0, navigation.DrawerWidth, 100);
			HeaderView.BackgroundColor = UIColor.FromRGB(49, 173, 225);
			UILabel usernameLabel = new UILabel();
			usernameLabel.Frame = new CGRect(0, 70, navigation.DrawerWidth, 30);
			usernameLabel.Text = (NSString)"James Pollock";
			usernameLabel.TextColor = UIColor.White;
			usernameLabel.TextAlignment = UITextAlignment.Center;
			HeaderView.AddSubview(usernameLabel);
			UIImageView userImg = new UIImageView();
			userImg.Frame = new CGRect((navigation.DrawerWidth / 2) - 25, 15, 50, 50);
			userImg.Image = new UIImage("Images/User.png");
			HeaderView.AddSubview(userImg);
			headerView.AddSubview(HeaderView);

			UIView drawerContentView = new UIView(new CGRect(0, 0, navigation.DrawerWidth, 100));

			UIView centerview = new UIView();
			centerview.Frame = new CGRect(0, 0, navigation.DrawerWidth, 500);

			UIButton homeButton = new UIButton(new CGRect(0,0,navigation.DrawerWidth,50));
			homeButton.SetTitle("Home", UIControlState.Normal);
			homeButton.SetTitleColor(UIColor.Black, UIControlState.Normal);
			homeButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
			homeButton.Layer.CornerRadius = 0;
			homeButton.Layer.BorderWidth = 1;
			homeButton.Layer.BorderColor=UIColor.FromRGB(0, 0, 0).CGColor;
			centerview.AddSubview(homeButton);

			UIButton profileButton = new UIButton(new CGRect(0, 50, navigation.DrawerWidth, 50));
			profileButton.SetTitle("Profile", UIControlState.Normal);
			profileButton.SetTitleColor(UIColor.Black, UIControlState.Normal);
			profileButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
			profileButton.Layer.CornerRadius = 0;
			profileButton.Layer.BorderWidth = 1;
			profileButton.Layer.BorderColor = UIColor.FromRGB(0, 0, 0).CGColor;
			centerview.AddSubview(profileButton);

			UIButton inboxButton = new UIButton(new CGRect(0, 100, navigation.DrawerWidth, 50));
			inboxButton.SetTitle("Inbox", UIControlState.Normal);
			inboxButton.SetTitleColor(UIColor.Black, UIControlState.Normal);
			inboxButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
			inboxButton.Layer.CornerRadius = 0;
			inboxButton.Layer.BorderWidth = 1;
			inboxButton.Layer.BorderColor = UIColor.FromRGB(0, 0, 0).CGColor;
			centerview.AddSubview(inboxButton);

			UIButton outboxButton = new UIButton(new CGRect(0, 150, navigation.DrawerWidth, 50));
			outboxButton.SetTitle("Outbox", UIControlState.Normal);
			outboxButton.SetTitleColor(UIColor.Black, UIControlState.Normal);
			outboxButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
			outboxButton.Layer.CornerRadius = 0;
			outboxButton.Layer.BorderWidth = 1;
			outboxButton.Layer.BorderColor = UIColor.FromRGB(0, 0, 0).CGColor;
			centerview.AddSubview(outboxButton);

			UIButton sentItemsButton = new UIButton(new CGRect(0, 200, navigation.DrawerWidth, 50));
			sentItemsButton.SetTitle("SentItems", UIControlState.Normal);
			sentItemsButton.SetTitleColor(UIColor.Black, UIControlState.Normal);
			sentItemsButton.Layer.CornerRadius = 0;
			sentItemsButton.Layer.BorderWidth = 1;
			sentItemsButton.Layer.BorderColor = UIColor.FromRGB(0, 0, 0).CGColor;
			centerview.AddSubview(sentItemsButton);

			UIButton trashButton = new UIButton(new CGRect(0, 250, navigation.DrawerWidth, 50));
			trashButton.SetTitle("Trash", UIControlState.Normal);
			trashButton.SetTitleColor(UIColor.Black, UIControlState.Normal);
			trashButton.Layer.CornerRadius = 0;
			trashButton.Layer.BorderWidth = 1;
			trashButton.Layer.BorderColor = UIColor.FromRGB(0, 0, 0).CGColor;
			centerview.AddSubview(trashButton);
			drawerContentView.AddSubview(centerview);

			navigation.DrawerContentView =drawerContentView;
			navigation.DrawerHeaderView =headerView;
			this.AddSubview(navigation);

{% endhighlight %}

{% endtabs %}

![](images/Drawercontentview.png)

## Drawer Header Content

Instead of providing everything in the drawer content view, `DrawerHeaderView` property can be used to display certain information like user id or names in the header part.

{% tabs %}

{% highlight c# %}

SFNavigationDrawer navigation = new SFNavigationDrawer();
	UIImageView userImgLabel=new UIImageView();
	userImgLabel.Frame =new CGRect ((this.Frame.Width/2)-100, 10, 80, 80);
	userImgLabel.Image = new UIImage ("Images/User.png");
	UILabel usernameLabel = new UILabel ();
	usernameLabel.Frame =new CGRect (0, 70, navigation.DrawerWidth, 30);
	usernameLabel.Text="James Pollock";
	usernameLabel.TextColor = UIColor.White;
	usernameLabel.TextAlignment = UITextAlignment.Center;
	UIView headerLayout = new UIView();
	headerLayout.AddSubview(userImgLabel);
	headerLayout.AddSubview(usernameLabel);
	navigation.DrawerHeaderHeight=100;
	navigation.DrawerHeaderView =headerLayout;
	this.AddSubview(navigation);
 
{% endhighlight %}

{% endtabs %}

![](images/Drawerheadview.png)


## Drawer Footer Content

Similar to drawer header view, the `DrawerFooterView` property can be used to set footer content. For ex: Logout option or Exit option can be placed at Footer part.

{% tabs %}

{% highlight c# %}

SFNavigationDrawer navigation = new SFNavigationDrawer();
	UILabel usernameLabel = new UILabel ();
	usernameLabel.Frame =new CGRect (0, 70, navigation.DrawerWidth, 30);
	usernameLabel.Text="James Pollock";
	usernameLabel.TextColor = UIColor.White;
	usernameLabel.TextAlignment = UITextAlignment.Center;
	UIView footerLayout = new UIView(); 
	footerLayout.AddSubview(usernameLabel);
	navigation.DrawerFooterHeight=100;
	navigation.DrawerFooterView =footerLayout;
	this.AddSubview(navigation);

{% endhighlight %}

{% endtabs %}

![](images/Drawerfooterview.png)

## Drawer Size

Gets or sets the height and width of the DrawerView panel in the NavigationDrawer control using `DrawerHeight` and `DrawerWidth` properties.

{% tabs %}

{% highlight c# %}

	navigation.DrawerHeight=300;
    navigation.DrawerWidth=300;

{% endhighlight %}

{% endtabs %}