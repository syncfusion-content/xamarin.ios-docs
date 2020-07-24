---
layout: post
title:  Add & modify shapes using PDF viewer Xamarin.iOS | Syncfusion
description: PDF viewer Xamarin.iOS allows user to add, move and delete shapes such as line, rectangle & ellipse PDF document
platform: Xamarin.iOS
control: SfPdfViewer
documentation: ug
---

# Working with Shape Annotations

Shape Annotations are used to add annotations in the form of shapes such as rectangle, ellipse, horizontal line, and vertical line at the specific area of interest. PDF viewer allows you to include shape annotations in a PDF document and provides options to modify or remove the existing shape annotations. The supported shape annotations are: 

1.	Rectangle
2.	Circle
3.	Line
4.	Arrow
5.	Polygon.

## Adding shape annotations

### Enabling the shape annotation mode

Set the [`AnnotationMode`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.SfPdfViewer~AnnotationMode.html) of the PDF Viewer to any of the shape annotations to enable it. Once the shape annotation mode is set, zooming, panning, and scrolling will be disabled. A shape annotation can be drawn only on the currently visible pages. Refer to the following code.

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Setting the annotation mode to Rectangle
pdfViewer.AnnotationMode = AnnotationMode.Rectangle;

{% endhighlight %}
{% endtabs %}

### Disabling shape annotation mode

Set the [`AnnotationMode`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.SfPdfViewer~AnnotationMode.html) of the PDF Viewer to ‘None’ to disable the shape annotation mode. When the shape annotation mode is disabled, zooming, panning, and scrolling will be enabled again.

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Setting the annotation mode to None
pdfViewer.AnnotationMode = AnnotationMode.None;

{% endhighlight %}
{% endtabs %}

### Detecting the inclusion of shape annotations

The [`ShapeAnnotationAdded`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.SfPdfViewer~ShapeAnnotationAdded_EV.html) event will be raised when a shape annotation is added to the PDF. The properties of the added shape annotation can be retrieved from the [`ShapeAnnotationAddedEventArgs`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationAddedEventArgs.html) parameter of the event handler. 

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Wire up the ShapeAnnotionAdded Event
pdfViewer.ShapeAnnotationAdded += PdfViewer_ShapeAnnotationAdded;

{% endhighlight %}
{% endtabs %}

The following code shows how to retrieve the properties of the added shape annotation.

{% tabs %}
{% highlight c# %}

private void PdfViewer_ShapeAnnotationAdded(object sender, ShapeAnnotationAddedEventArgs args)
        {
            //Get the added shape annotation type
            AnnotationMode annotationMode = args.AnnotationType;

            //Get the bounds of the added shape annotation
            CGRect bounds = args.Bounds;

            //Get the page number in which the added shape annotation is present
            int pageNumber = args.PageNumber;

            //Get the data points of the added shape annotation
            List<CGPoint> dataPoints = args.DataPoints;

            //Get the opacity value of the added shape annotation
            nfloat opacity = args.Opacity;            

            //Get the position of the added shape annotation within the page
            CGPoint position = args.Position;

            //Get the stroke color of the added shape annotation 
            UIColor strokeColor = args.StrokeColor;

            //Get the thickness of the added shape annotation
            float thickness = args.Thickness;

        }

{% endhighlight %}
{% endtabs %}

## Detecting tap on shape annotations

Tapping a shape annotation selects it or deselects it if it is already selected. The [`ShapeAnnotationTapped`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.SfPdfViewer~ShapeAnnotationTapped_EV.html) event is raised when a shape annotation is tapped. The properties of the tapped shape annotation can be retrieved from the [`ShapeAnnotationTappedEventArgs`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationTappedEventArgs_members.html) parameter of the event handler. 

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Wire up the ShapeAnnotionTapped event
pdfViewer.ShapeAnnotationTapped += PdfViewer_ShapeAnnotationTapped;

{% endhighlight %}
{% endtabs %}

The following code shows how to retrieve the properties of the tapped shape annotation.

{% tabs %}
{% highlight c# %}

private void PdfViewer_ShapeAnnotationTapped(object sender, ShapeAnnotationTappedEventArgs args)
        {
            //Get the tapped shape annotation type
            AnnotationMode annotationMode = args.AnnotationType;

            //Get the bounds of the tapped shape annotation
            CGRect bounds = args.Bounds;

            //Get the page number in which the tapped shape annotation is present
            int pageNumber = args.PageNumber;

            //Get the data points of the tapped shape annotation
            List<CGPoint> dataPoints = args.DataPoints;

            //Get the opacity value of the tapped shape annotation
            nfloat opacity = args.Opacity;

            //Get the position of the tapped shape annotation within the page
            CGPoint position = args.Position;

            //Get the stroke color of the tapped shape annotation 
            UIColor strokeColor = args.StrokeColor;

            //Get the thickness of the tapped shape annotation
            float thickness = args.Thickness;
        }

{% endhighlight %}
{% endtabs %}


## Selecting Shape annotations

You can select a shape annotation by tapping it. When a shape annotation is selected, the [`ShapeAnnotationSelected`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.SfPdfViewer~ShapeAnnotationSelected_EV.html) event will be raised. The properties of the selected shape annotation can be retrieved from the [`ShapeAnnotationSelectedEventArgs`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSelectedEventArgs.html) parameter of the event handler.  

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer();

//Wire up the ShapeAnnotionSelected event
pdfViewer.ShapeAnnotationSelected += PdfViewer_ShapeAnnotationSelected;

{% endhighlight %}
{% endtabs %}

The following code shows how to retrieve the properties of the selected shape annotation.

{% tabs %}
{% highlight c# %}

private void PdfViewer_ShapeAnnotationSelected(object sender, ShapeAnnotationSelectedEventArgs args)
{
//Get the selected shape annotation type
AnnotationMode annotationMode = args.AnnotationType;

//Get the bounds of the selected shape annotation
CGRect bounds = args.Bounds;

//Get the page number in which the selected shape annotation is present
int pageNumber = args.PageNumber;

//Get the list of other annotations that overlap the selected annotation
System.Collections.Generic.List<IAnnotation> overlappedAnnotation = args.OverlappedAnnotations;
}

{% endhighlight %}
{% endtabs %}

## Deselecting Shape annotations

You can deselect a selected shape annotation by tapping on it or somewhere else on the PDF page. Deselection can be detected using the [`ShapeAnnotationDeselected`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.SfPdfViewer~ShapeAnnotationDeselected_EV.html) event. The properties of the deselected shape annotation can be retrieved from the [`ShapeAnnotationDeselectedEventArgs`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationDeselectedEventArgs.html) parameter of the event handler. 

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Wire up the ShapeAnnotionDeselected event
pdfViewer.ShapeAnnotationDeselected = PdfViewer_ShapeAnnotationDeselected;

{% endhighlight %}
{% endtabs %}

The following code shows how to retrieve the properties of the deselected shape annotation.

{% tabs %}
{% highlight c# %}

private void PdfViewer_ShapeAnnotationDeselected(object sender, ShapeAnnotationDeselectedEventArgs args) 
{ 
//Get the deselected shape annotation type
AnnotationMode annotationType = args.AnnotationType; 

//Retrieves the bounds of the deselected shape annotation. 
CGRect bounds = args.Bounds; 

//Retrieves the page number where the deselected shape annotation resides. 
int page = args.PageNumber; 
}

{% endhighlight %}
{% endtabs %}

##Moving or resizing the selected shape annotation

To move or resize a shape annotation it should first be selected. After the appearance of the selector, tapping and dragging anywhere inside the selector will move the shape annotation. Tapping on the bubbles around the selector and dragging would resize the shape annotation. 

### Detecting the move or resize of a shape Annotation

The [`AnnotationMovedOrResized`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.SfPdfViewer~AnnotationMovedOrResized_EV.html) event will be raised when you move or resize the selected annotation. The properties of the moved or re-sized shape annotation can be retrieved from the [`AnnotationMovedOrResizedEventArgs`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.AnnotationMovedOrResizedEventArgs.html) parameter of the event handler. 

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Wire up the AnnotationMovedOrResized event
pdfViewer.AnnotationMovedOrResized = PdfViewer_AnnotationMovedOrResized;

{% endhighlight %}
{% endtabs %}

The following code shows how to retrieve the properties of the moved or re-sized shape annotation.

{% tabs %}
{% highlight c# %}

private void PdfViewer_AnnotationMovedOrResized(object sender, AnnotationMovedOrResizedEventArgs args)
        {
            //Determine whether the moved or resized annotation is a shape annotation or some other annotation. 
            if (sender as ShapeAnnotation != null)
            {
                //The annotation is a shape annotation 
            }
            else
            {
                //The annotation is not a shape annotation
            }

            //Retrieve the old bounds of the shape annotation 
            CGRect oldBounds = args.OldBounds;

            //Retrieve the new bounds of the shape annotation 
            CGRect newBounds = args.NewBounds;

            //Get the page number in which the shape annotation is moved or re-sized            
            int pageNumber = args.PageNumber;

            //Get the opacity value of the shape annotation            
            nfloat opacity = args.Opacity;

            //Get the color of the shape annotation
            UIColor color = args.Color;

            //Get the thickness of the shape annotation
            float thickness = args.Thickness;
        }

{% endhighlight %}
{% endtabs %}

## Deleting the shape annotations

The PDF Viewer allows you to remove a selected annotation or all the annotations in the PDF document.

### Removing a selected annotation

The following code sample shows how to remove the selected shape annotation from the PDF document.

{% tabs %}
{% highlight c# %}

ShapeAnnotation shapeAnnotation;
private void PdfViewer_ShapeAnnotationSelected(object sender, ShapeAnnotationSelectedEventArgs args)
        {
            //Cast the sender object as shape annotation. 
            shapeAnnotation = sender as ShapeAnnotation;
        }

private void deleteShapeAnnotationButton_Clicked(object sender, EventArgs e)
        {
            //Delete the shape annotation 
            pdfViewer.RemoveAnnotation(shapeAnnotation);
        }
{% endhighlight %}
{% endtabs %}

## Detecting the removal of a shape Annotation

The [`ShapeAnnotationRemoved`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.SfPdfViewer~ShapeAnnotationRemoved_EV.html) event will be raised when a shape annotation is removed from the PDF. The properties of the removed shape annotation can be retrieved from the [`ShapeAnnotationRemovedEventArgs`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationRemovedEventArgs.html) parameter of the event handler. 

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Wire up the ShapeAnnotionRemoved Event
pdfViewer.ShapeAnnotationRemoved = PdfViewer_ShapeAnnotationRemoved;

{% endhighlight %}
{% endtabs %}

The following code shows how to retrieve the properties of the removed shape annotation.

{% tabs %}
{% highlight c# %}

private void PdfViewerControl_ShapeAnnotationRemoved(object sender, ShapeAnnotationRemovedEventArgs args)
        {
            //Get the removed shape annotation type
            AnnotationMode annotationMode = args.AnnotationType;

            //Get the bounds of the removed shape annotation
            CGRect bounds = args.Bounds;

            //Get the data points of the removed shape annotation
            List<CGPoint> dataPoints = args.DataPoints;

            //Get the page number in which the removed shape annotation was present
            int pageNumber = args.PageNumber; 
        }

{% endhighlight %}
{% endtabs %}

## Customizing the appearance of shape annotations

You can customize the default values of [`stroke color`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~StrokeColor.html), [`opacity`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~Opacity.html), [`maximum height`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~MaximumHeight.html), [`minimum height`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~MinimumHeight.html), [`maximum width`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~MaximumWidth.html), [`minimum width`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~MinimumWidth.html), [`display text`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~Text.html), [`text background color`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~TextBackgroundColor.html), [`text color`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~TextColor.html), [`text opacity`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~TextOpacity.html), [`text size`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~TextSize.html), [`interaction (locked)`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.AnnotationSettings~IsLocked.html), [`thickness`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~Thickness.html), and [`fill color`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~FillColor.html) of the shape annotations that are to be added. 

N>This will not affect the shape annotations that were already added. The following properties are common to all the shape annotations. In all code samples, the Rectangle shape annotation is used for illustration purposes. 

### Setting the default stroke color

You can set the default stroke color for the shape annotations by using the [`StrokeColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~StrokeColor.html) property. Refer to the following code example

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Setting the stroke color for rectangle shape annotation
pdfViewer.AnnotationSettings.Rectangle.Settings.StrokeColor = UIColor.Red;

{% endhighlight %}
{% endtabs %}

### Setting the default opacity

You can set the default opacity for the shape annotations by using the [`Opacity`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~Opacity.html) property. The opacity value ranges from 0 to 1. Refer to the following code example.

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Setting the opacity for rectangle shape annotation
pdfViewer.AnnotationSettings.Rectangle.Settings.Opacity = 0.5f;

{% endhighlight %}
{% endtabs %}

### Setting the default fill color

You can set the default fill color for the shape annotations by using the [`FillColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~FillColor.html) property. Refer to the following code example.

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Setting the fill color for rectangle shape annotation
pdfViewer.AnnotationSettings.Rectangle.Settings.FillColor = UIColor.Blue;

{% endhighlight %}
{% endtabs %}

### Setting the default thickness

You can set the thickness for the shape annotations by using the [`Thickness`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~Thickness.html) property. Refer to the following code example.

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Setting thickness for the rectangle shape annotation
pdfViewer.AnnotationSettings.Rectangle.Settings.Thickness = 5;

{% endhighlight %}
{% endtabs %}

### Setting the default text

You can set the text for the shape annotations by using the [`Text`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~Text.html) property. Refer to the following code example.

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Setting the text for rectangle shape annotation
pdfViewer.AnnotationSettings.Rectangle.Settings.Text = “Area”;

{% endhighlight %}
{% endtabs %}

### Setting the default text background color

You can set the background color for the text assigned to the shape annotations by using the [`TextBackgroundColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~TextBackgroundColor.html) property. Refer to the following code example.

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Setting the text background color for rectangle shape annotation
pdfViewer.AnnotationSettings.Rectangle.Settings.TextBackgroundColor = UIColor.Black;

{% endhighlight %}
{% endtabs %}

### Setting the default text color

You can set the color for the text assigned to the shape annotations by using the [`TextColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~TextColor.html) property. Refer to the following code example.

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Setting the text color for rectangle shape annotation
pdfViewer.AnnotationSettings.Rectangle.Settings.TextColor = UIColor.Black;

{% endhighlight %}
{% endtabs %}

### Setting the default text opacity

You can set the opacity for the text assigned to the shape annotations by using the [`TextOpacity`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~TextOpacity.html) property. Refer to the following code example.

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Setting the text opacity for rectangle shape annotation
pdfViewer.AnnotationSettings.Rectangle.Settings.TextOpacity = 0.5f;

{% endhighlight %}
{% endtabs %}

### Setting the default text size

You can set the size for the text assigned to the shape annotations by using the [`TextSize`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~TextSize.html) property. Refer to the following code example.

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Setting the text opacity for rectangle shape annotation
pdfViewer.AnnotationSettings.Rectangle.Settings.TextOpacity = 0.5f;

{% endhighlight %}
{% endtabs %}

### Setting the default minimum height

You can set the minimum height for the shape annotations by using the [`MinimumHeight`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~MinimumHeight.html) property. Refer to the following code example.

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Setting the minimum height for rectangle shape annotation
pdfViewer.AnnotationSettings.Rectangle.Settings.MinimumHeight = 20;

{% endhighlight %}
{% endtabs %}

### Setting the default minimum width

You can set the minimum width for the shape annotations by using the [`MinimumWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~MinimumWidth.html) property. Refer to the following code example. 

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Setting the minimum width for rectangle shape annotation
pdfViewer.AnnotationSettings.Rectangle.Settings.MinimumWidth = 20;

{% endhighlight %}
{% endtabs %}

### Setting the default maximum height

You can set the maximum height for the shape annotations by using the [`MaximumHeight`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~MaximumHeight.html) property. Refer to the following code example. 

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Setting the maximum height for rectangle shape annotation
pdfViewer.AnnotationSettings.Rectangle.Settings.MaximumHeight = 60;

{% endhighlight %}
{% endtabs %}

### Setting the default maximum width

You can set the maximum width for the shape annotations by using the [`MaximumWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSettings~MaximumWidth.html) property. Refer to the following code example. 

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Setting the minimum width for rectangle shape annotation
pdfViewer.AnnotationSettings.Rectangle.Settings.MinimumWidth = 20;

{% endhighlight %}
{% endtabs %}

### Changing the properties of a selected shape annotation

You can change the properties of the selected annotation by casting the sender parameter of the [`ShapeAnnotationSelected`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.SfPdfViewer~ShapeAnnotationSelected_EV.html) event handler to ShapeAnnotation and modifying its properties. The following code shows how to change the properties.

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer(); 

//Wire up the ShapeAnnotionRemoved Event
pdfViewer.ShapeAnnotationSelected = PdfViewer_ShapeAnnotationSelected;

 private void PdfViewer_ShapeAnnotationSelected(object sender, ShapeAnnotationSelectedEventArgs args)
        {
            //Get the type of the annotation. Here, it is a rectangle.
            AnnotationMode annotationMode = args.AnnotationType;

            //Cast the sender object as shape annotation. 
            ShapeAnnotation selectedShapeAnnotation = sender as ShapeAnnotation;

            //Set the stroke color of the selected annotation using the shape annotation settings. 
            selectedShapeAnnotation.Settings.StrokeColor = UIColor.Blue;

            //Set the opacity of the selected annotation using the shape annotation settings. 
            selectedShapeAnnotation.Settings.Opacity = 0.3f;

            //Set the thickness of the selected annotation using the shape annotation settings. 
            selectedShapeAnnotation.Settings.Thickness = 3;

            //Set the fill color of the selected annotation using the shape annotation settings. 
            selectedShapeAnnotation.Settings.FillColor = UIColor.Red;

            //Set the minimum height for the selected annotation using the shape annotation settings.
            selectedShapeAnnotation.Settings.MinimumHeight = 20;

            //Set the minimum width for the selected annotation using the shape annotation settings.
            selectedShapeAnnotation.Settings.MinimumWidth = 20;

            //Set the maximum width for the selected annotation using the shape annotation settings.
            selectedShapeAnnotation.Settings.MaximumWidth = 80;

            //Set the maximum height for the selected annotation using the shape annotation settings.
            selectedShapeAnnotation.Settings.MaximumHeight = 80;

            //Set the text for the selected annotation using the shape annotation settings.
            selectedShapeAnnotation.Settings.Text = "Rectangle";

            //Set the text background color for the selected annotation using the shape annotation settings.
            selectedShapeAnnotation.Settings.TextBackgroundColor = UIColor.Black;

            //Set the text color for the selected annotation using the shape annotation settings.
            selectedShapeAnnotation.Settings.TextColor = UIColor.Black;

            //Set the text opacity for the selected annotation using the shape annotation settings.
            selectedShapeAnnotation.Settings.TextOpacity = 0.5f;

            //Set the text size for the selected annotation using the shape annotation settings.
            selectedShapeAnnotation.Settings.TextSize = 12;
        }

{% endhighlight %}
{% endtabs %}

## How to enable or disable the shape annotation interaction

The interaction operation can be enabled or disabled for the shape annotation alone by setting the [`SfPdfViewer.AnnotationSettings.Rectangle.IsLocked`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.RectangleAnnotation~IsLocked.html) API to false or true respectively.

For example, the following code disables the interaction operations for all shape annotations in the PDF. But the other annotation types can be selected, moved, resized, or removed.

{% tabs %}
{% highlight c# %}

//Disable the arrow annotation interaction 
pdfViewerControl.AnnotationSettings.Arrow.IsLocked = true; 

//Disable the line annotation interaction 
pdfViewerControl.AnnotationSettings.Line.IsLocked = true; 

//Disable the rectangle annotation interaction 
pdfViewerControl.AnnotationSettings.Rectangle.IsLocked = true;
 
//Disable the circle annotation interaction 
pdfViewerControl.AnnotationSettings.Circle.IsLocked = true;

//Disable the polygon annotation interaction 
pdfViewerControl.AnnotationSettings.Polygon.IsLocked = true;

{% endhighlight %}
{% endtabs %}

The interaction with shape annotation types will be allowed only if, the [`SfPdfViewer.AnnotationSettings.IsLocked`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.AnnotationSettings~IsLocked.html) API is set to false. The following code does not allow the interactions with shape annotations, although the [`SfPdfViewer.AnnotationSettings.Rectangle.IsLocked`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.RectangleAnnotation~IsLocked.html) property of the shape annotation is set to false.

{% tabs %}
{% highlight c# %}

//Disables the shape annotation interaction, though its 'IsLocked' property is set to ‘false’ 
pdfViewerControl.AnnotationSettings.IsLocked = true; 

pdfViewerControl.AnnotationSettings.Arrow.IsLocked = false;

pdfViewerControl.AnnotationSettings.Line.IsLocked = false; 

pdfViewerControl.AnnotationSettings.Rectangle.IsLocked = false; 

pdfViewerControl.AnnotationSettings.Circle.IsLocked = false;

pdfViewerControl.AnnotationSettings.Polygon.IsLocked = false;

{% endhighlight %}
{% endtabs %}

## How to get the list of Annotations that overlaps the selected shape Annotation

You can retrieve the list of Annotations that overlaps the selected shape Annotation from the [`ShapeAnnotationSelectedEventArgs`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.ShapeAnnotationSelectedEventArgs.html) parameter of the [`ShapeAnnotationSelected`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfPdfViewer.iOS~Syncfusion.SfPdfViewer.iOS.SfPdfViewer~ShapeAnnotationSelected_EV.html) event handler.

{% tabs %}
{% highlight c# %}

//Initialize the SfPdfViewer
SfPdfViewer pdfViewer = new SfPdfViewer();

//Wire up the ShapeAnnotionSelected event
pdfViewer.ShapeAnnotationSelected += PdfViewer_ShapeAnnotationSelected;

private void PdfViewer_ShapeAnnotationSelected(object sender, ShapeAnnotationSelectedEventArgs args)
        {
            // Get the list of Annotations that overlap the selected Annotation
            System.Collections.Generic.List<IAnnotation> overlappedAnnotation = args.OverlappedAnnotations;
        }

{% endhighlight %}
{% endtabs %}
