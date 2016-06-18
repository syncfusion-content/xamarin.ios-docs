---
layout: post
title: GettingStarted | DataSource | Xamarin | Syncfusion
description: How to create a sample in DataSource with sorting and grouping.
platform: xamarin.iOS
control: DataSource
documentation: UG
---
# DataSource

## Overview

DataSource is a non UI component that consumes raw data and processes data operations such as sorting, filtering and grouping saving developers’ time and efforts in building the functionality themselves. We can apply DataSource to any data bound control which can be further processed using the bound DataSource.

![](Getting-Started_images/Getting-Started_img1.png)

## Getting started 

### Assembly deployment

After installing Essential Studio for Xamarin, you can find all the required assemblies in the following installation folders,
{Syncfusion Essential Studio Installed location}\Essential Studio\{Syncfusion release version}\lib

N> Assemblies can be found in unzipped package location in Mac

Add the following assemblies to the iOS project as shown below:

**PCL project:**
<table>
<tr>
<td>
pcl\Syncfusion.DataSource.Portable.dll
</td>
</tr>
</table>

## Creating your first DataSource in Xamarin.iOS

This is how the final output will look like. You can also download the entire source code of this demo from [here](http://files2.syncfusion.com/Xamarin.iOS/Samples/DataSourceiOS_GettingStarted.zip).

![](Getting-Started_images/datasource.png)

* Create new **BlankApp** (Xamarin.iOS) application in **Xamarin Studio** or **Visual Studio**.
* Now, create a simple data source as shown in the following code example. Add the following code example in a newly created class file and save it as **Contacts.cs** file.

{% tabs %}
{% highlight c# %}
public class Contacts : INotifyPropertyChanged
{
    private string contactName;

    public Contacts(string name)
    {
        contactName = name;
    }

    public string ContactName
    {
        get { return contactName; }
        set
        {
            if (contactName != value)
            {
                contactName = value;
                this.RaisedOnPropertyChanged("ContactName");
            }
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;

    public void RaisedOnPropertyChanged(string _PropertyName)
    {
        if (PropertyChanged != null)
        {
            PropertyChanged(this, new PropertyChangedEventArgs(_PropertyName));
        }
    }
}

{% endhighlight %}
{% endtabs %}

* Add the following code example in a newly created class file and save it as **ContactList.cs** file.

{% tabs %}
{% highlight c# %}

public class ContactsList : ObservableCollection<Contacts>, INotifyPropertyChanged
{
    public ContactsList()
    {
        foreach (var cusName in CustomerNames)
        {
            var contact = new Contacts(cusName);
            this.Add(contact);
        }
    }

    string[] CustomerNames = new string[] {
        "Kyle",
        "Gina",
        "Irene",
        "Katie",
        "Michael",
        "Oscar",
        "Ralph",
        "Torrey",
        "William",
        "Bill",
        "Daniel",
        "Frank",
        "Brenda",
        "Danielle",
        "Fiona",
        "Howard",
        "Jack",
        "Larry",
        };
}

{% endhighlight %}
{% endtabs %}

* You can set the source of the DataSource by using the `DataSource.Source` property as follows. Now you can bind the `DataSource.DisplayItems` as ItemsSource for any data bound control.

{% tabs %}
{% highlight c# %}
[C#]
public App()
{
    DataSource dataSource = new DataSource();
    dataSource.Source = new ContactsList();
}
{% endhighlight %}
{% endtabs %}

## Sorting

DataSource also allows to sort the bound source by using the `DataSource.SortDescriptors` property. You can create a `SortDescriptor` for the property to be sorted and add it in the `DataSource.SortDescriptors` collection. 
SortDescriptor object holds following three properties:

* PropertyName: Name of the sorted property.
* Direction: An object of type `ListSortDirection` defines the sorting direction.
* Comparer: Comparer to be applied in when sorting take place

 The following code illustrates this.
 
{% tabs %}
{% highlight c# %}
[C#]
    dataSource.SortDescriptors.Add(new SortDescriptor("ContactName"));
{% endhighlight %}
{% endtabs %}

## Grouping

DataSource also allows to sort the bound source by using the `DataSource.GroupDescriptors` property. You can create a `GroupDescriptor` for the property to be grouped and add it in the `DataSource.GroupDescriptors` collection. 
`GroupDescriptor` object holds following two properties:

* PropertyName: Name of the grouped property.
* KeySelector: Sets the `KeySelector` for grouping
* Comparer: Comparer to be applied in when sorting take place

The following code example illustrates this without `KeySelector`.
{% tabs %}
{% highlight c# %}
[C#]
    dataSource.GroupDescriptors.Add(new GroupDescriptor("ContactName"));

{% endhighlight %}
{% endtabs %}

The following code example illustrates this with `KeySelector`.

{% tabs %}
{% highlight c# %}
[C#]
    dataSource.GroupDescriptors.Add(new GroupDescriptor() 
    {
        PropertyName = "ContactName",
        KeySelector = (object obj1) =>
        {
            var item = (obj1 as Contacts);
            return item.ContactName[0].ToString();
        }
    });

{% endhighlight %}
{% endtabs %}

## Binding DataSource to a UITableView

Please refer the below code example that illustrates binding the created DataSource to a UITableView control.

* Add the following code example in a newly created class file and save it as **TableViewSource.cs** file.

{% tabs %}
{% highlight c# %}
[C#]

    public class TableViewSource : UITableViewSource
    {

        #region Field

        DataSource dataSource;

    #endregion

    #region Constructor

    public TableViewSource(DataSource sfDataSource)
    {
        dataSource = sfDataSource;
    }

    #endregion

    #region implemented abstract members of UITableViewDataSource

    public override UITableViewCell GetCell(UITableView tableView, Foundation.NSIndexPath indexPath)
    {
        var item = dataSource.DisplayItems[indexPath.Row]  ;
        UITableViewCell cell = tableView.DequeueReusableCell("TableCell") as UITableViewCell;
        if (cell == null)
            cell = new UITableViewCell();
        if (item is Contacts)
        {
            cell.TextLabel.MinimumFontSize = 12f;
            cell.TextLabel.Text = (item as Contacts).ContactName;
            cell.TextLabel.BackgroundColor = UIColor.Clear;
            cell.TextLabel.TextAlignment = UITextAlignment.Left;
        }
        else if (item is GroupResult)
        {
            var group = item as GroupResult;
            cell.TextLabel.Font = UIFont.BoldSystemFontOfSize(14);
            cell.TextLabel.Text = group.Key.ToString();
            cell.TextLabel.TextAlignment = UITextAlignment.Center;
            cell.BackgroundColor = UIColor.Gray;
        }
        return cell;
    }

    public override nint RowsInSection(UITableView tableView, nint section)
    {
        return (nint)dataSource.DisplayItems.Count;
    }

    #endregion
} 

{% endhighlight %}
{% endtabs %}

Use below code in **SampleViewController.cs**.

{% tabs %}
{% highlight c# %}
[C#]

public SampleViewController()
{
    dataSource = new DataSource();
    dataSource.Source = new ContactsList();
    dataSource.SortDescriptors.Add(new SortDescriptor("ContactName"));
    dataSource.GroupDescriptors.Add(new GroupDescriptor()
    {
        PropertyName = "ContactName",
        KeySelector = (object obj1) =>
        {
            var item = (obj1 as Contacts);
            return item.ContactName[0].ToString();
        }
    });

    header = new UILabel();
    header.Text = "Contacts List ";
    header.BackgroundColor = UIColor.Gray;
    header.TextAlignment = UITextAlignment.Center;
    header.MinimumFontSize = 12f;


    tableView = new UITableView();
    tableView.AllowsSelection = false;
    tableView.SeparatorColor = UIColor.Clear;
    tableView.RowHeight = 30;
    tableView.EstimatedRowHeight = 30;
    tableView.Source = new TableViewSource(dataSource);
    View.BackgroundColor = UIColor.White;
    this.View.AddSubview(header);
    this.View.AddSubview(tableView);
}

public override void ViewDidLayoutSubviews()
{
    base.ViewDidLayoutSubviews();
    header.Frame = new CoreGraphics.CGRect(0, 20, this.View.Frame.Width, 50);
    tableView.Frame = new CoreGraphics.CGRect(0, 72, this.View.Frame.Width, this.View.Frame.Height - 72);
}

{% endhighlight %}
{% endtabs %}
