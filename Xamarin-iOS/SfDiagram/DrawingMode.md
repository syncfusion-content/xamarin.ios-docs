---
title: Adding drawing mode in Diagram control for Xamarin.iOS
description: Learn how to add drawing mode in diagram control.
platform: Xamarin.iOS
control: Diagram
documentation: ug
keywords: 
---
# Drawing mode
Drawing mode is used to draw continuously on the diagram area for selected mode dynamically.

## Text node
This node has default annotation. TextNode mode will add continuous text node. The following code example illustrates how to enable TextNode mode.
{% tabs %}
{% highlight c# %}
diagram.DrawingMode = DrawingMode.TextNode;
{% endhighlight %}
{% endtabs %}

## Connector
Connector mode adds continuous orthogonal connectors on the diagram area. In this mode, you can connect connectors in between Points, Nodes, or Ports. The following code example illustrates how to enable Connector mode.
{% tabs %}
{% highlight c# %}
diagram.DrawingMode = DrawingMode.Connector;
{% endhighlight %}
{% endtabs %}
![Drawing mode in Xamarin.iOS diagram](DrawingMode_images/DrawingMode.gif)

