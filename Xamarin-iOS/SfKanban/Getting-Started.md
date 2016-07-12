#<a id="KanbaniOS"></a>Kanban for Xamarin.iOS

**Create your first Kanban in Xamarin.iOS**

This section provides a quick overview for working with Essential Kanban for Xamarin.iOS. It’s an efficient way to visualize the workflow at each stage along its path to completion.

**Referencing Essential Studio Components in your Solution**

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio{14.2.0.26}\lib

Note: Assemblies are available in unzipped package location in Mac.

You have to add the following assembly reference to the iOS unified project

iOS-unifed\Syncfusion.SfKanban.iOS.dll

**Create a simple SfKanban**

This section explains how to create a SfKanban and configure it. 

This is how the final output will look like on iOS devices. You can download the entire source code of this demo for Xamarin.iOS from [here](http://files2.syncfusion.com/Xamarin.iOS/Samples/Kanban_GettingStarted.zip).

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
2. Import `SfKanban` control namespace `Syncfusion.SfKanban.iOS`.
3. Create an instance of `SfKanban` control and add as a SubView to a UIViewController.


```csharp
public partial class ViewController : UIViewController

{

	private SfKanban kanban;

	protected ViewController(IntPtr handle) : base(handle)
	{
		// Note: this .ctor should not contain any initialization logic.
	}

	public override void ViewDidLoad()
	{		
		base.ViewDidLoad();	
		kanban = new SfKanban();	
		kanban.Frame = this.View.Bounds;	
		View.AddSubview(kanban); 	
	}

}
```

**Create KanbanModel for the SfKanban**

Create a collection of `KanbanModel` objects for populating `SfKanban`.

```csharp
using System.Collections.ObjectModel;
using Syncfusion.SfKanban.iOS; 
public partial class ViewController : UIViewController
{
    private SfKanban kanban;
		
	protected ViewController(IntPtr handle) : base(handle)
	{
		Data = ItemsSourceCards();
	}

	public ObservableCollection<KanbanModel> Data
	{
		get;
		set;
	}
	
	ObservableCollection<KanbanModel> ItemsSourceCards()
	{
		ObservableCollection<KanbanModel> cards = new ObservableCollection<KanbanModel>();
		cards.Add(new KanbanModel() { 
			ID = 1, 
			Title = "iOS - 1002", 
			ImageURL = "Image1.png", 
			Category = "Open", 
			Description = "Analyze customer requirements", 
			ColorKey = "Red",
			Tags = new string[] { "Incident", "Customer" }
		});
		
		cards.Add(new KanbanModel() { 
			ID = 6, 
			Title = "Xamarin - 4576", 
			ImageURL = "Image2.png", 
			Category = "Open",
			Description = "Show the retrieved data from the server in grid control" 
			ColorKey = "Green", 
			Tags = new string[] { "SfDataGrid", "Customer" }
		});
		
		cards.Add(new KanbanModel() { 
			ID = 13, 
			Title = "UWP - 13", 
			ImageURL = "Image4.png", 
			Category = "In Progress", 
			Description = "Add responsive support to application", 
			ColorKey = "Brown", 
			Tags = new string[] { "Story", "Kanban" } 
		});  
		
		cards.Add(new KanbanModel() { 
			ID = 2543, 
			Title = "Xamarin_iOS - 2543", 
			Category = "Code Review", 
			ImageURL = "Image12.png", 
			Description = "Provide swimlane support kanban", 
			ColorKey = "Brown", 
			Tags = new string[] { "Feature","SfKanban" } 
		});
		  
		cards.Add(new KanbanModel() { 
			ID = 1975, 
			Title = "iOS - 1975", 
			Category = "Done", 
			ImageURL = "Image11.png", 
			Description = "Fix the issues reported by the customer", 
			ColorKey = "Purple", 
			Tags = new string[] { "Bug" } 
		});   
		
		return cards; 
	} 
}     
```
**Binding data to SfKanban**

In order to bind the data source of the `SfKanban`, set `ItemsSource` property as shown below. The following code binds the collection created in previous step to `ItemsSource` property.

```csharp
kanban.ItemsSource = this.Data;
```
**Defining Columns**

By default, we need to define the columns manually by adding the `KanbanColumn` object to the `Columns` collection property in `SfKanban`. 

`ItemsSource` which was bound to the kanban will be added to the respective columns using `ColumnMappingPath` property in `SfKanban` and `Categories` collection property in `KanbanColumn`.

We need to set the required property name to `ColumnMappingPath` which will be essential to add the data to the respective columns.

In this example, data whose `Category` property’s value is set as `Open` will be added to the todoColumn and other data will be added to the respective columns.

The following code example illustrates how this can be done.

```csharp
kanban.ColumnMappingPath = "Category"; 
 
KanbanColumn todoColumn = new KanbanColumn();
todoColumn.Title = "To Do"; 
todoColumn.Categories = new List<object>() { "Open" };
kanban.Columns.Add(todoColumn);  

KanbanColumn progressColumn = new KanbanColumn();
progressColumn.Title = "In Progress";  
progressColumn.Categories = new List<object>() { "In Progress" }; 
kanban.Columns.Add(progressColumn);  
 
KanbanColumn codeColumn = new KanbanColumn(); 
codeColumn.Title = "Code Review"; 
codeColumn.Categories = new List<object>() { "Code Review" };  
kanban.Columns.Add(codeColumn);  

KanbanColumn doneColumn = new KanbanColumn(); 
doneColumn.Title = "Done"; 
doneColumn.Categories = new List<object>() { "Done" };  
kanban.Columns.Add(doneColumn); 
```

You can also set `AutoGenerateColumns` property to true in which you don't need to define the columns as mentioned in the above example.  This will create columns depending on the `ColumnMappingPath` property for all the distinct values in `ItemsSource`.

When the columns are auto-generated, you can handle the `ColumnsGenerated` event to customize the columns after they are added to the `ActualColumns` collection in `SfKanban`.

**Working with workflows**

A Kanban workflow is a set of `Category` and  `AllowedTransitions`, that an item moves through during its lifecycle and typically represents processes within your organization.

`Category ` represents a state of an item at a particular point in a specific workflow. An item can be in only one category at a specific point of time.

`AllowedTransitions` is a list of categories to where the card can be moved from the current category. 

**Creating the workflows**

Initialize `Workflows` property with a list of `KanbanWorkflow` instances. Each instance represents a workflow in Kanban. The following code example illustrates how this can be done.

```csharp
var workflows = new List<KanbanWorkflow>();

var openWorkflow = new KanbanWorkflow();
openWorkflow.Category = "Open"; 
openWorkflow.AllowedTransitions = new List<object> { "In Progress" };  

var progressWorkflow = new KanbanWorkflow(); 
progressWorkflow.Category = "In Progress"; 
progressWorkflow.AllowedTransitions = new List<object> { "Open", "Code Review", "Closed-No Code Changes" };  

workflows.Add(openWorkflow); 
workflows.Add(progressWorkflow);    

kanban.Workflows = workflows;  
```

**Work In-Progress Limit**

In column, you can set minimum and maximum items limit by using the `MinimumLimit` and `MaximumLimit` properties. However, this will not restrict moving the items from one column to another column. But the violation of the limit can be indicated by changing the color of the error bar. 

```csharp
todoColumn.MinimumLimit = 5; 
todoColumn.MaximumLimit = 10;   
```

Following properties are used to customize its appearance.

* Color – used to change the default color of the error bar
* MaxValidationColor – used to change the maximum validation color of the error bar
* MinValidationColor – used to change the minimum validation color of the error bar
* Height – used to change the height of the error bar

```csharp
todoColumn.ErrorBarSettings.Color = UIColor.Green; 
todoColumn.ErrorBarSettings.MinValidationColor = UIColor.Orange; 
todoColumn.ErrorBarSettings.MaxValidationColor = UIColor.Red; 
todoColumn.ErrorBarSettings.Height = 4;    
```