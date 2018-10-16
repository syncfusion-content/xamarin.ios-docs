---
title: Adding connectors in diagram control for Xamarin.iOS
description: Learn how to add connector in diagram control.
platform: Xamarin.iOS
control: SfDiagram
documentation: UG
keywords: 
---
# Connector
The connectors are objects used to create link between two points. Nodes or ports are used to represent the relationship between them.

## Create connector
The connector can be created by defining start and end points.
{% tabs %}
{% highlight c# %}
// creating connector instance
var connector1 = new Connector()
{
  SourcePoint = new CGPoint(100,100),
  TargetPoint = new CGPoint(300,300)
};
diagram.AddConnector(connector1);
{% endhighlight %}
{% endtabs %}

## Connections with nodes
The SourceNode and TargetNode properties allows to define the nodes to be connected. The following code example illustrates how to connect two nodes:
{% tabs %}
{% highlight c# %}
// creating node  instance
var node1 = new Node(100, 300, 100, 100);
diagram.AddNode(node1);
var node2 = new Node(300, 300, 100, 100);
diagram.AddNode(node2);
// creating connector instance and connecting nodes with it
var connector1 = new Connector()
{
  SourceNode = node1,
  TargetNode = node2
};
diagram.AddConnector(connector1);
{% endhighlight %}
{% endtabs %}
![connections with nodes in Xamarin.iOS diagram](Connector_images/Connector_img1.jpeg)

## Connections with ports
The SourcePort and TargetPort properties allows to create connections between some specific points of source or target nodes.

## Using port
The following code example illustrates how to create and connect the ports:
{% tabs %}
{% highlight c# %}
// creating node  instance
var node1 = new Node(100, 100, 100, 100);
//adding port instance to the node
node1.Ports.Add(new Port() { NodeOffsetX = 0.5, NodeOffsetY = 0 });
//adding node to the diagram
diagram.AddNode(node1);
// creating node  instance
var node2 = new Node(300, 300, 100, 100);
//adding port instance to the node
node2.Ports.Add(new Port() { NodeOffsetX = 0.5, NodeOffsetY = 1 }); 
//adding node to the diagram
diagram.AddNode(node2);
//creating and connecting the ports with connector
var connector1 = new Connector()
{
  SourceNode = node1,
  TargetNode = node2,
  SourcePort = node1.Ports[0],
  TargetPort = node2.Ports[0],
  SegmentType = SegmentType.OrthoSegment
};
diagram.AddConnector(connector1);
{% endhighlight %}
{% endtabs %}
![Using port in Xamarin.iOS diagram](Connector_images/Connector_img2.jpeg)

## Segments
The path of the connector is defined with a collection of segments.

## Straight
The straight segment allows to create a straight line. To create a straight line, you should specify the segment as StraightSegment. The following code example illustrates how to create a default straight segment:
{% tabs %}
{% highlight c# %}
// creating connector instance with define its segment type
var connector1 = new Connector()
{
  SourcePoint = new CGPoint(100,100),
  TargetPoint = new CGPoint(300,300),
SegmentType= SegmentType.StraightSegment
};
diagram.AddConnector(connector1);
{% endhighlight %}
{% endtabs %}
![Straight connector in Xamarin.iOS diagram](Connector_images/Connector_img3.jpeg)

## Orthogonal
The orthogonal segments are used to create segments that are perpendicular to each other.
Set the segment as OrthogonalSegment to create the default orthogonal segment. The following code example illustrates how to create a default orthogonal segment:
{% tabs %}
{% highlight c# %}
// creating connector instance with define its segment type
var connector1 = new Connector()
{
  SourcePoint = new CGPoint(100,100),
  TargetPoint = new CGPoint(300,300),
  SegmentType = SegmentType.OrthoSegment
};
diagram.AddConnector(connector1);
{% endhighlight %}
{% endtabs %}
![Orthogonal connector in Xamarin.iOS diagram](Connector_images/Connector_img4.jpeg)

## Curve
Curve segments are used to create links between two points, nodes, or ports with curve segments. The following code example illustrates how to create a default curve segment.
{% tabs %}
{% highlight c# %}
// creating connector instance with define its segment type
var connector1 = new Connector()
{
  SourcePoint = new CGPoint(100,100),
  TargetPoint = new CGPoint(300,300),
  SegmentType = SegmentType.CurveSegment;
};
diagram.AddConnector(connector1);
{% endhighlight %}
{% endtabs %}
![Curve connector in Xamarin.iOS diagram](Connector_images/Connector_img5.jpeg)

## Bezier 
Bezier curve has cubic curve segments that are configurable with the control points. The “SourceControlPoint” and “TargetControlPoint” of bezier segment allow you to modify the control points. The following code example illustrates how to create and modify a bezier curve segment via control points.
{% tabs %}
{% highlight c# %}
// creating connector instance with define its segment type
  
Connector connector = new Connector();
connector.SourcePoint = new CGPoint(100, 100);
connector.TargetPoint = new CGPoint(300, 300);
connector.SourceControlPoint = new CGPoint(100, 175);
connector.TargetControlPoint = new CGPoint(316, 175);
connector.SegmentType = SegmentType.BezierSegment;
diagram.AddConnector(connector);

{% endhighlight %}
{% endtabs %}
![Bezier connector in Xamarin.iOS diagram](Connector_images/Connector_img6.jpeg)

## Decorator
The start and end points of a connector can be decorated with some customizable shapes like arrow, circle, diamond, and square. You can decorate the connection end points with the SourceDecorator and TargetDecorator properties of connector.
The SourceDecoratorStyle and TargetDecoratorStyle properties define the shape of the decorators. The following code example illustrates how to create decorators of various shapes:
{% tabs %}
{% highlight c# %}
//creating connector instance with decorator-->
var connector1 = new Connector()
{
SourcePoint = new CGPoint(100,100),
TargetPoint = new CGPoint(300,300),
SourceDecoratorType = DecoratorType.Circle,
TargetDecoratorType = DecoratorType.Diamond,
SegmentType = SegmentType.StraightSegment
};
diagram.AddConnector(connector1);
{% endhighlight %}
{% endtabs %}
![Connector decorator in Xamarin.iOS diagram](Connector_images/Connector_img7.jpeg)

## Remove connector
There are two ways to remove connector from the connection, they are:
1. Passing the connector as parameter to remove connector method in the diagram.
The following code example illustrates how to remove a connector from the connection:
{% tabs %}
{% highlight c# %}
//creating connector instance
var connector1 = new Connector()
{
  SourcePoint = new CGPoint(100,100),
  TargetPoint = new CGPoint(300,300)
};
//adding connector to the diagram
diagram.AddConnector(connector1);
//removing connector from the diagram using object
diagram.RemoveConnector(connector1);
{% endhighlight %}
{% endtabs %}
2. Passing the index value of the connector to remove connector method in the diagram (using RemoveAt method).
The following code example illustrates how to remove a connector from connection:
{% tabs %}
{% highlight c# %}
//creating connector instance
var connector1 = new Connector()
{
  SourcePoint = new CGPoint(100,100),
  TargetPoint = new CGPoint(300,300)
};
//adding connector to the diagram
diagram.AddConnector(connector1);
//removing connector from the diagram using index
diagram.Connectors.RemoveAt(0);
{% endhighlight %}
{% endtabs %}

## Appearance
The StrokeThickness, stroke are the set of properties. The style of line connectors and decorators can be customized with that properties.

## Connector appearance
The following code example illustrates how to customize the connector appearance:
{% tabs %}
{% highlight c# %}
// creating connector instance
var connector1 = new Connector()
{
  SourcePoint = new CGPoint(100,100),
  TargetPoint = new CGPoint(300,300),
  SegmentType = SegmentType.StraightSegment
};
//defining connector styles
connector1.Style = new Style()
{
  StrokeBrush = new SolidBrush(UIColor.Gray),
  StrokeStyle = StrokeStyle.Dashed,
  StrokeWidth = 4
};
diagram.AddConnector(connector1);
{% endhighlight %}
{% endtabs %}
![Connector appearance in Xamarin.iOS diagram](Connector_images/Connector_img8.jpeg)

## Decorator appearance
The following code example illustrates how to customize the appearance of the decorator:
{% tabs %}
{% highlight c# %}
// creating connector instance with decorator
var connector1 = new Connector()
{
  SourcePoint = new CGPoint(100,100),
  TargetPoint = new CGPoint(300,300),
  SegmentType = SegmentType.StraightSegment,
  SourceDecoratorType = DecoratorType.Circle,
  TargetDecoratorType = DecoratorType.Diamond
};
//defining decorator style for a connector
connector1.TargetDecoratorStyle = new DecoratorStyle()
{
  Fill = UIColor.Yellow,
  StrokeColor = UIColor.Brown,
  StrokeWidth = 4,
  Size = 12
};
// defining decorator style for a connector
connector1.SourceDecoratorStyle = new DecoratorStyle()
{
  Fill = UIColor.Green,
  StrokeColor = UIColor.Gray,
  StrokeWidth = 5,
  Size = 12
};
diagram.AddConnector(connector1);
{% endhighlight %}
{% endtabs %}
![Decorator appearance in Xamarin.iOS diagram](Connector_images/Connector_img9.jpeg)

