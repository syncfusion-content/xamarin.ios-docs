---
layout: post
title:  Getting Started for Essential Xamarin.iOS PDF viewer
description: getting started
platform: Xamarin.iOS
control: SfPdfViewer
documentation: ug
---

# Getting Started

This section explains about the assemblies required for the deployment of SfPdfViewer and how to create simple application using the SfPdfViewer control.

## Assembly Required

### iOS(Unified) project

iOS-unified\Syncfusion.SfPdfViewer.iOS.dll


## Create a simple application with the SfPdfViewer

Follow the below steps to create a simple application with the SfPdfViewer and load a PDF document.

* Create a new iOS application for Xamarin.iOS in the Visual Studio and refer the required assembly to the project. 

* Create an instance of SfPdfViewer in view controller and add it as sub view in viewDidLoad override method.
   
{% tabs %}
{% highlight c# %}

    public override void ViewDidLoad ()
    {
        base.ViewDidLoad ();            
        SfPdfViewer pdfViewerControl = new SfPdfViewer ();
        this.View.AddSubview (pdfViewerControl);
    }

{% endhighlight %}
{% endtabs %}

* In order to update the layout of the parent view to the PDF viewer control, include the below code in ViewDidLayoutSubviews method by overriding it from ViewController.

{% tabs %}
{% highlight c# %}

    public override void ViewDidLayoutSubviews()
    {
        base.ViewDidLayoutSubviews();
	    pdfViewerControl.Frame = this.View.Frame;
    }

{% endhighlight %}
{% endtabs %}

## Loading PDF document

The LoadDocument method can be used to load a PDF document using stream input.

{% tabs %}   
{% highlight c# %}

    public override void ViewDidAppear(bool animated)
    {
        base.ViewDidAppear(animated); 
	    var fileStream = typeof(ViewController).GetTypeInfo().Assembly.GetManifestResourceStream("PDFViewerDemo.Assets.GIS Succinctly.pdf");
		pdfViewerControl.LoadDocument(fileStream);			
         
    }

{% endhighlight %}
{% endtabs %}


## Unloading PDF document from the PDF viewer

The SfPdfViewer control allows you to unload the PDF document from the viewer when the control is not in use anymore. This releases the PDF document and all its associated resources.

We need to call the Unload method of SfPdfViewer control as in the below code snippet to achieve the same.

{% tabs %} 
{% highlightc# %}

pdfViewerControl.Unload();

{% endhighlight %}
{% endtabs %}

This is how the final output will look like on iOS devices.

![](pdfviewer_images/gettingstarted.png)