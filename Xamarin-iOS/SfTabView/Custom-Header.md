---
layout: post
title:  Custom Header
description: Custom Header in Syncfusion TabView control for Xamarin.iOS platform
platform: Xamarin.iOS
control: TabView
documentation: ug
---

# Custom Header 

When the built-in view is not needed, it can be overridden by adding the custom view to the header region for a tab. 

{% tabs %}

{% highlight C# %}

UIButton allCallsButton = new UIButton();
	allCallsButton.SetTitle("All Calls", UIControlState.Normal);
	allCallsButton.BackgroundColor = UIColor.FromRGB(240, 240, 240);
	allCallsButton.TouchUpInside += AllCallsButton_Clicked;
	var tabViewItem = new SfTabItem()
	{
		Title = "Calls",
		Content = allContactsGrid,
		HeaderContent = allCallsButton
	};
			
{% endhighlight %}

{% endtabs %}

## How to handle events for custom view with tab view?

When you use button or similar control with clicked event, it can be handled directly and set to the SelectedIndex property to navigate the clicked view.

{% highlight C# %}

private void AllCallsButton_Clicked(object sender, EventArgs e)
{
	tabView.SelectedIndex = 0;
}
			
{% endhighlight %}


