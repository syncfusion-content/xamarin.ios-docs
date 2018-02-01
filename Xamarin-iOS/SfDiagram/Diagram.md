---
title: Diagram for Essential Xamarin.iOS Diagram
description: Diagram
platform: Xamarin.iOS
control: SfDiagram
documentation: UG
keywords: 
---
# Diagram
The diagram control allows to create different types of diagrams such as flow charts, use case diagrams, workflow process diagrams, and more.

## PageSettings
The Page settings are enabled to customize the appearance, width, and height of the diagram page. The size and appearance of the diagram pages can be customized with the PageSettings property.
The PageWidth and PageHeight properties of page settings define the size of the page. You can also customize the appearance of page regions with the BackgroundColor property.
The following code illustrates how to customize the page size and appearance of the page:
{% tabs %}
{% highlight c# %}
//Sets Page background 
diagram.BackgroundColor = Color.Lime; 
//Sets Page size 
diagram.PageSettings.PageWidth = 500; 
diagram.PageSettings.PageHeight = 500; 
//Customizes the appearance of Page
diagram.PageSettings.PageBackGround= Color.White;
{% endhighlight %}
{% endtabs %}

## Stencil:
Stencil has a collection of symbols. It is used to clone the desired symbol by dragging it from the stencil and dropping it into the SfDiagram.
The following code snippet illustrates how to add the stencil:
{% tabs %}
{% highlight c# %}
Stencil stencil = new Stencil(); 
View.AddSubview(stencil);
{% endhighlight %}
{% endtabs %}

## NodeTemplate:
You can replace the entire node template with your own design using SfDiagram.NodeTemplate property.
The following code snippet illustrates replacing the node template:
{% tabs %}
{% highlight c# %}
var template = new UIView()
template.Frame=new CGRect(0,0,100,100);
template.Layout.BorderWidth=1;
var image=new UIImageView();
image.Frame=new CGRect(0,0,100,100);
image.Image=UIImage.FromBundle(“employee.png”);
template.AddSubview(image);
diagram.NodeTemplate = template;
{% endhighlight %}
{% endtabs %}

## Diagram constraints
The constraints property of diagram allows you to enable or disable certain features. 
This will enable or disable the following node behavior.
* Drag
* Resize
* Rotate
* AnnotationEditing
* EnableSelectors
* EnableZoomAndPan
* IsReadOnly
**Example**
The following code illustrates how to disable the item dragging:
{% tabs %}
{% highlight c# %}
SfDiagram diagram = new SfDiagram();
// Disable the item dragging
diagram.EnableDrag = false;
View.AddSubview(diagram);
{% endhighlight %}
{% endtabs %}

