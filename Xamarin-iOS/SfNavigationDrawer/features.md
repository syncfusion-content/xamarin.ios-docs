---
layout: post
title: Various features of Syncfusion NavigationDrawer control for Xamarin.iOS
description: Learn how to set content view, drawer content view, footer view, header view, drawer size in NavigationDrawer.
platform: Xamarin.iOS
control: NavigationDrawer
documentation: ug
---

# Features

## ContentView

The main view of the NavigationDrawer can be set using `ContentView` property with desired views.

{% highlight c# %}

	FrameLayout ContentFrame=new FrameLayout(this); 
	ContentFrame.SetBackgroundColor(Color.WHITE);
	ImageView img1 = new ImageView(this);
	img1.SetImageResource(R.drawable._menu_);
	img1.SetScaleType(ImageView.ScaleType._FIT_XY_);
	ContentFrame.SetBackgroundColor(Color.WHITE);
	ContentFrame.AddView(img1);
	navigationDrawer.ContentView=ContentFrame;
	
{% endhighlight %}
	
![](images/Content-View.png)

## DrawerContentView

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
	frame.SetBackgroundColor (Color.White);
	frame.AddView (contentLayout);
	//Add Drawer content view to Navigation
	slideDrawer.DrawerContentView=frame;	

{% endhighlight %}

![](images/DrawerContentView.png)

## DrawerFooterView

Gets or sets the footer for the DrawerView panel in the SfNavigationDrawer control using `DrawerFooterView` property.

{% highlight c# %}

	TextView userName= new TextView(this);
	userName.Text="James Pollock";
	userName.SetGravity(Gravity.CENTER);
	userName.TextSize=20;
	userName.SetBackgroundColor(Color._TRANSPARENT_); text.setTextColor(Color._WHITE_);
	LinearLayout footerLayout = new LinearLayout(this); 
	footerLayout.Orientation=LinearLayout.VERTICAL; 
 	footerLayout.SetBackgroundColor(Color._parseColor_("#1aa1d6")); 
	footerLayout.SetGravity(Gravity._Top_);
	footerLayout.SetPadding(0, 20, 0, 0);
	footerLayout.AddView(userName);
	navigationDrawer.DrawerFooterView=footerLayout;

{% endhighlight %}

![](images/DrawerFooterView.png)

## DrawerHeaderView

Gets or sets the header of the DrawerView panel in the SfNavigationDrawer control using `DrawerHeaderView` property.

{% highlight c# %}

	ImageView userImg= new ImageView(this);
	userImg.SetImageResource(R.drawable.user);
	userImg.SetBackgroundColor(Color.parseColor("#1aa1d6"));
	TextView userName= new TextView(this);
	userName.Text="James Pollock";
	userName.SetGravity(Gravity.CENTER);
	userName.TextSize=20;
	userName.SetBackgroundColor(Color.TRANSPARENT);
	userName.TextColor=Color.WHITE;
	LinearLayout headerLayout = new LinearLayout(this);
	headerLayout.Orientation=LinearLayout.VERTICAL;
	headerLayout.SetBackgroundColor(Color.parseColor("#1aa1d6"));
	headerLayout.SetGravity(Gravity.CENTER);
	headerLayout.SetPadding(0, 20, 0, 0);
	headerLayout.addView(userImg);
	headerLayout.AddView(userName);
	navigationDrawer.DrawerHeaderView=headerLayout;
 
{% endhighlight %}

![](images/DrawerHeaderView.png)

## Drawer Size

Gets or sets the height and width of the DrawerView panel in the NavigationDrawer control using `DrawerHeight` and `DrawerWidth` properties.

{% highlight c# %}

	sfNavigationDrawer.setDrawerHeight(300);
        sfNavigationDrawer.DrawerWidth=300;

{% endhighlight %}