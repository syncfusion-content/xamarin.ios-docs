---
layout: post
title:  Select & copy text using PDF viewer Xamarin.iOS | Syncfusion
description: Select and copy text support allows user to select the text in the PDF document and copy it to the clipboard using PDF Viewer Xamarin.iOS
platform: Xamarin.iOS
control: SfPdfViewer
documentation: ug
---

# Select and copy the text

The PDF viewer supports text selection and copy feature, which allows user to select the text in the PDF document and copy it to the clipboard. This section illustrates about how to use this feature.

<table>

<tr>
<th>Property</th>
<th>Action</th>
</tr>

<tr>
<td>IsTextSelectionEnabled</td>
<td>Gets or sets the value that enables or disables the text selection feature in the PDF viewer. This property when set to true enables text selection and vice versa. By default, this property is set to true.</td>
</tr>

</table>

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewerControl;

public override void ViewDidLoad()
{
      base.ViewDidLoad();
      pdfViewerControl = new SfPdfViewer();
      //Text selection feature in the PDF viewer is disabled.
      pdfViewerControl.IsTextSelectionEnabled = false;
      this.View.AddSubview(pdfViewerControl);
}

public override void ViewDidAppear(bool animated)
{
      base.ViewDidAppear(animated);
      var fileStream = typeof(MainViewController).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStartediOS.Assets.GIS Succinctly.pdf");
      pdfViewerControl.LoadDocument(fileStream);
}

{% endhighlight %}
{% endtabs %}

## How to enable or disable the context menu?

By default, PDF viewer comes with a context menu that will be displayed above the selected text in the PDF document, which has a button (option) to copy the selected text. The display of the context menu can be disabled by setting ShowContextMenu property of the TextSelectionSettings class to false. The below code illustrates the same. By default, context menu will be enabled in the PDF viewer. 

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewerControl;

public override void ViewDidLoad()
{
      base.ViewDidLoad();
      pdfViewerControl = new SfPdfViewer();
      //The display of the default context menu for the text selection is disabled.
      pdfViewerControl.TextSelectionSettings.ShowContextMenu = false;       
      this.View.AddSubview(pdfViewerControl);
}

public override void ViewDidAppear(bool animated)
{
      base.ViewDidAppear(animated);
      var fileStream = typeof(MainViewController).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStartediOS.Assets.GIS Succinctly.pdf");
      pdfViewerControl.LoadDocument(fileStream);
}

{% endhighlight %}
{% endtabs %}

## How to modify the selection and its handle color?

The color used for text selection and the color of the handle can be customized based on the developer’s requirements. The properties TextSelectionColor and TextSelectionHandleColor of the TextSelectionSettings class can be used to customize them. The below code snippet illustrates the same.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewerControl;

public override void ViewDidLoad()
{
      base.ViewDidLoad();
      pdfViewerControl = new SfPdfViewer();
      
      //Customizing the color being displayed while selecting the text from PDF document.

      pdfViewerControl.TextSelectionSettings.TextSelectionColor = UIColor.FromRGBA(0, 0, 255, 50);

      //Customizing the color of text selection handler displayed while selecting the text from PDF document.

      pdfViewerControl.TextSelectionSettings.TextSelectionHandleColor = UIColor.FromRGBA(0, 0, 255, 255);
      this.View.AddSubview(pdfViewerControl);
}

public override void ViewDidAppear(bool animated)
{
      base.ViewDidAppear(animated);
      var fileStream = typeof(MainViewController).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStartediOS.Assets.GIS Succinctly.pdf");
      pdfViewerControl.LoadDocument(fileStream);
}

{% endhighlight %}
{% endtabs %}

## How to acquire selected text?

The completion of the text selection action would trigger TextSelectionCompleted event.  The event argument of this event will contain a copy of the selected text in the String format. 

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewerControl;

public override void ViewDidLoad()
{
      base.ViewDidLoad();
      pdfViewerControl = new SfPdfViewer();
     // Wired up the TextSelectionCompleted event.
      pdfViewerControl.TextSelectionCompleted += PdfViewerControl_TextSelectionCompleted;
   
      this.View.AddSubview(pdfViewerControl);
}

public override void ViewDidAppear(bool animated)
{
      base.ViewDidAppear(animated);
      var fileStream = typeof(MainViewController).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStartediOS.Assets.GIS Succinctly.pdf");
      pdfViewerControl.LoadDocument(fileStream);
}

private void PdfViewerControl_TextSelectionCompleted(object sender, TextSelectionCompletedEventArgs args)
{
     //The selected text is acquired and stored in the variable selectedText.
     var selectedText = args.SelectedText;
}

{% endhighlight %}
{% endtabs %}

## How to acquire page number, page bounds and selected region?

The completion of the text selection action would trigger TextSelectionCompleted event.  The event argument would contain details about the page number in which the selection operation is performed, bounds of the page and the selection region. 

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewerControl;

public override void ViewDidLoad()
{
      base.ViewDidLoad();
      pdfViewerControl = new SfPdfViewer();
     // Wired up the TextSelectionCompleted event.
      pdfViewerControl.TextSelectionCompleted += PdfViewerControl_TextSelectionCompleted;
   
      this.View.AddSubview(pdfViewerControl);
}

public override void ViewDidAppear(bool animated)
{
      base.ViewDidAppear(animated);
      var fileStream = typeof(MainViewController).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStartediOS.Assets.GIS Succinctly.pdf");
      pdfViewerControl.LoadDocument(fileStream);
}

private void PdfViewerControl_TextSelectionCompleted(object sender, TextSelectionCompletedEventArgs args)
{

    //The number of the page in which the selection is performed is acquired.
    var pageNumberOfSelectedText = args.PageNumber;

    //The region of the text being selected is acquired.
    var selectedTextRegion = args.SelectedRegion;

    //The bounds of the page in which the selection is performed is acquired.
    var pageBounds = args.PageBounds;
}

{% endhighlight %}
{% endtabs %}