---
title: Adding gridlines in Diagram control for Xamarin.iOS | Syncfusion
description: Describes how to add gridlines,snapping gridlines and customization of gridlines in diagram control for Xamarin.iOS
platform: Xamarin.iOS
control: Diagram
documentation: ug
keywords: 
---
# Gridlines
Gridlines are the pattern of lines drawn behind the diagram elements. It provides a visual guidance when dragging or arranging the node on the diagram surface.

## Gridlines visibility
The “ShowGrid” property in PageSettings will show or hide the gridlines. The following code example illustrates how to enable grid visibility.
{% tabs %}
{% highlight c# %}
diagram.PageSettings.ShowGrid = true;
{% endhighlight %}
{% endtabs %}

## Customizing gridlines
Grid cell size and gridline color can be modified using the “GridSize” and “GridColor” properties respectively. The following code example illustrates how to customize the grid.
{% tabs %}
{% highlight c# %}
diagram.PageSettings.GridColor = Color.Pink;
diagram.PageSettings.GridSize = 14;
{% endhighlight %}
{% endtabs %}

## Snapping gridlines
Nodes can be aligned and resized easily using gridlines by enabling the snap to grid. The following code example illustrates how to enable the snap to grid.
{% tabs %}
{% highlight c# %}
diagram.PageSettings.SnapToGrid = true;
{% endhighlight %}
{% endtabs %}
![Snapping gridlines in Xamarin.iOS diagram](Gridlines_images/Gridlines.gif)

