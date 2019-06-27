---
layout: post
title: Getting Started with Syncfusion TabView control for Xamarin.iOS 
description: A quick tour to initial users on Syncfusion TabView control for Xamarin.iOS platform
platform: Xamarin.iOS
control: TabView
documentation: ug
---

# Getting Started

This section provides an overview for working with the tab view control for Xamarin.iOS. Walk through the entire process of creating a real-world application with tab view.

## Assembly deployment

After installing the Essential Studio for Xamarin, find all the required assemblies in the installation folders,

{Syncfusion Essential Studio Installed location}\Essential Studio\16.1.0.24\Xamarin\lib}

E.g., C:\Program Files (x86)\Syncfusion\Essential Studio\16.1.0.24\Xamarin\lib

N>In Mac, assemblies can be found in unzipped package location.


## Tab view for Xamarin.iOS

The following list of assemblies should be added as reference from the lib folder to use the tab view.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>Xamarin.iOS</td>
<td>pcl\Syncfusion.SfTabView.iOS.dll</td>
</tr>
</table>

### Create a simple tab view

This section explains how to create a simple tab view and configure it. The following screenshot illustrates the tab view in iOS devices.

![simple tab view](images/Getting-Started/xamarin_ios_tabview.png)

## Creating the project

Create a new BlankApp (iOS) application in Xamarin Studio or Visual Studio.

## Adding tab view in Xamarin.iOS

Add the required assembly reference to the project as discussed in the Assembly deployment section.

Import the control namespace as shown in the following code.

{% tabs %}

{% highlight C# %}

using Syncfusion.iOS.TabView;

{% endhighlight %}

{% endtabs %}

Set the tab view control to sub view in the `ViewDidLoad` method on the inherited class of `UIViewController`.

{% tabs %}

{% highlight c# %}

		private SfTabView tabView;
        public override void ViewDidLoad()
        {
            base.ViewDidLoad();
            tabView = new SfTabView();
            tabView.Frame = new CGRect(0, 0, View.Frame.Width, View.Frame.Height);
            View.AddSubview(tabView);
        }
		
{% endhighlight %}

{% endtabs %}

## Adding tab items

Tab items can be configured in tab view through the `Items` property of `SfTabView`, which holds the collection of `SfTabItem` through `TabItemsCollection`.

{% tabs %}

{% highlight C# %}

            var tabItems = new TabItemCollection
            {
                new SfTabItem()
                {
                    Title = "Calls",
                    Content = allContactsUIView
                },
                new SfTabItem()
                {
                    Title = "Favorites",
                    Content = favoritesUIView
                },
                new SfTabItem()
                {
                    Title = "Contacts",
                    Content = contactsUIView
                }
            };

            tabView.Items = tabItems;
            

{% endhighlight %}

{% endtabs %}

## Share the header space equally

To share the header space to the tabs equally, set the number of tabs that can be distributed in the available space though the `VisibleHeaderCount` of `SfTabView`.

{% tabs %}

{% highlight C# %}

tabView.VisibleHeaderCount = 3;

{% endhighlight %}

{% endtabs %}

After set the number of tabs, you can add the required controls to your application. Here, a `ListView` has been added in the content region.

## Adding list view in the tab view

## Preparing data

Create a view model class with `ContactsInfo` collection property, which cab be initialized with required number of data objects.

{% highlight c# %}

public class ContactInfo
{
	public string Name { get; set; }
	public long Number { get; set; }
}

public class ContactsViewModel
{
	private ObservableCollection<ContactInfo> contactList;

	public ObservableCollection<ContactInfo> ContactList
	{
		get { return contactList; }
		set { contactList = value; }
	}
	public ContactsViewModel()
	{
		ContactList = new ObservableCollection<ContactInfo>();
		ContactList.Add(new ContactInfo{Name = "Aaron",Number = 7363750});
		ContactList.Add(new ContactInfo { Name = "Adam", Number = 7323250 });
		ContactList.Add(new ContactInfo { Name = "Adrian", Number = 7239121 });
		ContactList.Add(new ContactInfo { Name = "Alwin", Number = 2329823 });
		ContactList.Add(new ContactInfo { Name = "Alex", Number = 8013481 });
		ContactList.Add(new ContactInfo { Name = "Alexander", Number = 7872329 });
		ContactList.Add(new ContactInfo { Name = "Barry", Number = 7317750 });
	}
}

{% endhighlight %}

## Binding data to table view

Create a `UITableView`, and set the data source from `ContactList`. The appearance of each cell can be customized by using the `GetCell` method of `UITableViewSource`. Similarly, the content region for other tabs also can be configured.

## ContentTransitionDuration

You can set the duration for the TabView content transition by setting `ContentTransitionDuration` property. 

{% tabs %}

{% highlight c# %}

  tabview.ContentTransitionDuration = 200;

{% endhighlight %}

{% endtabs %}

## Swiping

By default, both vertical swiping for the list view and horizontal swiping for the tab view will work. If it is not required, you can customize this by using the `EnableSwiping` property of `SfTabView`.
