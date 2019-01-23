---
layout: post
title:  Working with Document Link Annotation (Table of content) | Syncfusion
description: Working with Document Link Annotation (Table of content) in Xamarin.iOS PDF viewer
platform: Xamarin.iOS
control: SfPdfViewer
documentation: ug
---

# Working with Document Link Annotation (Table of content)

The PDF viewer navigates to a specific destination within the PDF document.


## How to disable document link navigation in PDF document using PDF viewer control?

Set the “EnableDocumentLinkAnnotation” property to false to disable the document link navigation in PDF viewer. 

{% tabs %}
{% highlight c# %}

pdfViewerControl.EnableDocumentLinkAnnotation = false;

{% endhighlight %}
{% endtabs %}

N>By default, the EnableDocumentLinkAnnotation property is set to true.
