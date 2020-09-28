---
layout: post
title:  Freetext annotations in Xamarin.iOS PDF Viewer | Syncfusion
description: Learn about free text annotations support in Syncfusion Xamarin.iOS Pdf Viewer (SfPdfViewer) control and more details.
platform: Xamarin.iOS
control: SfPdfViewer
documentation: ug
---

# Working with free text annotations

PDF viewer allows you to include free text annotations in a PDF document and provides options to modify or remove the existing ones.

## Adding free text annotations

### Enabling free text annotation mode

Set the `AnnotationMode` property of the PDF viewer to `FreeText`. After setting the annotation mode, tap any PDF page and a popup will appear. Zooming, panning and scrolling will be disabled. Type the text in the popup and click &#34;OK&#34; to add the typed text to the page. Zooming, panning, and scrolling will be enabled again if the free text annotation is added. 

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.AnnotationMode = AnnotationMode.FreeText;

{% endhighlight %}
{% endtabs %}

### Disabling free text annotation mode

Setting the annotation mode to `None` disables the free text mode.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.AnnotationMode = AnnotationMode.None;

{% endhighlight %}
{% endtabs %}

### Detecting the inclusion of free text annotations

The event `FreeTextAnnotationAdded` will be raised when a free text annotation is added to the PDF.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.FreeTextAnnotationAdded += PdfViewer_FreeTextAnnotationAdded;

{% endhighlight %}
{% endtabs %}

## Detecting tap on free text annotations

Tapping a free text annotation selects it or deselects if it is already selected. The event `FreeTextAnnotationTapped` is raised when a free text is tapped.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.FreeTextAnnotationTapped += PdfViewer_FreeTextAnnotationTapped;

{% endhighlight %}
{% endtabs %}

## Selecting free text annotations

You can select a free text annotation by tapping it. When a free text is selected, the `FreeTextAnnotationSelected` event will be raised.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.FreeTextAnnotationSelected += PdfViewer_FreeTextAnnotationSelected;

{% endhighlight %}
{% endtabs %}

When the event is raised, the properties of the selected free text can be obtained from the `args` parameter of the event handler.

{% tabs %}
{% highlight c# %} 

private void PdfViewer_FreeTextAnnotationSelected(object sender, FreeTextAnnotationSelectedEventArgs args)
{
	//Obtain the bounds of the annotation
	CGRect bounds = args.Bounds;

	//Obtain the text in the annotation
	string text = args.Text;

	//Obtain the size of the text in the annotation
	float textSize = args.TextSize;

	//Obtain the color of the text
	UIColor textColor = args.TextColor;

	//Obtain the page number in which the selected annotation is
	int pageNumber = args.PageNumber;
}

{% endhighlight %}
{% endtabs %}

## Deselecting free text annotations

You can deselect a selected free text annotation by tapping on it or somewhere else on the PDF page. Deselection can be detected using the `FreeTextAnnotationDeselected` event.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.FreeTextAnnotationDeselected += PdfViewer_FreeTextAnnotationDeselected;

{% endhighlight %}
{% endtabs %}

## Customizing the appearance of free text annotations

You can customize the default values of opacity, display text, text color, text size, maximum height, minimum height, maximum width, minimum width, interaction (locked), and free text dialog of the free text annotations that are to be added. This will not affect the free text annotations that were already added.

### Setting the default opacity

You can set the default opacity for the free text annotations by using the [`SfPdfViewer.AnnotationSettings.FreeText.Opacity`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS.FreeTextAnnotationSettings.html#Syncfusion_SfPdfViewer_iOS_FreeTextAnnotationSettings_Opacity) property. The opacity value ranges from 0 to 1. Refer to the following code example.
 
{% tabs %} 
{% highlight c# %}

//Setting the opacity for the free text annotation 
pdfViewer.AnnotationSettings.FreeText.Opacity = 0.5f;

{% endhighlight %}
{% endtabs %}

### Setting the default text

You can set the text for the free text annotations by using the [`SfPdfViewer.AnnotationSettings.FreeText.Text`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS.FreeTextAnnotationSettings.html#Syncfusion_SfPdfViewer_iOS_FreeTextAnnotationSettings_Text) property. Refer to the following code example.
 
{% tabs %} 
{% highlight c# %}

//Setting the text for the free text annotation
pdfViewer.AnnotationSettings.FreeText.Text = “Syncfusion”;

{% endhighlight %}
{% endtabs %}


### Setting the default text color

You can set the color for the text assigned to the free text annotations by using the [`SfPdfViewer.AnnotationSettings.FreeText.TextColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS.FreeTextAnnotationSettings.html#Syncfusion_SfPdfViewer_iOS_FreeTextAnnotationSettings_TextColor) property. Refer to the following code example.
 
{% tabs %} 
{% highlight c# %}

//Setting the text color for the free text annotation
pdfViewer.AnnotationSettings.FreeText.TextColor = UIColor.Black;

{% endhighlight %}
{% endtabs %}

### Setting the default text size

You can set the size for the text assigned to the free text annotations by using the [`SfPdfViewer.AnnotationSettings.FreeText.TextSize`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS.FreeTextAnnotationSettings.html#Syncfusion_SfPdfViewer_iOS_FreeTextAnnotationSettings_TextSize) property. Refer to the following code example.

{% tabs %}
{% highlight c# %}

//Setting the text size for the free text annotation
pdfViewer.AnnotationSettings.FreeText.TextSize = 2;

{% endhighlight %}
{% endtabs %}

### Setting the default minimum height

You can set the minimum height for the free text annotations by using the [`SfPdfViewer.AnnotationSettings.FreeText.MinimumHeight`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS.FreeTextAnnotationSettings.html#Syncfusion_SfPdfViewer_iOS_FreeTextAnnotationSettings_MinimumHeight) property. Refer to the following code example.

{% tabs %}
{% highlight c# %}

//Setting the minimum height for the free text annotation
pdfViewer.AnnotationSettings.FreeText.MinimumHeight = 20;

{% endhighlight %}
{% endtabs %}

### Setting the default minimum width

You can set the minimum width for the free text annotations by using the [`SfPdfViewer.AnnotationSettings.FreeText.MinimumWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS.FreeTextAnnotationSettings.html#Syncfusion_SfPdfViewer_iOS_FreeTextAnnotationSettings_MinimumWidth) property. Refer to the following code example.

{% tabs %}
{% highlight c# %}

//Setting the minimum width for the free text annotation
pdfViewer.AnnotationSettings.FreeText.MinimumWidth = 20;

{% endhighlight %}
{% endtabs %}

### Setting the default maximum height

You can set the maximum height for the free text annotations by using the [`SfPdfViewer.AnnotationSettings.FreeText.MaximumHeight`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS.FreeTextAnnotationSettings.html#Syncfusion_SfPdfViewer_iOS_FreeTextAnnotationSettings_MaximumHeight) property. Refer to the following code example.

{% tabs %}
{% highlight c# %}

//Setting the maximum height for the free text annotation
pdfViewer.AnnotationSettings.FreeText.MaximumHeight = 60;

{% endhighlight %}
{% endtabs %}

### Setting the default maximum width

You can set the maximum width for the free text annotations by using the [`SfPdfViewer.AnnotationSettings.FreeText.MaximumWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS.FreeTextAnnotationSettings.html#Syncfusion_SfPdfViewer_iOS_FreeTextAnnotationSettings_MaximumWidth) property. Refer to the following code example.

{% tabs %}
{% highlight c# %}

//Setting the maximum width for the free text annotation
pdfViewer.AnnotationSettings.FreeText.MaximumWidth = 60;

{% endhighlight %}
{% endtabs %}


### Changing the properties of a selected free text 

You can change the properties of the selected annotation by casting the `sender` parameter of the `FreeTextAnnotationSelected` event handler to `FreeTextAnnotation` and modifying its properties. The following code shows how to change the properties.

{% tabs %}
{% highlight c# %} 

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.FreeTextAnnotationSelected += PdfViewer_FreeTextAnnotationSelected;
changeFreeTextPropertiesButton.TouchUpInside += ChangeFreeTextPropertiesButton_TouchUpInside;
FreeTextAnnotation selectedFreeTextAnnotation;

private void PdfViewer_FreeTextAnnotationSelected(object sender, FreeTextAnnotationSelectedEventArgs args)
{
	//Cast the sender object to free text annotation
	selectedFreeTextAnnotation = sender as FreeTextAnnotation;
}

private void ChangeFreeTextPropertiesButton_TouchUpInside(object sender, EventArgs e)
{
	//Change the color of the text
    selectedFreeTextAnnotation.Settings.TextColor = UIColor.Purple;

    //Change the size of the text
    selectedFreeTextAnnotation.Settings.TextSize = 6;
}

{% endhighlight %}
{% endtabs %}

## Moving or resizing free text annotations

To move or resize the annotation, it should be selected. After the selector appears, tapping and dragging anywhere inside the selector will move the annotation. Tapping on the bubbles around the selector and dragging will resize the annotation.

### Detecting the move or resize of a free text

The event `FreeTextAnnotationMovedOrResized` will be raised when you move or resize the selected annotation.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.FreeTextAnnotationMovedOrResized += PdfViewer_FreeTextAnnotationMovedOrResized;

{% endhighlight %}
{% endtabs %}

The properties of the moved or resized free text can be obtained from the `args` parameter of the event handler.

{% tabs %}
{% highlight c# %}

private void PdfViewer_FreeTextAnnotationMovedOrResized(object sender, FreeTextAnnotationMovedOrResizedEventArgs args)
{
	//Retrieve the old bounds of the annotation
	CGRect oldBounds = args.OldBounds;

	//Retrieve the new bounds of the annotation
	CGRect newBounds = args.NewBounds;

	//Retrieve the current page number
	int pageNumber = args.PageNumber;
}
{% endhighlight %}
{% endtabs %}

## Deleting free text annotations

The PDF viewer can remove a selected annotation or all the annotations in the PDF document. 

### Removing a selected free text annotation.

The following code snippet illustrates removing a selected free text from the PDF document.
{% tabs %}
{% highlight c# %}

FreeTextAnnotation selectedFreeTextAnnotation;

private void PdfViewer_FreeTextAnnotationSelected(object sender, FreeTextAnnotationSelectedEventArgs args)
{
	//Cast the sender object to free text annotation.
	selectedFreeTextAnnotation = sender as FreeTextAnnotation;
}

private void deleteFreeTextAnnotationButton_Clicked(object sender, EventArgs e)
{
	//Delete the selected free text annotation
	pdfViewer.RemoveAnnotation(selectedFreeTextAnnotation);
}

{% endhighlight %}
{% endtabs %}

### Removing all annotations

The `ClearAllAnnotations` method can be used to delete all annotations irrespective of their types from the PDF. 

{% tabs %}
{% highlight c# %}

pdfViewer.ClearAllAnnotations();

{% endhighlight %}
{% endtabs %}

### Detecting the removal of a free text

The event `FreeTextAnnotationRemoved` will be raised when a free text annotation is removed from the PDF.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.FreeTextAnnotationRemoved += PdfViewer_FreeTextAnnotationRemoved;

{% endhighlight %}
{% endtabs %}

The properties of the removed free text can be obtained from the `args` parameter of the event handler.

{% tabs %}
{% highlight c# %}

private void PdfViewerControl_FreeTextAnnotationRemoved(object sender, FreeTextAnnotationRemovedEventArgs args)
{
	//Get the bounds 
	CGRect bounds = args.Bounds;
	//Get the page number on which the deselected free text is 
	int pageNumber = args.PageNumber;
	//Get the text of the free text annotation 
	string text = args.Text;
	//Get the text color 
	UIColor textColor = args.TextColor;
	//Get the text size 
	float textSize = args.TextSize;

}

{% endhighlight %}
{% endtabs %}

## How to enable or disable the free text dialog

The free text dialog can be enabled or disabled for adding the free text annotation by setting the [`IsFreeTextDialogEnabled`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS.FreeTextAnnotationSettings.html#Syncfusion_SfPdfViewer_iOS_FreeTextAnnotationSettings_IsFreeTextDialogEnabled) API to true or false respectively. The default value is set to true.

{% tabs %}
{% highlight c# %}

//Disable the free text dialog
pdfViewer.AnnotationSettings.FreeText.IsFreeTextDialogEnabled = false;

{% endhighlight %}
{% endtabs %}

## How to enable or disable the free text annotation interaction

The interaction operation can be enabled or disabled for the free text annotation alone by setting the [`IsLocked`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS.FreeTextAnnotationSettings.html#Syncfusion_SfPdfViewer_iOS_FreeTextAnnotationSettings_IsLocked) API to false or true respectively.

For example, the following code disables the interaction operations for all free text annotations in the PDF. But the other annotation types can be selected, moved, resized, or removed.

{% tabs %}
{% highlight c# %}

//Disable the free text annotation interaction
pdfViewerControl.AnnotationSettings.FreeText.IsLocked = true;

{% endhighlight %}
{% endtabs %}

The interaction with the free text annotation types will be allowed only if the [`SfPdfViewer.AnnotationSettings.IsLocked`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfPdfViewer.iOS.AnnotationSettings.html#Syncfusion_SfPdfViewer_iOS_AnnotationSettings_IsLocked) API is set to false. The following code does not allow the interactions with free text annotations, although the IsLocked property of the free text annotation is set to false.

{% tabs %}
{% highlight c# %}

//Disables the free text annotation interaction, though the 'IsLocked' property is set to ‘false’
 pdfViewerControl.AnnotationSettings.IsLocked = true;
 
//Disable the free text annotation interaction
pdfViewerControl.AnnotationSettings.FreeText.IsLocked = false;

{% endhighlight %}
{% endtabs %}