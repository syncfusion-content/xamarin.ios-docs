---
layout: post
title: Loading encrypted PDFs using SfPdfViewer in Xamarin.iOS | Syncfusion
description: Describes how PDF Viewer allows the user to load and view the password protected PDF documents in Xamarin.iOS
platform: Xamarin.iOS
control: SfPdfViewer
documentation: ug
---

# Loading password-protected PDFs

Password protected PDFs can be loaded using the `LoadDocument(Stream pdfStream, string password)` method. 

{% tabs %}
{% highlight c# %}

string password = "PASSWORD";
pdfViewerControl.LoadDocument(pdfStream, password);

{% endhighlight %}
{% endtabs %}

In the above code snippet, `pdfStream` is the Stream instance read from the encrypted PDF and `password` is the key with which the PDF is encrypted. 

## Loading password-protected PDF asynchronously

PDF Viewer allows you to load the PDF document from the specified stream with password asynchronously using the `LoadDocumentAsync` method. You can also cancel the asynchronous PDF loading when it is in progress.

{% tabs %}
{% highlight c# %}

pdfViewerControl.LoadDocumentAsync(documentStream, password, cancellationTokenSource);

{% endhighlight %}
{% endtabs %}

In the above code sample, `documentStream` is the Stream instance read from the encrypted PDF, and the `password` is the key with that the PDF is encrypted, and the `cancellationTokenSource` enables you to cancel the asynchronous PDF loading.

For canceling the asynchronous PDF loading and detecting the cancellation when it occurred, refer the `Loading a PDF asynchronously` section of [Getting Started](https://help.syncfusion.com/xamarin-ios/sfpdfviewer/getting-started).

## Handling invalid passwords

If the password provided with the `LoadDocument(Stream pdfStream, string password)` is invalid, then the `PasswordErrorOccurred` event is raised. The `Title` property of the `PasswordErrorOccurredEventArgs` parameter helps identify whether the event raised due to invalid password. In that case the `Title` property will read "Error loading encrypted PDF document". 

{% tabs %}
{% highlight c# %}

pdfViewerControl.PasswordErrorOccurred += PdfViewerControl_PasswordErrorOccurred;
private void PdfViewerControl_PasswordErrorOccurred(object sender, PasswordErrorOccurredEventArgs args)
{
	//Get the details regarding the password error occurred. 
    string title = args.Title;
    string description = args.Description;
}

{% endhighlight %}
{% endtabs %}

N>The event will also be raised when an encrypted PDF is loaded without providing a password using the `LoadDocument(Stream pdfStream)` overload.        

