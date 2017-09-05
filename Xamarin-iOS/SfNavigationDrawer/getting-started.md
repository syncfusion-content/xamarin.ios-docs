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

## Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio {version number}\lib

Add the following assembly references to the iOS project,

android\Syncfusion.SfNavigationDrawer.iOS.dll

## Add SfNavigationDrawer

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight c# %}

	using Syncfusion.SfNavigationDrawer.iOS;
	
{% endhighlight %}

{% endtabs %}

* Now add the SfNavigationDrawer control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight c# %}

SFNavigationDrawer navigation = new SFNavigationDrawer();
this.AddSubview(navigationDrawer);
	
{% endhighlight %}

{% endtabs %}

## Add Main Content 

The main view of the NavigationDrawer can be set using `ContentView` property with desired views.

{% tabs %}

{% highlight c# %}

	namespace NavigationDrawerTest
{
	public partial class ViewController : UIViewController
	{
		public ViewController(IntPtr handle) : base(handle)
		{
		}

		public override void ViewDidLoad()
		{
			base.ViewDidLoad();
			SFNavigationDrawer navigation = new SFNavigationDrawer();
			this.Add(navigation);
			navigation.Frame = new CGRect(0, 0, this.View.Frame.Width, this.View.Frame.Height);
			navigation.DrawerHeaderHeight = 100;
			navigation.DrawerWidth = 200;
			UIView contentView = new UIView(new CGRect(0, 0, this.View.Frame.Width, this.View.Frame.Height);
			UILabel homeLabel = new UILabel();
			homeLabel.Frame = new CGRect(5, 2, contentView.Frame.Width - 8, 30);
			homeLabel.Text = "Home";
			homeLabel.TextColor = UIColor.White;
			homeLabel.BackgroundColor = UIColor.FromRGB(49, 173, 225);
			homeLabel.TextAlignment = UITextAlignment.Center;
			contentView.AddSubview(homeLabel);
			UILabel textBlockLabel1 = new UILabel();
			textBlockLabel1.Frame = new CGRect(15, 20, contentView.Frame.Width - 10, 300);
			textBlockLabel1.Text = "Lorem ipsum dolor sit amet, lacus amet amet ultricies. Quisque mi venenatis morbi libero, orci dis, mi ut et class porta, massa ligula magna enim, aliquam orci vestibulum tempus. Turpis facilisis vitae consequat, cum a a, turpis dui consequat massa in dolor per, felis non amet. Auctor eleifend in omnis elit vestibulum, donec non elementum tellus est mauris, id aliquam, at lacus, arcu pretium proin lacus dolor et. Eu tortor, vel ultrices amet dignissim mauris vehicula. Lorem tortor neque, purus taciti quis id. Elementum integer orci accumsan minim phasellus vel.";
			textBlockLabel1.LineBreakMode = UILineBreakMode.WordWrap;
			textBlockLabel1.TextAlignment = UITextAlignment.Justified;
			textBlockLabel1.Lines = 0;
			textBlockLabel1.Font = UIFont.FromName("Helvetica", 15f);
			contentView.AddSubview(textBlockLabel1);

			UIButton drawerButton = new UIButton();
			drawerButton.SetTitle("Content View", UIControlState.Normal);
			drawerButton.Frame = new CGRect(45, 350, contentView.Frame.Width - 40, 30);
			drawerButton.BackgroundColor = UIColor.Gray;
			drawerButton.TouchUpInside += (object sender, EventArgs e) =>
			{
				navigation.ToggleDrawer();

			};
			contentView.AddSubview(drawerButton);
			navigation.ContentView = contentView;
			this.Add(navigation);
		}
	}
}

{% endhighlight %}

{% endtabs %}

## Add Drawer Content

The sliding main content of the NavigationDrawer which is a part of DrawerPanel can be set using `DrawerContentView` property with desired views.

{% tabs %}

{% highlight c# %}

	//DrawerView
		namespace NavigationDrawerTest
{
	public partial class ViewController : UIViewController
	{
		public ViewController(IntPtr handle) : base(handle)
		{
		}

		public override void ViewDidLoad()
		{
			base.ViewDidLoad();
			// Perform any additional setup after loading the view, typically from a nib.
			SFNavigationDrawer navigation = new SFNavigationDrawer();
			this.Add(navigation);
			navigation.Frame = new CGRect(0, 0, this.View.Frame.Width, this.View.Frame.Height);
			navigation.DrawerHeaderHeight = 100;
			navigation.DrawerWidth = 200;
            UIView contentView = new UIView(new CGRect(0, 0, this.View.Frame.Width, this.View.Frame.Height);
			UIButton menubutton = new UIButton();
			menubutton.Frame =new CGRect(10, 5, 25, 25);
			menubutton.SetBackgroundImage (new UIImage("Images/menu.png"), UIControlState.Normal);

			menubutton.TouchUpInside += (object sender, EventArgs e) => 
			{
				navigation.ToggleDrawer();
			};

			contentView.AddSubview (menubutton);
			navigation.ContentView = contentView;

			UIView headerView = new UIView(new CGRect(0, 0, navigation.DrawerWidth, 100));

			UIView HeaderView = new UIView();
			HeaderView.Frame = new CGRect(0, 0, navigation.DrawerWidth, 100);
			HeaderView.BackgroundColor = UIColor.FromRGB(49, 173, 225);
			UILabel usernameLabel = new UILabel();
			usernameLabel.Frame = new CGRect(0, 70, navigation.DrawerWidth, 30);
			usernameLabel.Text = (NSString)"James Pollock";
			usernameLabel.TextColor = UIColor.White;
			usernameLabel.TextAlignment = UITextAlignment.Center;
			HeaderView.AddSubview(usernameLabel);
			UIImageView userImg = new UIImageView(UIImage.FromBundle("Images/Image15.png"));
			userImg.Frame = new CGRect((navigation.DrawerWidth / 2) - 25, 15, 50, 50);
			HeaderView.AddSubview(userImg);
			headerView.AddSubview(HeaderView);

			UIView drawerContentView = new UIView(new CGRect(0, 0, navigation.DrawerWidth, 100));

			UIView centerview = new UIView();
			centerview.Frame = new CGRect(0, 0, navigation.DrawerWidth, 500);
			UIButton homeButton = new UIButton(new CGRect(0, 0, navigation.DrawerWidth, 50));
			homeButton.SetTitle("Home", UIControlState.Normal);
			homeButton.SetTitleColor(UIColor.Black, UIControlState.Normal);
			homeButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
			centerview.AddSubview(homeButton);

			UIButton profileButton = new UIButton(new CGRect(0, 50, navigation.DrawerWidth, 50));
			profileButton.SetTitle("Profile", UIControlState.Normal);
			profileButton.SetTitleColor(UIColor.Black, UIControlState.Normal);
			profileButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
			profileButton.Layer.CornerRadius = 0;
			profileButton.Layer.BorderColor = UIColor.FromRGB(0, 0, 0).CGColor;
			centerview.AddSubview(profileButton);

			UIButton inboxButton = new UIButton(new CGRect(0, 100, navigation.DrawerWidth, 50));
			inboxButton.SetTitle("Inbox", UIControlState.Normal);
			inboxButton.SetTitleColor(UIColor.Black, UIControlState.Normal);
			inboxButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
			inboxButton.Layer.CornerRadius = 0;
			inboxButton.Layer.BorderColor = UIColor.FromRGB(0, 0, 0).CGColor;
			centerview.AddSubview(inboxButton);

			UIButton outboxButton = new UIButton(new CGRect(0, 150, navigation.DrawerWidth, 50));
			outboxButton.SetTitle("Outbox", UIControlState.Normal);
			outboxButton.SetTitleColor(UIColor.Black, UIControlState.Normal);
			outboxButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
			outboxButton.Layer.CornerRadius = 0;
			outboxButton.Layer.BorderColor = UIColor.FromRGB(0, 0, 0).CGColor;
			centerview.AddSubview(outboxButton);

			UIButton sentItemsButton = new UIButton(new CGRect(0, 200, navigation.DrawerWidth, 50));
			sentItemsButton.SetTitle("SentItems", UIControlState.Normal);
			sentItemsButton.SetTitleColor(UIColor.Black, UIControlState.Normal);
			sentItemsButton.Layer.CornerRadius = 0;
			sentItemsButton.Layer.BorderColor = UIColor.FromRGB(0, 0, 0).CGColor;
			centerview.AddSubview(sentItemsButton);

			UIButton trashButton = new UIButton(new CGRect(0, 250, navigation.DrawerWidth, 50));
			trashButton.SetTitle("Trash", UIControlState.Normal);
			trashButton.SetTitleColor(UIColor.Black, UIControlState.Normal);
			trashButton.Layer.CornerRadius = 0;
			trashButton.Layer.BorderColor = UIColor.FromRGB(0, 0, 0).CGColor;
			centerview.AddSubview(trashButton);
			drawerContentView.AddSubview(centerview);

			navigation.DrawerContentView = drawerContentView;
			navigation.DrawerHeaderView = headerView;
			this.Add(navigation);

		}

	}
}

{% endhighlight %}

{% endtabs %}

![](images/getting-started.png)