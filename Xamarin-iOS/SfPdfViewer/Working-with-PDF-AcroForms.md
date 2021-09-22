---
layout: post
title:  Filling PDF forms using PDF Viewer Xamarin.iOS | Syncfusion
description: Filling and signing forms in the PDF document using Syncfusion PDF Viewer control | Xamarin.iOS | Syncfusion
platform: Xamarin.iOS
control: SfPdfViewer
documentation: ug
---

# Working with PDF AcroForms

PDF Viewer supports adding/modifying the existing forms fields content present in the PDF document. By default, it detects the form fields present in the PDF document and enables modifying or filling the values.

## How to restrict editing the form field values in the existing PDF document

By setting the `EnableFormFilling` property of the PdfViewerControl instance to false, you can avoid modifying the values of the form field elements present in the loaded PDF document.

{% tabs %}
{% highlight c# %}

//Does not load the form fields in PDF viewer
pdfViewerControl.EnableFormFilling = false;

{% endhighlight %}
{% endtabs %}

N>By default, the EnableFormFilling property is set to true.

## How to flatten and save the form fields data

Flattening PDF form is a process of removing the form fields in the PDF document, thereby rendering the form fields appearance and its content in the page graphics. This will avoid the PDF form being edited in any device. PDF Viewer supports flattening the PDF form when saving. You can perform this action by passing the parameter `true` to the Save method of PDF Viewer.

{% tabs %}
{% highlight c# %}

//Flatten and save the form fields during saving process
pdfViewerControl.SaveDocument(true);

{% endhighlight %}
{% endtabs %}

## Rendering the appearance content of signature form fields

By default, the PDF viewer does not display the appearance content of signature form fields. But the appearance can be displayed by flattening the signature form fields before loading the PDF. This can be achieved by setting the `FlattenSignatureFields` property as true. The default value of the property is set as false.

{% tabs %}
{% highlight c# %}

//Sets a value whether the signature form fields should be flattened when the PDF is loaded or not.
pdfViewerControl.FormSettings.FlattenSignatureFields = true;

//Loads the PDF. 
pdfViewerControl.LoadDocument(stream);

{% endhighlight %}
{% endtabs %}

N> Signature form fields are only flattened when the page displayed in the viewer is only for viewing the appearance of signature form fields. Once the signature form fields are flattened, the interactions such as select, edit, resize, and remove cannot be performed. Setting the `FlattenSignatureFields` property as `true` will does not affect the save and form field export operations. The signature form fields will not be flattened in these operations.

## Events to track form field interaction

The PDF Viewer allows you to track form field interactions using events. The interactions on the following types of form fields can be tracked using events.

* Text
* Check Box
* Radio button
* Combo Box
* List box
* Signature

### Detecting the value change of form fields

The`FormFieldValueChanged` event will be raised when the values of the form fields are changed.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FormFieldValueChanged="PdfViewer_FormFieldValueChanged"/>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

privatevoidPdfViewerControl_FormFieldValueChanged(object sender, FormFieldValueChangedEventArgs args)
 { 
 
 //Get the name of the form field          
 string fieldName = args.FormFieldName;
 
 //Get the type of the form field   
 FormFieldType formFieldType= args.FormFieldType; 
 
 //Get the value of the form field after the event occurs    
 object newValue = args.NewValue;     
 
 //Get the value of the form field before the event occurs 
 object oldValue = args.OldValue;

 }

{% endhighlight %}
{% endtabs %}

### Detecting the focus of form fields

The `FormFieldFocused` event will be raised when text or signature field is focused.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FormFieldFocused="PdfViewer_FormFieldFocused"/>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

privatevoidPdfViewerControl_FormFieldFocused(object sender, FormFieldFocusedEventArgs args) 
{  
          
//Get the name of the form field             
string fieldName = args.FormFieldName;           

//Get the type of the form field            
FormFieldType formFieldType= args.FormFieldType; 

}

{% endhighlight %}
{% endtabs %}

N>This event will be raised only for the text and signature form fields.

### Detecting the unfocus of form fields

The `FormFieldUnfocused` event will be raised when text or signature field is unfocused.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FormFieldUnfocused="PdfViewer_FormFieldUnfocused"/>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

privatevoidPdfViewerControl_FormFieldUnfocused(object sender, FormFieldUnfocusedEventArgs args) 
{          
  //Get the name of the form field             
  string fieldName = args.FormFieldName;       

  //Get the type of the form field       
  FormFieldType formFieldType= args.FormFieldType;
  
}

{% endhighlight %}
{% endtabs %}

N>This event will be raised only for the text and signature form fields.