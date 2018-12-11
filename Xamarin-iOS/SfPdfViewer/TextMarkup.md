---
layout: post
title:  Working with text markup annotation
description: Working with text markup annotation
platform: Xamarin.iOS
control: SfPdfViewer
documentation: ug
---

# Working with text markup annotation

The PDF viewer supports to add, edit, and delete text markup annotations (highlight, underline, and strikethrough) in the PDF document.

## Highlight a text

The two ways to highlight a text in the PDF document are: 

1. By selecting the text and highlight option

	* Select the text in the PDF document.
    * Select “Highlight” option in the context menu that appears.
	
2. Enabling the highlight mode and selecting the text

By default, the PDF viewer will be in the scrolling and text selection mode. Once highlight annotation mode is activated, scrolling of the document will be frozen and highlight annotations will be included when you swipe over the texts in the pages of the PDF document.

XAML code to switch to highlight annotation mode

C# code to switch to highlight annotation mode

{% tabs %}
{% highlight c# %}

	internal SfPdfViewer pdfViewerControl;
	UIButton highlightAnnotationButton = new UIButton();

public override void ViewDidLoad()
{
	base.ViewDidLoad();
	pdfViewerControl = new SfPdfViewer();
	pdfViewerControl.Frame = new CGRect(this.View.Frame.X, 60,     this.View.Frame.Width, this.View.Frame.Height - 20);
	highlightAnnotationButton.Frame = new CGRect(15, 7, 35, 35);
	highlightAnnotationButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
	highlightAnnotationButton.TouchUpInside += HighlightAnnotationButton_TouchUpInside;
	highlightAnnotationButton.SetBackgroundImage(UIImage.FromFile("HighlightAnnotation.png"), UIControlState.Normal);
	this.View.Add(highlightAnnotationButton);
	this.View.AddSubview(pdfViewerControl);

}

public override void ViewDidAppear(bool animated)
{
	base.ViewDidAppear(animated);
	var fileStream = typeof(MainViewController).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStartediOS.Assets.GIS Succinctly.pdf");
	pdfViewerControl.LoadDocument(fileStream);
}
//Enable highlight annotation.
void HighlightAnnotationButton_TouchUpInside(object sender, EventArgs e)
{
	pdfViewerControl.AnnotationMode = AnnotationMode.Highlight;
}

{% endhighlight %}
{% endtabs %}

C# code to switch to normal mode from annotation mode.

{% tabs %}
{% highlight c# %}

pdfViewerControl.AnnotationMode = AnnotationMode.None;

{% endhighlight %}
{% endtabs %}

## Underline a text

The two ways to underline a text in the PDF document are: 

1. By selecting the text and underline option

	* Select the text in the PDF document.
    * Select “Underline” option in the context menu that appears.
	
2. Enabling the underline mode and selecting the text

By default, the PDF viewer will be in the scrolling and text selection mode. Once underline annotation mode is activated, scrolling of the document will be frozen and underline annotations will be included when you swipe over the texts in the pages of the PDF document.

XAML code to switch to underline annotation mode

C# code to switch to underline annotation mode

{% tabs %}
{% highlight c# %}

internal SfPdfViewer pdfViewerControl;
UIButton underlineAnnotationButton = new UIButton();

public override void ViewDidLoad()
{
	base.ViewDidLoad();

	pdfViewerControl = new SfPdfViewer();
	pdfViewerControl.Frame = new CGRect(this.View.Frame.X, 60, this.View.Frame.Width, this.View.Frame.Height - 20);
	underlineAnnotationButton.Frame = new CGRect(15, 7, 35, 35);
	underlineAnnotationButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
	underlineAnnotationButton.TouchUpInside += UnderlineAnnotationButton_TouchUpInside;
	underlineAnnotationButton.SetBackgroundImage(UIImage.FromFile("UnderlineAnnotation.png"), UIControlState.Normal);
	this.View.Add(underlineAnnotationButton);
	this.View.AddSubview(pdfViewerControl);

}

public override void ViewDidAppear(bool animated)
{
	base.ViewDidAppear(animated);
	var fileStream = typeof(MainViewController).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStartediOS.Assets.GIS Succinctly.pdf");
	pdfViewerControl.LoadDocument(fileStream);
}

//Enable underline annotation.
void UnderlineAnnotationButton_TouchUpInside(object sender, EventArgs e)
{
	pdfViewerControl.AnnotationMode = AnnotationMode.Underline;
}



{% endhighlight %}
{% endtabs %}

C# code to switch to normal mode from annotation mode.

{% tabs %}
{% highlight c# %}

pdfViewerControl.AnnotationMode = AnnotationMode.None;

{% endhighlight %}
{% endtabs %}

## Strikethrough a text

The two ways to strikethrough a text in the PDF document are: 

1. By selecting the text and strikethrough option

	* Select the text in the PDF document.
    * Select “Strikethrough” option in the context menu that appears.
	
2. Enabling the strikethrough mode and selecting the text

By default, the PDF viewer will be in the scrolling and text selection mode. Once strikethrough annotation mode is activated, scrolling of the document will be frozen and strikethrough annotations will be included when you swipe over the texts in the pages of the PDF document.

XAML code to switch to strikethrough annotation mode

C# code to switch to strikethrough annotation mode

{% tabs %}
{% highlight c# %}

internal SfPdfViewer pdfViewerControl;
UIButton strikethroughAnnotationButton = new UIButton();

public override void ViewDidLoad()
{
	base.ViewDidLoad();

	pdfViewerControl = new SfPdfViewer();
	pdfViewerControl.Frame = new CGRect(this.View.Frame.X, 60, this.View.Frame.Width, this.View.Frame.Height - 20);
	strikethroughAnnotationButton.Frame = new CGRect(15, 7, 35, 35);
	strikethroughAnnotationButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
	strikethroughAnnotationButton.TouchUpInside += StrikethroughAnnotationButton_TouchUpInside;
	strikethroughAnnotationButton.SetBackgroundImage(UIImage.FromFile("StrikethroughAnnotation.png"), UIControlState.Normal);
	this.View.Add(strikethroughAnnotationButton);
	this.View.AddSubview(pdfViewerControl);

}

public override void ViewDidAppear(bool animated)
{
	base.ViewDidAppear(animated);
	var fileStream = typeof(MainViewController).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStartediOS.Assets.GIS Succinctly.pdf");
	pdfViewerControl.LoadDocument(fileStream);
}

//Enable strikethrough annotation.
void StrikethroughAnnotationButton_TouchUpInside(object sender, EventArgs e)
{
	pdfViewerControl.AnnotationMode = AnnotationMode.Strikethrough;
}

{% endhighlight %}
{% endtabs %}

C# code to switch to normal mode from annotation mode.

{% tabs %}
{% highlight c# %}

pdfViewerControl.AnnotationMode = AnnotationMode.None;

{% endhighlight %}
{% endtabs %}

## Deleting a text markup annotation

The PDF viewer removes a single annotation in the PDF document, removes all the annotations in a page, and removes all the annotations in the document.

### Removing a single annotation.

The following code snippet illustrates removing a selected annotation in the PDF document.

{% tabs %}
{% highlight c# %}

IAnnotation annotation;
internal SfPdfViewer pdfViewerControl;
UIButton removeButton = new UIButton();

public override void ViewDidLoad()
{
	base.ViewDidLoad();

	pdfViewerControl = new SfPdfViewer();
	pdfViewerControl.Frame = new CGRect(this.View.Frame.X, 60, this.View.Frame.Width, this.View.Frame.Height - 20);
	removeButton.Frame = new CGRect(this.View.Frame.Width - 100, 7, 35, 35);
	removeButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
	removeButton.TouchUpInside += RemoveButton_TouchUpInside;
	removeButton.SetBackgroundImage(UIImage.FromFile("Remove.png"), UIControlState.Normal);
	this.View.Add(removeButton);
	this.View.AddSubview(pdfViewerControl);
	pdfViewerControl.TextMarkupSelected += PdfViewerControl_TextMarkupSelected;

}

public override void ViewDidAppear(bool animated)
{
	base.ViewDidAppear(animated);
	var fileStream = typeof(MainViewController).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStartediOS.Assets.GIS Succinctly.pdf");
	pdfViewerControl.LoadDocument(fileStream);
}

void PdfViewerControl_TextMarkupSelected(object sender, TextMarkupSelectedEventArgs args)
{
   //Get the annotation from selected event.
   annotation = sender as IAnnotation;
}

void RemoveButton_TouchUpInside(object sender, EventArgs e)
{
	pdfViewerControl.RemoveAnnotation(annotation);
}

{% endhighlight %}
{% endtabs %}

### Removing all the annotations in a page

The ClearAllAnnotations(int pageNumber) API can be used to remove all the annotations in a page of the PDF document. 

C# code to clear all the annotations in a given page number.

{% tabs %}
{% highlight c# %}

UIButton clearAllButton = new UIButton();
internal SfPdfViewer pdfViewerControl;
int pageNumber = 3;

public override void ViewDidLoad()
{
	base.ViewDidLoad();

	pdfViewerControl = new SfPdfViewer();
	pdfViewerControl.Frame = new CGRect(this.View.Frame.X, 60, this.View.Frame.Width, this.View.Frame.Height - 20);
	clearAllButton.Frame = new CGRect(this.View.Frame.Width - 100, 7, 35, 35);
	clearAllButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
	clearAllButton.TouchUpInside += clearAllButton_TouchUpInside;
	clearAllButton.SetBackgroundImage(UIImage.FromFile("Remove.png"), UIControlState.Normal);
	this.View.Add(clearAllButton);
	this.View.AddSubview(pdfViewerControl);

}

public override void ViewDidAppear(bool animated)
{
	base.ViewDidAppear(animated);
	var fileStream = typeof(MainViewController).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStartediOS.Assets.GIS Succinctly.pdf");
	pdfViewerControl.LoadDocument(fileStream);
}
//Clear all the annotations in the given page number in a button click.
void clearAllButton_TouchUpInside(object sender, EventArgs e)
{
	pdfViewerControl.ClearAllAnnotations(pageNumber);

}


{% endhighlight %}
{% endtabs %}

### Removing all the annotations in the PDF document

The ClearAllAnnotations API can be used to remove all the annotations in the PDF document.

C# code to clear all the annotations in the PDF document.

{% tabs %}
{% highlight c# %}

UIButton clearAllButton = new UIButton();
internal SfPdfViewer pdfViewerControl;

public override void ViewDidLoad()
{
	base.ViewDidLoad();

	pdfViewerControl = new SfPdfViewer();
	pdfViewerControl.Frame = new CGRect(this.View.Frame.X, 60, this.View.Frame.Width, this.View.Frame.Height - 20);
	clearAllButton.Frame = new CGRect(this.View.Frame.Width - 100, 7, 35, 35);
	clearAllButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
	clearAllButton.TouchUpInside += clearAllButton_TouchUpInside;
	clearAllButton.SetBackgroundImage(UIImage.FromFile("Remove.png"), UIControlState.Normal);
	this.View.Add(clearAllButton);
	this.View.AddSubview(pdfViewerControl);

}

public override void ViewDidAppear(bool animated)
{
	base.ViewDidAppear(animated);
	var fileStream = typeof(MainViewController).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStartediOS.Assets.GIS Succinctly.pdf");
	pdfViewerControl.LoadDocument(fileStream);
}

//Clear all the annotations in the PDF document in a button click.
void clearAllButton_TouchUpInside(object sender, EventArgs e)
{
	pdfViewerControl.ClearAllAnnotations();

}

{% endhighlight %}
{% endtabs %}

## Editing the color of the text markup annotation

You can edit the color of the text markup annotation before including the annotation and after including the annotation. 

### Before inclusion of the annotation or Default color

You can alter the default color of the annotation to change the color while including annotation. Refer to the following code sample. 

{% tabs %}
{% highlight c# %}

internal SfPdfViewer pdfViewerControl;

public override void ViewDidLoad()
{
	base.ViewDidLoad();

	pdfViewerControl = new SfPdfViewer();
	pdfViewerControl.Frame = new CGRect(this.View.Frame.X, 60, this.View.Frame.Width, this.View.Frame.Height - 20);
	this.View.AddSubview(pdfViewerControl);
	pdfViewerControl.AnnotationSettings.TextMarkup.Highlight.Color = UIColor.Blue;
	pdfViewerControl.AnnotationSettings.TextMarkup.Underline.Color = UIColor.Yellow;
	pdfViewerControl.AnnotationSettings.TextMarkup.Strikethrough.Color = UIColor.Green;
}

public override void ViewDidAppear(bool animated)
{
	base.ViewDidAppear(animated);
	var fileStream = typeof(MainViewController).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStartediOS.Assets.GIS Succinctly.pdf");
	pdfViewerControl.LoadDocument(fileStream);
}



{% endhighlight %}
{% endtabs %}

N>**Setting this property will not edit the color of annotations that are included in prior.

### After inclusion of the annotation

* Select the annotation.
* TextMarkupSelected event will be triggered and you will get a copy of selected annotation. 
* Edit the copy of annotation, so that you can edit the color of the text markup annotation.          

The following code snippet illustrates the same.    
                     
{% tabs %}
{% highlight c# %}

TextMarkupAnnotation selectedAnnotation;
internal SfPdfViewer pdfViewerControl;
UIButton redColorButton = new UIButton();

public override void ViewDidLoad()
{
	base.ViewDidLoad();

	pdfViewerControl = new SfPdfViewer();
	pdfViewerControl.Frame = new CGRect(this.View.Frame.X, 60, this.View.Frame.Width, this.View.Frame.Height - 20);
	redColorButton.Frame = new CGRect(this.View.Frame.Width - 100, 7, 35, 35);
	redColorButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
	redColorButton.BackgroundColor = UIColor.Red;
	redColorButton.TouchUpInside += RedColorButton _TouchUpInside;
	this.View.Add(redColorButton);
	this.View.AddSubview(pdfViewerControl);
	pdfViewerControl.TextMarkupSelected += PdfViewerControl_TextMarkupSelected;

}

public override void ViewDidAppear(bool animated)
{
	base.ViewDidAppear(animated);
	var fileStream = typeof(MainViewController).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStartediOS.Assets.GIS Succinctly.pdf");
	pdfViewerControl.LoadDocument(fileStream);
}

void PdfViewerControl_TextMarkupSelected(object sender, TextMarkupSelectedEventArgs args)
{
   //Get the annotation from selected event.
   selectedAnnotation = sender as TextMarkupAnnotation;
}

//Apply color to the selected annotation in a button click.
void RedColorButton_TouchUpInside(object sender, EventArgs e)
{
	if (selectedAnnotation!= null)
		selectedAnnotation.Settings.Color = UIColor.Red;
}


{% endhighlight %}
{% endtabs %}

## Performing undo and redo

The PDF viewer performs undo and redo for the changes made in annotations in the PDF document. In text markup annotation undo and redo actions are provided for: 

* Inclusion of new text markup annotation.
* Deletion of text markup annotation.
* Changing the color of the text markup annotation. 

Refer to the following code sample to perform undo and redo operations:  


{% tabs %}
{% highlight c# %}

internal SfPdfViewer pdfViewerControl;
UIButton UndoButton = new UIButton();
UIButton RedoButton = new UIButton();

public override void ViewDidLoad()
{
	base.ViewDidLoad();

	pdfViewerControl = new SfPdfViewer();
	pdfViewerControl.Frame = new CGRect(this.View.Frame.X, 60, this.View.Frame.Width, this.View.Frame.Height - 20);
	UndoButton.Frame = new CGRect(130, 7, 35,35);
	UndoButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
	UndoButton.TouchUpInside += UndoButton_TouchUpInside;
	UndoButton.SetBackgroundImage(UIImage.FromFile("Undo.png"), UIControlState.Normal);
	this.View.Add(UndoButton);

	RedoButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
		RedoButton.Frame = new CGRect(parentView.Frame.Width / 2 + 10, 7, 35,35);
		RedoButton.Frame = new CGRect(175, 7, 35,35);
	RedoButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
	RedoButton.TouchUpInside += RedoButton_TouchUpInside;
	RedoButton.SetBackgroundImage(UIImage.FromFile("Redo.png"), UIControlState.Normal);
	this.View.Add(RedoButton);            this.View.AddSubview(pdfViewerControl);

}

public override void ViewDidAppear(bool animated)
{
	base.ViewDidAppear(animated);
	var fileStream = typeof(MainViewController).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStartediOS.Assets.GIS Succinctly.pdf");
	pdfViewerControl.LoadDocument(fileStream);
}

//Perform Redo operation in a button click.
void RedoButton_TouchUpInside (object sender, EventArgs ea)
{
	pdfViewerControl.PerformRedo();
}

//Perform Undo operation in a button click.
void UndoButton_TouchUpInside(object sender, EventArgs ea)
{
	pdfViewerControl.PerformUndo();
}

{% endhighlight %}
{% endtabs %}

## Saving the PDF document

After performing all the changes over the PDF document in the PDF viewer, the resultant document can be saved using the SaveDocument() API.

{% tabs %}
{% highlight c# %}

	internal SfPdfViewer pdfViewerControl;
	UIButton saveButton = new UIButton();

public override void ViewDidLoad()
{
	base.ViewDidLoad();

	pdfViewerControl = new SfPdfViewer();
	pdfViewerControl.Frame = new CGRect(this.View.Frame.X, 60, this.View.Frame.Width, this.View.Frame.Height - 20);
	saveButton.Frame = new CGRect(55, 7, 35,35);
	saveButton.HorizontalAlignment = UIControlContentHorizontalAlignment.Center;
	saveButton.TouchUpInside += SaveButton_TouchUpInside;
	saveButton.SetBackgroundImage(UIImage.FromFile("Save.png"), UIControlState.Normal);
	this.View.Add(saveButton);
	this.View.AddSubview(pdfViewerControl);
}

public override void ViewDidAppear(bool animated)
{
	base.ViewDidAppear(animated);
	var fileStream = typeof(MainViewController).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStartediOS.Assets.GIS Succinctly.pdf");
	pdfViewerControl.LoadDocument(fileStream);
}

//Save the PDF document in a button click.
void SaveButton_TouchUpInside(object sender, EventArgs e)
{
	Stream stream = new MemoryStream();
	stream = pdfViewerControl.SaveDocument();
	string path =            Environment.GetFolderPath(Environment.SpecialFolder.Personal);
	string filePath = Path.Combine(path, "savedDocument.pdf");
	FileStream fileStream = File.Open(filePath, FileMode.Create);
	stream.Position = 0;
	stream.CopyTo(fileStream);
	fileStream.Close();
}



{% endhighlight %}
{% endtabs %}


N>*The CanUndo property is used to identify whether a document loaded in the PDF viewer is edited or not. When this property is set to true, means that the document in the PDF viewer is edited. 
