---
layout: post
title: Various features of Syncfusion NavigationDrawer control for Xamarin.iOS
description: Learn how to set content view, drawer content view, footer view, header view, drawer size in NavigationDrawer.
platform: Xamarin.iOS
control: NavigationDrawer
documentation: ug
---

# Setting Main Content

The SfNavigationDrawer is mainly divided into two parts, such as [Main Content](#main-content) and  [Drawer Panel Content](/Xamarin/SfNavigationDrawer/Drawer-Content "Sliding Panel Contents")

## Main Content

The main display view that displays our various content of the app can be set using `ContentView` property with desired views.

{% tabs %}

{% highlight c# %}

	UIView background=new UIView(new CGRect(0,50,this.Frame.Width,this.Frame.Height+72));
	background.BackgroundColor = UIColor.White;
	setvalue1 (0);
	this.Add(background);
	UIImageView userImgLabel=new UIImageView();
	userImgLabel.Frame =new CGRect ((this.Frame.Width/2)-100, 10, 80, 80);
	userImgLabel.Image = new UIImage ("Images/User.png");
	
	UILabel headerContentLabel = new UILabel ();
	headerContentLabel.Frame =new CGRect ((bounds.Width/2)-100, 10, 200, 30);
	headerContentLabel.Text="Home";
	headerContentLabel.TextColor = UIColor.White;
	headerContentLabel.TextAlignment = UITextAlignment.Center;
	this.AddSubview (headerContentLabel);
	
	UILabel textBlockLabel1 = new UILabel ();
	textBlockLabel1.Frame = new CGRect (15, 10, content.Frame.Width-20, 300);
	textBlockLabel1.Text = "Lorem ipsum dolor sit amet, lacus amet amet ultricies. Quisque mi venenatis morbi libero, orci dis, mi ut et class porta, massa ligula magna enim, aliquam orci vestibulum tempus. Turpis facilisis vitae consequat, cum a a, turpis dui consequat massa in dolor per, felis non amet. Auctor eleifend in omnis elit vestibulum, donec non elementum tellus est mauris, id aliquam, at lacus, arcu pretium proin lacus dolor et. Eu tortor, vel ultrices amet dignissim mauris vehicula. Lorem tortor neque, purus taciti quis id. Elementum integer orci accumsan minim phasellus vel.";
	textBlockLabel1.LineBreakMode = UILineBreakMode.WordWrap;
	textBlockLabel1.TextAlignment = UITextAlignment.Justified;
	textBlockLabel1.Lines = 0;
	textBlockLabel1.Font = UIFont.FromName ("Helvetica", 15f);
	
	content.AddSubview (textBlockLabel1);
	content.Add (userImgLabel);
	background.Add(content);
	
{% endhighlight %}

{% endtabs %}
	
![](images/content-view.png)