---
layout: post
title:  Getting Started for Essential Xamarin.iOS Kanban
description: getting started
platform: Xamarin.iOS
control: SfKanban
documentation: ug
---

#Kanban for Xamarin.iOS

**Create your first Kanban in Xamarin.iOS**

This section provides a quick overview for working with Essential Kanban for Xamarin.iOS. It’s an efficient way to visualize the workflow at each stage along its path to completion.

**Referencing Essential Studio Components in your Solution**

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio{18.3.0.50}\lib

Note: Assemblies are available in unzipped package location in Mac.

You have to add the following assembly reference to the iOS unified project

iOS-unified\Syncfusion.SfKanban.iOS.dll

**Create a simple SfKanban**

This section explains how to create a SfKanban and configure it. 

This is how the final output will look like on iOS devices. You can download the entire source code of this demo for Xamarin.iOS from [here](https://github.com/SyncfusionExamples/xamarin.ios-kanban-getting-started).

![Kanban](kanban_images/kanban.png)

In this walk through, you will create a new application that contains the SfKanban which includes the below topics.

* Adding SfKanban in Xamarin.iOS
* Create data model
* Binding data
* Defining columns
* Working with Workflows
* Work In-Progress Limit

**Adding SfKanban in Xamarin.iOS**

1. Add the required assembly references to the project as discussed in the _Reference Essential Studio Components in your Solution_ section.
2. Import [`SfKanban`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html) control namespace [`Syncfusion.SfKanban.iOS`](https://help.syncfusion.com/cr/xamarin-ios/sfkanban).
3. Create an instance of [`SfKanban`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html) control and add as a SubView to a UIViewController.


{% highlight C# %}
public partial class ViewController : UIViewController

{

	private SfKanban kanban;

	protected ViewController(IntPtr handle) : base(handle)
	{
		
	}

	public override void ViewDidLoad()
	{		
		base.ViewDidLoad();	
		kanban = new SfKanban();	
		kanban.Frame = this.View.Bounds;	
		View.AddSubview(kanban); 	
	}

}
{% endhighlight %}

**Create KanbanModel for the SfKanban**

Create a collection of [`KanbanModel`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanModel.html) objects for populating [`SfKanban`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html).

{% highlight C# %}
using Syncfusion.SfKanban.iOS;
using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;

namespace Kanban_GettingStarted
{
    public class DataModel
    {
        public ObservableCollection<KanbanModel> Cards { get; set; }

        public List<object> IList;

        public DataModel()
        {
            Cards = new ObservableCollection<KanbanModel>();

            IList = new List<object>() { "Open", "Test", "Close", "InProgress" };

            Cards.Add(
                new KanbanModel()
                {
                    ID = 1,
                    Title = "iOS - 1",
                    ImageURL = "Image1.png",
                    Category = "Open",
                    Description = "Analyze customer requirements",
                    ColorKey = "Red",
                    Tags = new string[] { "Bug", "Customer", "Release Bug" }
                }
            );

            Cards.Add(
                new KanbanModel()
                {
                    ID = 6,
                    Title = "Xamarin - 6",
                    ImageURL = "Image2.png",
                    Category = "Open",
                    Description = "Show the retrived data from the server in grid control",
                    ColorKey = "Red",
                    Tags = new string[] { "Bug", "Customer", "Breaking Issue" }
                }
            );

            Cards.Add(
                new KanbanModel()
                {
                    ID = 3,
                    Title = "iOS - 3",
                    ImageURL = "Image3.png",
                    Category = "Open",
                    Description = "Fix the filtering issues reported in safari",
                    ColorKey = "Red",
                    Tags = new string[] { "Bug", "Customer", "Breaking Issue" }
                }
            );

            Cards.Add(
                new KanbanModel()
                {
                    ID = 11,
                    Title = "iOS - 11",
                    ImageURL = "Image4.png",
                    Category = "Open",
                    Description = "Add input validation for editing",
                    ColorKey = "Red",
                    Tags = new string[] { "Bug", "Customer", "Breaking Issue" }
                }
            );

            Cards.Add(
                new KanbanModel()
                {
                    ID = 15,
                    Title = "Android - 15",
                    Category = "Open",
                    ImageURL = "Image5.png",
                    Description = "Arrange web meeting for cutomer requirement",
                    ColorKey = "Red",
                    Tags = new string[] { "Story", "Kanban" }
                });

            Cards.Add(
                new KanbanModel()
                {
                    ID = 3,
                    Title = "Android - 3",
                    Category = "Code Review",
                    ImageURL = "Image6.png",
                    Description = "API Improvements",
                    ColorKey = "Purple",
                    Tags = new string[] { "Bug", "Customer" }
                });

            Cards.Add(
                new KanbanModel()
                {
                    ID = 4,
                    Title = "UWP - 4",
                    ImageURL = "Image7.png",
                    Category = "Code Review",
                    Description = "Enhance editing functionality",
                    ColorKey = "Brown",
                    Tags = new string[] { "Story", "Kanban" }
                });

            Cards.Add(
                new KanbanModel()
                {
                    ID = 9,
                    Title = "Xamarin - 9",
                    ImageURL = "Image8.png",
                    Category = "Code Review",
                    Description = "Improve application performance",
                    ColorKey = "Orange",
                    Tags = new string[] { "Story", "Kanban" }
                }
            );

            Cards.Add(
                new KanbanModel()
                {
                    ID = 13,
                    Title = "UWP - 13",
                    ImageURL = "Image9.png",
                    Category = "In Progress",
                    Description = "Add responsive support to applicaton",
                    ColorKey = "Brown",
                    Tags = new string[] { "Story", "Kanban" }
                }
            );

            Cards.Add(
                new KanbanModel()
                {
                    ID = 17,
                    Title = "Xamarin - 17",
                    Category = "In Progress",
                    ImageURL = "Image10.png",
                    Description = "Fix the issues reported in IE browser",
                    ColorKey = "Brown",
                    Tags = new string[] { "Bug", "Customer" }
                }
            );

            Cards.Add(
                new KanbanModel()
                {
                    ID = 21,
                    Title = "Xamarin - 21",
                    Category = "In Progress",
                    ImageURL = "Image11.png",
                    Description = "Improve performance of editing functionality",
                    ColorKey = "Purple",
                    Tags = new string[] { "Bug", "Customer" }
                }
            );

            Cards.Add(
                new KanbanModel()
                {
                    ID = 19,
                    Title = "iOS - 19",
                    Category = "In Progress",
                    ImageURL = "Image12.png",
                    Description = "Fix the issues reported by the customer",
                    ColorKey = "Purple",
                    Tags = new string[] { "Bug" }
                }
            );

            Cards.Add(
                new KanbanModel()
                {
                    ID = 8,
                    Title = "Android",
                    Category = "Code Review",
                    ImageURL = "Image13.png",
                    Description = "Check login page validation",
                    ColorKey = "Brown",
                    Tags = new string[] { "Feature" }
                }
            );

            Cards.Add(
                new KanbanModel()
                {
                    ID = 24,
                    Title = "UWP - 24",
                    ImageURL = "Image14.png",
                    Category = "In Progress",
                    Description = "Test editing functionality",
                    ColorKey = "Orange",
                    Tags = new string[] { "Feature", "Customer", "Release" }
                }
            );

            Cards.Add(
                new KanbanModel()
                {
                    ID = 20,
                    Title = "iOS - 20",
                    Category = "In Progress",
                    ImageURL = "Image15.png",
                    Description = "Fix the issues reported in data binding",
                    ColorKey = "Red",
                    Tags = new string[] { "Feature", "Release", }
                }
            );

            Cards.Add(
                new KanbanModel()
                {
                    ID = 12,
                    Title = "Xamarin - 12",
                    Category = "In Progress",
                    ImageURL = "Image16.png",
                    Description = "Test editing functionality",
                    ColorKey = "Red",
                    Tags = new string[] { "Feature", "Release", }
                }
            );

            Cards.Add(
                new KanbanModel()
                {
                    ID = 11,
                    Title = "iOS - 11",
                    Category = "In Progress",
                    ImageURL = "Image17.png",
                    Description = "Check filtering validation",
                    ColorKey = "Red",
                    Tags = new string[] { "Feature", "Release", }
                }
            );

            Cards.Add(
                new KanbanModel()
                {
                    ID = 13,
                    Title = "UWP - 13",
                    ImageURL = "Image18.png",
                    Category = "Closed",
                    Description = "Fix cannot open user's default database sql error",
                    ColorKey = "Purple",
                    Tags = new string[] { "Bug", "Internal", "Release" }
                });

            Cards.Add(
                new KanbanModel()
                {
                    ID = 14,
                    Title = "Android - 14",
                    Category = "Closed",
                    ImageURL = "Image19.png",
                    Description = "Arrange web meeting with customer to get login page requirement",
                    ColorKey = "Red",
                    Tags = new string[] { "Feature" }
                }
            );

            Cards.Add(
                new KanbanModel()
                {
                    ID = 15,
                    Title = "Xamarin - 15",
                    Category = "Closed",
                    ImageURL = "Image20.png",
                    Description = "Login page validation",
                    ColorKey = "Red",
                    Tags = new string[] { "Bug" }
                }
            );

            Cards.Add(
                new KanbanModel()
                {
                    ID = 16,
                    Title = "Xamarin - 16",
                    ImageURL = "Image21.png",
                    Category = "Closed",
                    Description = "Test the application in IE browser",
                    ColorKey = "Purple",
                    Tags = new string[] { "Bug" }
                }
            );

            Cards.Add(
                new KanbanModel()
                {
                    ID = 20,
                    Title = "UWP - 20",
                    ImageURL = "Image22.png",
                    Category = "Closed",
                    Description = "Analyze stored procedure",
                    ColorKey = "Brown",
                    Tags = new string[] { "CustomSample", "Customer", "Incident" }
                }
            );

            Cards.Add(
                new KanbanModel()
                {
                    ID = 21,
                    Title = "Android - 21",
                    Category = "Closed",
                    ImageURL = "Image23.png",
                    Description = "Arrange web meeting with customer to get editing requirements",
                    ColorKey = "Orange",
                    Tags = new string[] { "Story", "Improvement" }
                }
            );
        }
    }
}    
{% endhighlight %}

**Binding data to SfKanban**

In order to bind the data source of the [`SfKanban`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html), set [`ItemsSource`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html#Syncfusion_SfKanban_iOS_SfKanban_ItemsSource) property as shown below. The following code binds the collection created in previous step to [`ItemsSource`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html#Syncfusion_SfKanban_iOS_SfKanban_ItemsSource) property.

{% highlight C# %}
DataModel model = new DataModel();
kanban.ItemsSource = model.Cards;
{% endhighlight %}
**Defining Columns**

By default, we need to define the columns manually by adding the [`KanbanColumn`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanColumn.html) object to the [`Columns`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html#Syncfusion_SfKanban_iOS_SfKanban_Columns) collection property in [`SfKanban`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html). 

[`ItemsSource`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html#Syncfusion_SfKanban_iOS_SfKanban_ItemsSource) which was bound to the kanban will be added to the respective columns using [`ColumnMappingPath`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html#Syncfusion_SfKanban_iOS_SfKanban_ColumnMappingPath) property in [`SfKanban`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html) and [`Categories`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanColumn.html#Syncfusion_SfKanban_iOS_KanbanColumn_Categories) collection property in [`KanbanColumn`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanColumn.html).

We need to set the required property name to [`ColumnMappingPath`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html#Syncfusion_SfKanban_iOS_SfKanban_ColumnMappingPath) which will be essential to add the data to the respective columns.

In this example, data whose [`Category`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanModel.html#Syncfusion_SfKanban_iOS_KanbanModel_Category) property’s value is set as `Open` will be added to the openColumn, [`Title`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanColumn.html#Syncfusion_SfKanban_iOS_KanbanColumn_Title) and other data will be added to the respective columns.

The following code example illustrates how this can be done.

{% highlight C# %}
kanban.ColumnMappingPath = "Category"; 
 
KanbanColumn column1 = new KanbanColumn();
column1.Title = "To Do";
column1.MinimumLimit = 5;
column1.MaximumLimit = 15;
column1.Categories = new List<object> { "Open", "Postponed", "Validated" };
kanban.Columns.Add(column1);

KanbanColumn column2 = new KanbanColumn();
column2.Title = "In Progress";
column2.MinimumLimit = 3;
column2.MaximumLimit = 8;
column2.Categories = new List<object> { "In Progress" };
kanban.Columns.Add(column2);

KanbanColumn column3 = new KanbanColumn();
column3.Title = "Code Review";
column3.MinimumLimit = 5;
column3.MaximumLimit = 10;
column3.Categories = new List<object> { "Code Review" };
kanban.Columns.Add(column3);

KanbanColumn column4 = new KanbanColumn();
column4.Title = "Done";
column4.MinimumLimit = 8;
column4.MaximumLimit = 12;
column4.Categories = new List<object> { "Closed", "Closed-No Code Changes", "Resolved" };
kanban.Columns.Add(column4);
{% endhighlight %}

You can also set [`AutoGenerateColumns`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html#Syncfusion_SfKanban_iOS_SfKanban_AutoGenerateColumns) property to true in which you don't need to define the columns as mentioned in the above example.  This will create columns depending on the [`ColumnMappingPath`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html#Syncfusion_SfKanban_iOS_SfKanban_ColumnMappingPath) property for all the distinct values in [`ItemsSource`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html#Syncfusion_SfKanban_iOS_SfKanban_ItemsSource).

When the columns are auto-generated, you can handle the [`ColumnsGenerated`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html) event to customize the columns after they are added to the [`ActualColumns`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html#Syncfusion_SfKanban_iOS_SfKanban_ActualColumns) collection in [`SfKanban`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html).

## Customizing Column Size

By default, columns are sized smartly to arrange the default elements of the cards with better readability. However, you can define the minimum and maximum width for the columns in SfKanban using [`SfKanban.MinColumnWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html#Syncfusion_SfKanban_iOS_SfKanban_MinColumnWidth) and [`SfKanban.MaxColumnWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html#Syncfusion_SfKanban_iOS_SfKanban_MaxColumnWidth) properties respectively.

{% highlight C# %}

kanban.MaxColumnWidth = 340;
kanban.MinColumnWidth = 300;

{% endhighlight %}

You can also define the exact column width using [`SfKanban.ColumnWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html#Syncfusion_SfKanban_iOS_SfKanban_ColumnWidth) property.

{% highlight C# %}

kanban.ColumnWidth = 250;
	
{% endhighlight %}

## Expand/Collapse Column

Columns can be expanded/collapsed by tapping the toggle button which is placed at top right corner of the Kanban header. [`IsExpanded`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanColumn.html#Syncfusion_SfKanban_iOS_KanbanColumn_IsExpanded) property is used to programmatically expand/collapse the Kanban column. The following code example describes the above behavior.

{% highlight C# %}

KanbanColumn openColumn = new KanbanColumn();
openColumn.IsExpanded = false; 
KanbanColumn progressColumn = new KanbanColumn();
progressColumn.IsExpanded = false;

kanban.Columns.Add(openColumn);
kanban.Columns.Add(progressColumn);

{% endhighlight %}

## Enable/Disable Drag & Drop

You can enable and disable the drag and drop operation of the cards for particular column using [`KanbanColumn.AllowDrag`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanColumn.html#Syncfusion_SfKanban_iOS_KanbanColumn_AllowDrag) and [`KanbanColumn.AllowDrop`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanColumn.html#Syncfusion_SfKanban_iOS_KanbanColumn_AllowDrop) properties.

The following code is used to disable the drag operation from progress column.

{% highlight C# %}

KanbanColumn progressColumn = new KanbanColumn();
progressColumn.AllowDrag = false;

{% endhighlight %}

The following code is used to disable the drop operation of the cards into the progress column.

{% highlight C# %}

KanbanColumn progressColumn = new KanbanColumn();
progressColumn.AllowDrop = false;

{% endhighlight %}

## Items Count

[`ItemsCount`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanColumn.html#Syncfusion_SfKanban_iOS_KanbanColumn_ItemsCount) property is used to get the total cards count in each column.

{% highlight C# %}

int count = openColumn.ItemsCount;         

{% endhighlight %}

**Working with workflows**

A Kanban workflow is a set of [`Category`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanWorkflow.html#Syncfusion_SfKanban_iOS_KanbanWorkflow_Category) and  [`AllowedTransitions`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanWorkflow.html#Syncfusion_SfKanban_iOS_KanbanWorkflow_AllowedTransitions), that an item moves through during its life cycle and typically represents processes within your organization.

[`Category`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanWorkflow.html#Syncfusion_SfKanban_iOS_KanbanWorkflow_Category) represents a state of an item at a particular point in a specific workflow. An item can be in only one category at a specific point of time.

[`AllowedTransitions`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanWorkflow.html#Syncfusion_SfKanban_iOS_KanbanWorkflow_AllowedTransitions) is a list of categories to where the card can be moved from the current category. 

**Creating the workflows**

Initialize [`Workflows`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html#Syncfusion_SfKanban_iOS_SfKanban_Workflows) property with a list of [`KanbanWorkflow`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanWorkflow.html) instances. Each instance represents a workflow in Kanban. The following code example illustrates how this can be done.

{% highlight C# %}
List<KanbanWorkflow> keyfield = new List<KanbanWorkflow>();
keyfield.Add(new KanbanWorkflow("Open", new List<object> { "In Progress" }));
keyfield.Add(new KanbanWorkflow("In Progress", new List<object> { "Postponed", "Validated", "Code Review", "Closed-No Code Changes" }));
keyfield.Add(new KanbanWorkflow("Code Review", new List<object> { "Closed", "Resolved" }));
keyfield.Add(new KanbanWorkflow("Closed", new List<object> { "Open" }));
keyfield.Add(new KanbanWorkflow("Postponed", new List<object> { "In Progress" }));
keyfield.Add(new KanbanWorkflow("Validated", new List<object> { "In Progress" }));
keyfield.Add(new KanbanWorkflow("Closed-No Code Changes", new List<object> { }));
keyfield.Add(new KanbanWorkflow("Resolved", new List<object> { }));

kanban.Workflows = keyfield;  
{% endhighlight %}

**Work In-Progress Limit**

In column, you can set minimum and maximum items limit by using the [`MinimumLimit`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanColumn.html#Syncfusion_SfKanban_iOS_KanbanColumn_MinimumLimit) and [`MaximumLimit`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanColumn.html#Syncfusion_SfKanban_iOS_KanbanColumn_MaximumLimit) properties. However, this will not restrict moving the items from one column to another column. But the violation of the limit can be indicated by changing the color of the error bar. 

{% highlight C# %}
column1.MinimumLimit = 5;
column1.MaximumLimit = 15;   
{% endhighlight %}

Following properties of [`ErrorBarSettings`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanColumn.html#Syncfusion_SfKanban_iOS_KanbanColumn_ErrorBarSettings) are used to customize its appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanErrorBarSettings.html#Syncfusion_SfKanban_iOS_KanbanErrorBarSettings_Color) – used to change the default color of the error bar
* [`MaxValidationColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanErrorBarSettings.html#Syncfusion_SfKanban_iOS_KanbanErrorBarSettings_MaxValidationColor) – used to change the maximum validation color of the error bar
* [`MinValidationColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanErrorBarSettings.html#Syncfusion_SfKanban_iOS_KanbanErrorBarSettings_MinValidationColor) – used to change the minimum validation color of the error bar
* [`Height`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanErrorBarSettings.html#Syncfusion_SfKanban_iOS_KanbanErrorBarSettings_Height) – used to change the height of the error bar

{% highlight C# %}
openColumn.ErrorBarSettings.Color = UIColor.Green; 
openColumn.ErrorBarSettings.MinValidationColor = UIColor.Orange; 
openColumn.ErrorBarSettings.MaxValidationColor = UIColor.Red; 
openColumn.ErrorBarSettings.Height = 4;    
{% endhighlight %}
