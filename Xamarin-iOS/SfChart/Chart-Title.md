---
layout: post
title: Chart Title | SFChart | Xamarin.iOS | Syncfusion
description: How to add and customize chart title in SFChart
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Chart Title

You can define and customize the Chart title using `Title` property of `SFChart`. The `Text` property of `SFChartTitle` is used to set the text for the title. 

Following properties are used to customize its appearance.

* `TextColor` – used to change the color of the text
* `BackgroundColor` – used to change the background color
* `BorderColor` – used to change the border color
* `BorderWidth` – used to change the border width
* `Font` – used to change the text size, font family and font weight
* `Margin` - used to change the margin for title

{% highlight c# %}

chart.Title.Text        = new NSString ("Efficiency of Oil Fired Power Production");

chart.Title.TextColor   = UIColor.Blue; 

{% endhighlight %}


![](charttitle_images/charttitle_img1.png)


## Text Alignment

You can align the title text content to the Start, Center or End of the title using the `TextAlignment` property of the `SFChartTitle`.

{% highlight c# %}

chart.Title.Text            = new NSString ("Efficiency of Oil Fired Power Production");

chart.Title.TextAlignment   = UITextAlignment.Left; 

chart.Title.TextColor       = UIColor.Blue; 

{% endhighlight %}


![](charttitle_images/charttitle_img2.png)