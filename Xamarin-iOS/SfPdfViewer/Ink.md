---
layout: post
title:  Add freehand scribble in PDF using Syncfusion PDF Viewer iOS
description: PDF viewer Xamarin.iOS allows user to add ink annotation and provides options to edit or remove an existing ink annotation in the PDF file.
platform: Xamarin.iOS
control: SfPdfViewer
documentation: ug
---

# Working with ink annotation

PDF viewer allows you to include ink annotation in the PDF document and provides options to edit or remove the existing ink annotation in the PDF document.

## Inclusion of ink annotation

This section describes how to include ink annotation in PDF viewer control Xamarin.iOS.

### Enabling ink annotation mode

Set the `AnnotationMode` property of the PDF viewer object to ink to enable the ink annotation. By setting this, zooming and scrolling will be disabled and touch interactions will be converted into inks on the PDF pages. Refer to the following code. 

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.AnnotationMode = AnnotationMode.Ink;

{% endhighlight %}
{% endtabs %}

Use the following code to reset the annotation mode to none. 

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.AnnotationMode = AnnotationMode.None;

{% endhighlight %}
{% endtabs %}

### Adding ink annotation

Steps involved in adding ink annotation to the PDF document:

1.	Switch to ink annotation mode.
2.	Add inks to the pages of the PDF document, this will be recorded as a session.
3.	You can perform undo and redo operations for every stroke made in the session.
4.	You can also choose the color and thickness of the ink, here color and thickness are restricted to the complete ink and not individual strokes.
5.	After adding ink annotation, you can either accept or discard the changes.

### How to accept and include the ink annotation on to the PDF viewer?

The following code can be used to accept and include the drawn ink annotation to the PDF viewer control.

{% tabs %}
{% highlight c# %}

pdfViewer.EndInkSession(true);

{% endhighlight %}
{% endtabs %}

### How to ignore/discard drawn ink annotation from the PDF viewer before inclusion?

The following code can be used to ignore or discard the drawn ink annotation to the PDF viewer control.

{% tabs %}
{% highlight c# %}

pdfViewer.EndInkSession(false);

{% endhighlight %}
{% endtabs %}

## How to identify whether the ink annotation is included?

You can identify whether the drawn ink annotation has been added to the PDF viewer control or not by using the `InkAdded` event. This event will be raised once the annotation is added. 

{% tabs %}
{% highlight c# %}
SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.InkAdded`+= pdfViewer_InkAdded;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

private void pdfViewer_InkAdded(object sender, InkAddedEventArgs args)
{
    //Retrieves the bounds of the deselected annotation.
    Rectangle bounds = args.Bounds;

    //Retrieves the page number where the deselected annotation resides.
    int pageNumber = args.PageNumber;

    //Retrieves the color of the deselected annotation.
    Color color = args.Color;

    //Retrieves the thickness of the deselected annotation.
    float thickness = args.Thickness;

    //Retrieves the opacity of the deselected annotation.
    float opacity = args.Opacity;

}

{% endhighlight %}
{% endtabs %}

## How to perform undo and redo operation during inking session?

You can perform undo and redo operations on the drawn ink annotations during the pre-conformance session. 

The following code can be used to perform undo operation on the ink annotations drawn over the PDF viewer control.

{% tabs %}
{% highlight c# %}

pdfViewer.UndoInk();

{% endhighlight %}
{% endtabs %}

You can identify the undo operation in this session using the following event. 

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.CanUndoInkModified += PdfViewer_CanUndoInkModified;

{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}

private void PdfViewer_CanUndoInkModified(object sender, CanUndoInkModifiedEventArgs args)
{
    bool canUndoInk = args.CanUndoInk;
}

{% endhighlight %}
{% endtabs %}

The following code can be used to perform redo operation on the ink annotations drawn over the PDF viewer control.

{% tabs %}
{% highlight c# %}

pdfViewer.RedoInk();

{% endhighlight %}
{% endtabs %}

You can identify the redo operation in this session using the following event. 

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.CanRedoInkModified += PdfViewer_CanRedoInkModified;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

private void PdfViewer_CanRedoInkModified(object sender, CanRedoInkModifiedEventArgs args)
{
   bool CanRedoInk = args.CanRedoInk;
}

{% endhighlight %}
{% endtabs %}

## Deleting ink annotation

The PDF viewer can remove a selected annotation or all the annotations in the PDF document. 

### Removing a selected annotation.

The following code snippet illustrates removing a selected annotation from the PDF document.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.InkSelected	+= PdfViewer_InkSelected;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}


private void PdfViewer_InkSelected(object sender, InkSelectedEventArgs args)
{
    //Casts the sender object as Ink annotation.
    InkAnnotation selectedInkAnnotation = sender as InkAnnotation;

    //Removes the selected annotation from the PDF viewer.
    pdfViewer.RemoveAnnotation(selectedInkAnnotation);
}

{% endhighlight %}
{% endtabs %}

### How to identify the removal of ink annotation?

You can identify removal of ink annotation using the `InkRemoved` event, which is available in the PDF viewer control. This event will be raised when you remove the ink annotation from the PDF viewer control.

The following C# code shows how to acquire bounds, page number, color, thickness, and opacity of the removed ink annotation.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.InkRemoved+=PdfViewer_InkRemoved;

{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}

private void PdfViewer_InkRemoved(object sender, InkRemovedEventArgs args)
{

    //Retrieves the bounds of the deselected annotation.
    Rectangle bounds = args.Bounds;

    //Retrieves the page number where the deselected annotation resides.
    int pageNumber = args.PageNumber;

    //Retrieves the color of the deselected annotation.
    Color color = args.Color;

    //Retrieves the thickness of the deselected annotation.
    float thickness = args.Thickness;

    //Retrieves the opacity of the deselected annotation.
    float opacity = args.Opacity;
}

{% endhighlight %}
{% endtabs %}

## Working with ink annotation settings

You can customize the color, opacity, and thickness of the ink annotation.

### Changing the color

You can set the color of the ink annotation by using the `AnnotationSettings.Ink.Color` property. Refer to the following code sample. 
 
{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();

pdfViewer.AnnotationMode = AnnotationMode.Ink;

pdfViewer.AnnotationSettings.Ink.Color = Color.Red;

{% endhighlight %}
{% endtabs %}


### Changing the opacity

You can set the opacity of the ink annotation by using the `AnnotationSettings.Ink.Opacity` property. Opacity value ranges from 0 to 1. Refer to the following code example. 

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();

pdfViewer.AnnotationMode = AnnotationMode.Ink;

pdfViewer.AnnotationSettings.Ink.Opacity = 0.5f; 

{% endhighlight %}
{% endtabs %}

### Changing the thickness

You can set the thickness of the ink annotation by using the `AnnotationSettings.Ink.Thickness` property. Refer to the following code example. 

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();

pdfViewer.AnnotationMode = AnnotationMode.Ink;

pdfViewer.AnnotationSettings.Ink.Thickness = 5;

{% endhighlight %}
{% endtabs %}

## How to select the ink annotation?

You can select the ink annotation by tapping the annotation. 

### How to change the properties of ink annotation after selection?

You can select and change the properties of the ink annotation using the `InkSelected` event. This event will be raised when you select the ink annotation. This is illustrated in the following code sample. 


{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.InkSelected += PdfViewer_InkSelected;

{% endhighlight %}
{% endtabs %}

You can change the properties of the selected annotation using the `InkSelectedEventArgs` object.  The following code shows how to change the properties of the selected annotation in the `InkSelectedEventHandler`.

{% tabs %}
{% highlight c# %}

private void PdfViewer_InkSelected(object sender, InkSelectedEventArgs args)
{
    //Casts the sender object as Ink annotation.
    InkAnnotation selectedInkAnnotation = sender as InkAnnotation;

    //Sets the color of the selected annotation using ink annotation settings.
    selectedInkAnnotation.Settings.Color = Color.Blue;

    //Sets the opacity of the selected annotation using ink annotation settings.
    selectedInkAnnotation.Settings.Opacity = 0.3f;

    //Sets the thickness of the selected annotation using ink annotation settings.
    selectedInkAnnotation.Settings.Thickness = 3;
}

{% endhighlight %}
{% endtabs %}

You can identify whether the ink annotation is tapped or not using the`InkTapped` event. This event will be triggered if you tap the ink annotation whether to select or deselect the annotation. 

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.InkTapped += PdfViewer_InkTapped;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

private void PdfViewer_InkTapped(object sender, InkTappedEventArgs args)
{
    //Retrieves the bounds of the deselected annotation.
    Rectangle bounds = args.Bounds;

    //Retrieves the page number where the deselected annotation resides.
    int pageNumber = args.PageNumber;

    //Retrieves the color of the deselected annotation.
    Color color = args.Color;

    //Retrieves the thickness of the deselected annotation.
    float thickness = args.Thickness;

    //Retrieves the opacity of the deselected annotation.
    float opacity = args.Opacity;
}

{% endhighlight %}
{% endtabs %}

## How to deselect the ink annotation?

You can deselect the ink annotation by tapping on the selected annotation or on the PDF page. Deselection can be identified using the `InkDeselected` event.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.InkDeselected += PdfViewer_InkDeselected;

{% endhighlight %}
{% endtabs %}

The following code shows how to identify the deselected annotation from the raised event.

{% tabs %}
{% highlight c# %}

private void PdfViewer_InkDeselected(object sender, InkDeselectedEventArgs args)
{ 
   //Retrieves the bounds of the deselected annotation.
   Rectangle bounds = args.Bounds;

   //Retrieves the page number where the deselected annotation resides.
   int page = args.PageNumber;

   //Retrieves the color of the deselected annotation.
   Color color = args.Color;

   //Retrieves the thickness of the deselected annotation.
   float thickness = args.Thickness;

   //Retrieves the opacity of the deselected annotation.
   float opacity = args.Opacity;
 
 }

{% endhighlight %}
{% endtabs %}

## How to move or resize the selected ink annotation?

Select and drag the annotation to move or resize the ink annotation. 

### How to identify whether the ink annotation is moved or resized?

The event `AnnotationMovedOrResized` will be raised when you move or resize the selected annotation.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.AnnotationMovedOrResized += PdfViewer_AnnotationMovedOrResized;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

private void PdfViewer_AnnotationMovedOrResized(object sender, AnnotationMovedOrResizedEventArgs args) 
{
     //Retrieves the old bounds of the annotation
     Rectangle oldBounds = args.OldBounds;

     //Retrieves the new bounds of the annotation
     Rectangle newBounds = args.NewBounds;
}

{% endhighlight %}
{% endtabs %}

## How to draw the ink annotation using a stylus and scroll or zoom PDF page with the touch

The ink annotation operation can be customized so that the ink strokes can be added only using a stylus by setting the `InkAnnotationSettings.TouchMode` API to `TouchMode.Stylus`. When the `TouchMode` is set to stylus, the PDF can be zoomed and scrolled using a finger. The default value of the `TouchMode` property is `TouchMode.Direct` in which all touch interactions will be considered as ink operations. So in the `TouchMode.Direct` mode, the page cannot be scrolled or zoomed when the ink annotation mode is on.

{% tabs %}
{% highlight c# %}

//TouchMode is set to Stylus
pdfViewerControl.AnnotationSettings.Ink.TouchMode = TouchMode.Stylus;

{% endhighlight %}
{% endtabs %}
