---
layout: post
title: Display Type
description: Different display types available in Syncfusion TabView control for Xamarin.iOS platform
platform: Xamarin.iOS
control: TabView
documentation: ug
---

# Display Type

Tab view will display the title of each tab item by default. It can be changed to any of the below type.

* Text only.
* Image only.
* Image with text.
* No header.

![](images/Display-Type/xamarin_ios_tabstyle01.png)


It can be changed by settings the `DisplayMode` property of `SfTabView`.

{% tabs %}

{% highlight C# %}

tabView.DisplayMode = TabDisplayMode.ImageWithText;

{% endhighlight %}

{% endtabs %}

`No header` can be used when header is not needed for the tab view control, so content space will be occupied in the entire available height.

N> Image appearance in the header can be achieved through font icons.

## How to change the selection color for text and font icons?

Selected index can be differentiated by setting `SelectionColor` property of `SfTabItem`.

{% tabs %}

{% highlight C# %}

var tabViewItem = new SfTabItem()
			{
				Title = "Calls",
				TitleFontColor = Color.Green,
			}
			
{% endhighlight %}

{% endtabs %}

Further customizations of header are discussed in the below sections.

* How to customize text appearance of the header title?
* How to set and customize font icons appearance in the header?
* Setting font file for font icons.

## How to customize text appearance of the header title?

{% tabs %}

{% highlight C# %}

var tabViewItem = new SfTabItem()
			{
				Title = "Calls",
				Content = allContactsGrid,
				TitleFontColor = Color.Red,
				
			}
			
{% endhighlight %}

{% endtabs %}

## How to set and customize font icons appearance in the header?

Add the font file into your application by following the below steps.

**Adding font file for iOS**

* Add the font file with Build Action: `BundleResource`, and
* Update the `Info.plist` file (Fonts provided by application, or UIAppFonts, key).

**Setting font file for font icons**

{% tabs %}

{% highlight C# %}

var tabViewItem = new SfTabItem
		{
			Title = "Calls",
			Content = allContactsGrid,
			IconFont = "a", // setting value for font icons as mentioned in *.ttf.
			FontIconFontColor = Color.LightBlue,
			FontIconFont = UIFont.FromName("TabIcons", 20);
		};

			
{% endhighlight %}

{% endtabs %}
