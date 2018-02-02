---
title: Adding annotation for node and connector
description: Learn how to add annotation in node and connector
platform: Xamarin.iOS
control: SfDiagram
documentation: UG
keywords: 
---
# Annotations
Annotations is a block of text that can be displayed over a node or connector. Annotation is used to represent an object textually with a string, that can be edited at run time.
You can add multiple labels to a node or connector.

## Create Annotation
Define the annotation and add that in the annotations property of node or connector to add annotations. The content property of annotation defines the object to be displayed. The following code illustrates how to create annotation:
{% tabs %}
{% highlight c# %}
//To Add Annotation for Node
Node node1 = new Node(100, 300, 100, 100);
node1.Annotations.Add(new Annotation() { Content = "Label" });
diagram.AddNode(node1);
// To Add Annotation for Connector
Connector Connector1 = new Connector();
Connector1.SourcePoint = new CGPoint(100, 100);
Connector1.TargetPoint = new CGPoint(200, 200);
Connector1.Annotations.Add(new Annotation() { Content = "Label" });diagram.AddConnector(Connector1);
{% endhighlight %}
{% endtabs %}
![](Annotation_images/Annotation_img1.jpeg)

## Accessing an annotation from node and connector instance
You can access the node or connector annotation using annotation name. The following code illustrates how to access annotation:
{% tabs %}
{% highlight c# %}
// Accessing Annotation 
Connector Connector1 = new Connector();
Connector1.SourcePoint = new CGPoint(100, 100);
Connector1.TargetPoint = new CGPoint(300, 300);
var label = new Annotation() { Content = "Label" };
Connector1.Annotations.Add(label);
diagram.AddConnector(Connector1);
Connector1.Annotations.Remove(label);
{% endhighlight %}
{% endtabs %}

## Remove an annotation
You can remove the annotation using index value. The following code illustrates how to remove annotation:
{% tabs %}
{% highlight c# %}
//Remove Annotation using Index
Connector Connector1 = new Connector();
Connector1.SourcePoint = new CGPoint(100, 100);
Connector1.TargetPoint = new CGPoint(300, 300);
var label = new Annotation() { Content = "Label" };
Connector1.Annotations.Add(label);
diagram.AddConnector(Connector1);
Connector1.Annotations.RemoveAt(0);
{% endhighlight %}
{% endtabs %}

## Annotation Customization
You can customize the annotation using properties. The following code illustrates how to customize an annotation.
{% tabs %}
{% highlight c# %}
// Annotation customization for node 
Node node1 = new Node(100,300,100,100);
var label = new Annotation()
{
Content = "Label",
FontFamily = "Arial",
FontSize = 14,
TextBrush = new SolidBrush(UIColor.Red)
} ;
node1.Annotations.Add(label);
diagram.AddNode(node1);
// Annotation customization for connector 
Connector Connector1 = new Connector();
Connector1.SourcePoint = new CGPoint(100, 100);
Connector1.TargetPoint = new CGPoint(200, 200);
var label = new Annotation()
{
Content = "Label",
FontFamily = "Arial",
FontSize = 14,
TextBrush = new SolidBrush(UIColor.Red)
};
Connector1.Annotations.Add(label);
diagram.AddConnector(Connector1);
{% endhighlight %}
{% endtabs %}
![](Annotation_images/Annotation_img2.jpeg)

## Alignment
Annotation can be aligned relatively with node boundaries. It has horizontal and vertical alignment settings. It will be complex when using four alignments together but gives you more control. 
{% tabs %}
{% highlight c# %}
// Annotation alignment for Node
Node node1 = new Node(100,300,100,100);
Annotation label = new Annotation()
{
       Content = "Label",
       HorizontalAlignment = HorizontalAlignment.Center,
      VerticalAlignment = VerticalAlignment.Top
};
node1.Annotations.Add(label);
diagram.AddNode(node1);
//Annotation alignment for Connector
Connector Connector1 = new Connector();
Connector1.SourcePoint = new CGPoint(100, 100);
Connector1.TargetPoint = new CGPoint(200, 200);
Connector1.Annotations.Add(new Annotation() { Content = "Label", HorizontalAlignment = HorizontalAlignment.Center,
      VerticalAlignment = VerticalAlignment.Center
 });
diagram.AddConnector(Connector1);
{% endhighlight %}
{% endtabs %}
![](Annotation_images/Annotation_img3.jpeg)

