---
title: Port
description: Briefs about port in SfDiagram
platform: Xamarin.iOS
control: SfDiagram
documentation: UG
keywords: 
---
# Port
SfDiagram defines custom ports for making connections. When a connector is connected between two nodes, its end points are automatically docked to the nearest node boundary and the port  act as the connection points. It allows to create connections with only specific points.

## Create ports for a node
To add a port, you should define the port object and add it to ports property of node. The NodeOffsetX and NodeOffsetY property of port accepts an object of fractions and used to determine the position of ports.
The following code illustrates how to add ports to node:
{% tabs %}
{% highlight c# %}
//Creating node instance
Node node1 = new Node() { OffsetX = 300, OffsetY = 300, Width = 100, Height = 100, ShapeType = ShapeType.Rectangle };
sfDiagram.AddNode(node1);
Node node2 = new Node() { OffsetX = 600, OffsetY = 600, Width = 100, Height = 100, ShapeType = ShapeType.Rectangle };
sfDiagram.AddNode(node2);
// creating port instance
Port port1 = new Port();
port1.NodeOffsetX = 0.5;
port1.NodeOffsetY = 0;
Port port2 = new Port();
port2.NodeOffsetX = 0.5;
port2.NodeOffsetY = 1;
//adding port to the node instance
node1.Ports.Add(port1);
node2.Ports.Add(port2);
//creating and connecting the ports with connector
Connector connector = new Connector() { SourceNode = node1, TargetNode = node2, SourcePort = port1, TargetPort = port2 };
sfDiagram.AddConnector(connector);
{% endhighlight %}
{% endtabs %}
![](Port_images/Port_img1.jpeg)

## Accessing a port from the node instance
You can access the port by its index from the ports property in a node.
The following code illustrates how to access a port from the node instance:
{% tabs %}
{% highlight c# %}
Node node = sfDiagram.Nodes[0];
//Accessing the port by index from the Port collection in node
Port port = node.Ports[0];
{% endhighlight %}
{% endtabs %}

## Remove a port from the node
You can use Remove() method in ports property of a node to remove the port from a node.
The following code illustrates how to remove a port from the node:
{% tabs %}
{% highlight c# %}
Node node = sfDiagram.Nodes[0];
//Accessing the port by index from the Port collection in node
Port port = node.Ports[0];
//Removing the port for the node
node.Ports.Remove(port);
{% endhighlight %}
{% endtabs %}

# Customization
You can customize a port by resizing it and applying style to it.
The following code illustrates how to customize a port:
{% tabs %}
{% highlight c# %}
//Creating a node
Node node1 = new Node() { OffsetX = 300, OffsetY = 300, Width = 100, Height = 100, ShapeType = ShapeType.Rectangle };
sfDiagram.AddNode(node1);
// creating a port 
Port port = new Port();
port.NodeOffsetX = 0.5;
port.NodeOffsetY = 1;
//adding the port to the node instance
node1.Ports.Add(port);
port.Height = 10;
port.Width = 10;
//Setting the shape type for the port
port.ShapeType = ShapeType.Circle;
//Creating style instance for the port 
Style style = new Style();
style.StrokeWidth = 3;
style.Brush = new SolidBrush(UIColor.Black);
port.Style = style;
{% endhighlight %}
{% endtabs %}
