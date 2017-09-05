---
layout: post
title: Various features of Syncfusion NavigationDrawer control for Xamarin.iOS
description: Learn how to set content view, drawer content view, footer view, header view, drawer size in NavigationDrawer.
platform: Xamarin.iOS
control: NavigationDrawer
documentation: ug
---

# Setting Main Content

The SfNavigationDrawer is mainly divided into two parts, such as [Main Content](#main-content) and  [Drawer Panel Content](/Xamarin-iOS/SfNavigationDrawer/Drawer-Content "Sliding Panel Contents")

## Main Content

The main display view that displays our various content of the app can be set using `ContentView` property with desired views.

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
			navigation.ContentView = contentView;
			this.Add(navigation);
		}
	}
}
	
{% endhighlight %}

{% endtabs %}
	
![](images/content-view.png)