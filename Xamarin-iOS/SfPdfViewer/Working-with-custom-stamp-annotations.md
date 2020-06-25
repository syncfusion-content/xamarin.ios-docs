---
layout: post
title: Custom stamp annotations | PDF Viewer | Xamarin.iOS | Syncfusion
description: The custom stamp annotation allows the users to include any form of Xamarin.iOS widget like Button, Entry, Label, and Image anywhere in the PDF document
platform: Xamarin.iOS
control: SfPdfViewer
documentation: ug
---

# Working with custom stamp annotations

PDF Viewer allows you to include any form of Xamarin.iOS UIView that is Button, Entry, Label, Image and more anywhere in the pages of the PDF Viewer as custom stamp annotation. You can perform operations like add, move, resize, and delete the custom stamp annotations. Also, you can save and load the existing custom stamp annotation that is associated with the PDF document

## Add a custom stamp

The custom stamps can be added using any of the following APIs:

{% tabs %}
{% highlight c# %}

//Add custom stamp/view to the specified page
pdfViewer.AddStamp(View view, int pageNumber)

//Add custom stamp/view to the specified page and position as Point object
pdfViewer.AddStamp(View view, int pageNumber, Point position)

//Add custom stamp/view to the specified page and position as Rectangle object
pdfViewer.AddStamp(View view, int pageNumber, Rectangle bounds)

{% endhighlight %}
{% endtabs %}

A typical example of the custom stamp in the real world includes, adding an image as custom stamp. PDF Viewer provides option to add any user defined signature or seal image as custom stamp to the PDF document. The following code sample explains the same.

{% tabs %}
{% highlight c# %}

private void Button_Clicked(object sender, EventArgs e)
{
    //Set image source
    Image image = new Image();
    image.Source = ImageSource.FromResource("Sample.Assets.Logo.png", typeof(App).GetTypeInfo().Assembly);
    image.WidthRequest = 200;
    image.HeightRequest = 100;

    //Add image as custom stamp to the first page
    pdfViewer.AddStamp(image, 1);
}

{% endhighlight %}
{% endtabs %}

The `StampAnnotationAdded` event will be raised when custom stamp annotations are added in the PDF document.

{% tabs %}
{% highlight c# %}

pdfViewer.StampAnnotationAdded += PdfViewer_StampAnnotationAdded;

{% endhighlight %}
{% endtabs %}

## Select a custom stamp

You can select a custom stamp annotation by tapping on it and this action is followed by the appearance of the selector around the custom stamp annotation. The `StampAnnotationSelected` event will be raised when custom stamp annotations are selected in the PDF document.

{% tabs %}
{% highlight c# %}

pdfViewer.StampAnnotationSelected += PdfViewer_StampAnnotationSelected;

{% endhighlight %}
{% endtabs %}

The `StampAnnotationSelectedEventArgs` properties of the selected custom stamp annotation includes page number and bounds information. The following code sample explains this.

{% tabs %}
{% highlight c# %}

private void PdfViewer_StampAnnotationSelected(object sender, StampAnnotationSelectedEventArgs e)
{
    //Gets the page number of selected stamp annotation
    int pageNumber = e.PageNumber;

    //Gets the bounds of selected stamp annotation
    Rectangle bounds = e.Bounds;
}

{% endhighlight %}
{% endtabs %}

Also, tapping a custom stamp annotation selects it or deselects if it is already selected. Tapping a custom stamp annotation will raise the `StampAnnotationTapped` event.

{% tabs %}
{% highlight c# %}

pdfViewer.ShapeAnnotationTapped += PdfViewer_ShapeAnnotationTapped;

{% endhighlight %}
{% endtabs %}

## Deselect a custom stamp

You can deselect a selected custom stamp annotation by tapping on it or somewhere else on the PDF document. Deselection of a custom stamp annotation can be detected using the `StampAnnotationDeselected` event.

{% tabs %}
{% highlight c# %}

pdfViewer.StampAnnotationDeselected += PdfViewer_StampAnnotationDeselected;

{% endhighlight %}
{% endtabs %}

## Move or resize a custom stamp

Select the custom stamp annotation to move or resize it. After the selector appears around the custom stamp annotation, drag it to move to a new location by tapping anywhere inside the selector. Similarly, drag the selector corner handle(s) to resize the selected custom stamp annotation. The `StampAnnotationMovedOrResized` event will be raised when you move or resize the selected annotation.

{% tabs %}
{% highlight c# %}

pdfViewer.StampAnnotationMovedOrResized += PdfViewer_StampAnnotationMovedOrResized;

{% endhighlight %}
{% endtabs %}

The `StampAnnotationMovedOrResizedEventArgs` properties of the moved or resized custom stamp annotation includes page number, old bounds, and new bounds information. The following code sample explains this.

{% tabs %}
{% highlight c# %}

private void PdfViewer_StampAnnotationMovedOrResized(object sender, StampAnnotationMovedOrResizedEventArgs e)
{
    //Get the page number of selected stamp annotation
    int pageNumber = e.PageNumber;

    //Get the old bounds of selected stamp annotation
    Rectangle oldBounds = e.OldBounds;

    //Get the new bounds of selected stamp annotation
    Rectangle newBounds = e.NewBounds;
}

{% endhighlight %}
{% endtabs %}

## Delete a custom stamp

When you select the custom stamp annotation, delete icon will appear on the bottom toolbar. By clicking that delete icon, the selected custom stamp annotation can be removed. The `StampAnnotationRemoved` event will be raised when a custom stamp annotation is removed from the PDF.

{% tabs %}
{% highlight c# %}

pdfViewer.StampAnnotationRemoved += PdfViewer_StampAnnotationRemoved;

{% endhighlight %}
{% endtabs %}