---
layout: post
title: Loading encrypted PDFs using SfPdfViewer in Xamarin.iOS | Syncfusion
description: PDF Viewer allows the user to load and view the password protected PDF documents | Xamarin.iOS | Syncfusion
platform: Xamarin.iOS
control: SfPdfViewer
documentation: ug
---

# Loading password protected PDFs

Password protected PDFs can be loaded using the `LoadDocument(Stream pdfStream, string password)` method. 

{% tabs %}
{% highlight c# %}

string password = "PASSWORD";
pdfViewerControl.LoadDocument(pdfStream, password);

{% endhighlight %}
{% endtabs %}

In the above code snippet, `pdfStream` is the Stream instance read from the encrypted PDF and `password` is the key with which the PDF is encrypted. 

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

