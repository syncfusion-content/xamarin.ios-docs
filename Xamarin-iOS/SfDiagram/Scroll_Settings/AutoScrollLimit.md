---
layout: post
title: Auto-Scroll Limit in Xamarin.iOS Diagram control | Syncfusion®
description: Learn here all about Auto-Scroll Limit support in Syncfusion<sup>&reg;</sup>; Xamarin.iOS Diagram (SfDiagram) control and more.
platform: xamarin.ios
control: SfDiagram
documentation: ug
---

# Auto-Scroll Limit in Xamarin Diagram (SfDiagram)

The auto-scroll limit allows you to define the scrollable region of the Diagram while the page is getting auto-scrolled. The `AutoScrollLimit` property of scroll settings class helps to limit the auto scrolling area. It includes the following options:

* Infinity: Allows auto-scroll in all directions without any restriction.
* Diagram: Allows auto-scroll within the Diagram content.
* Limited: Allows auto-scroll within the specified area.

The default operation is `Infinity.`

{% tabs %}
{% highlight C# %}
//Initialize the SfDiagram.
SfDiagram diagram = new SfDiagram();
//Initialize the scroll setting with auto scroll limit and scrolling area.
diagram.ScrollSettings = new ScrollSettings()
{
    AutoScrollLimit = ScrollLimit.Limited,
    ScrollableArea = new Rect(0,0,1500,1500),
};
{% endhighlight %}
{% endtabs %}

| AutoScrollLimit | Output |
|---|---|
| Infinity |![AutoScroll infinity](ScrollSettings_Images/AutoScrollLimit_Infinity.gif) |
| Diagram |![AutoScroll diagram](ScrollSettings_Images/AutoScrollLimit_DiagramContent.gif) |
| Limited <br> ScrollableArea = (0,0,1500,1500) | ![AutoScroll limited](ScrollSettings_Images/AutoScrollLimit_Limited.gif) |
