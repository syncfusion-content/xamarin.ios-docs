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

{% endtabs %}

![](images/Drawercontentview.png)

## Drawer Header Content

Instead of providing everything in the drawer content view, `DrawerHeaderView` property can be used to display certain information like user id or names in the header part.

{% tabs %}

{% highlight c# %}

	UIImageView userImgLabel=new UIImageView();
	userImgLabel.Frame =new CGRect ((this.Frame.Width/2)-100, 10, 80, 80);
	userImgLabel.Image = new UIImage ("Images/User.png");
	UILabel usernameLabel = new UILabel ();
	usernameLabel.Frame =new CGRect (0, 70, sideMenuController.DrawerWidth, 30);
	usernameLabel.Text="James Pollock";
	usernameLabel.TextColor = UIColor.White;
	usernameLabel.TextAlignment = UITextAlignment.Center;
	LinearLayout headerLayout = new LinearLayout(this);
	headerLayout.Orientation=LinearLayout.VERTICAL;
	headerLayout.BackgroundColor=UIColor.parseColor("#1aa1d6");
	headerLayout.Gravity(Gravity.CENTER);
	headerLayout.AddSubview(userImg);
	headerLayout.AddSubview(userName);
	navigationDrawer.DrawerHeaderView.Add(headerLayout);
 
{% endhighlight %}

{% endtabs %}

![](images/Drawerheadview.png)


## Drawer Footer Content

Similar to drawer header view, the `DrawerFooterView` property can be used to set footer content. For ex: Logout option or Exit option can be placed at Footer part.

{% tabs %}

{% highlight c# %}

	UILabel usernameLabel = new UILabel ();
	usernameLabel.Frame =new CGRect (0, 70, sideMenuController.DrawerWidth, 30);
	usernameLabel.Text="James Pollock";
	usernameLabel.TextColor = UIColor.White;
	usernameLabel.TextAlignment = UITextAlignment.Center;
	LinearLayout footerLayout = new LinearLayout(); 
	footerLayout.Orientation=LinearLayout.VERTICAL; 
 	footerLayout.BackgroundColor=UIColor._parseColor_("#1aa1d6"); 
	footerLayout.Gravity(Gravity._Top_);
	footerLayout.AddSubview(userName);
	navigationDrawer.DrawerFooterView.Add(footerLayout);

{% endhighlight %}

{% endtabs %}

![](images/Drawerfooterview.png)

## Drawer Size

Gets or sets the height and width of the DrawerView panel in the NavigationDrawer control using `DrawerHeight` and `DrawerWidth` properties.

{% tabs %}

{% highlight c# %}

	navigationDrawer.DrawerHeight=300;
    navigationDrawer.DrawerWidth=300;

{% endhighlight %}

{% endtabs %}