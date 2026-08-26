---
layout: post
title: Syncfusion® AutoComplete Source Mode for Xamarin.iOS
description: Learn how to use AutoCompleteSource in AutoComplete control to populate items and configure data sources.
platform: xamarin.ios 
control: AutoComplete
documentation: ug
---

# Populating Items

The SfAutoComplete control supports binding to different data sources such as IList Data Source and Observable Collection Data Source.

## Through AutoCompleteSource Item

* The `AutoCompleteSource` property in the SfAutoComplete control is used to set the list of strings for the suggestions dropdown.

* This creates a text box that automatically completes input strings by comparing the prefix being entered to the prefixes of all strings in a maintained source. This is useful for text box controls where URLs, addresses, file names, or commands will be frequently entered.

{% tabs %}

{% highlight C# %}

NSMutableArray countryList=new NSMutableArray();
countryList.Add((NSString)"Afghanistan");
countryList.Add((NSString)"Akrotiri");
countryList.Add((NSString)"Albania"); 
countryAutoComplete.AutoCompleteSource=countryList;

{% endhighlight %}

{% endtabs %}

![Autocomplete source options](images/autocompletesource.png)

## Through Data Binding

DataSource is a collection of SfAutoComplete items that can hold any objects and displays the items based on the provided `DisplayMemberPath` value.

To populate items using a data source, create a model class with the properties to be bound.

{% tabs %}

{% highlight C# %}

public class Student
{
string Name;
string Age;
public Student(string name,string age)
{
this.Name = name;
this.Age = age;

}
public string getName()
{
return Name;
}
public string getAge()
{
return Age;
}
}
{% endhighlight %}

{% endtabs %}

* Create a Student collection using the Student class and assign the collection to the DataSource property of SfAutoComplete.

{% tabs %}

{% highlight C# %}

public NSMutableArray StudentDetails
{
get;
set;
}

void GetStudentData()
{
NSMutableArray array = new NSMutableArray();
array.Add(getDictionary("John", "24"));
array.Add(getDictionary("James", "37"));

StudentDetails = array;
}

NSDictionary getDictionary(string name, string age)
{

object[] objects = new object[2];
object[] keys = new object[2];
keys.SetValue("Name", 0);
keys.SetValue("Age", 1);
objects.SetValue((NSString)name, 0);
objects.SetValue((NSString)age, 1);
return NSDictionary.FromObjectsAndKeys(objects, keys);
}

		
{% endhighlight %}

{% endtabs %}

* Since the student collection has two properties, you need to specify which property the control should use to provide suggestions. In this case, configure the control to provide suggestions based on the Name property.

{% tabs %}

{% highlight C# %}

studentAutoComplete= new SfAutoComplete();
studentAutoComplete.DataSource = StudentDetails;
studentAutoComplete.DisplayMemberPath = "Name";
studentAutoComplete.SelectedValuePath = "Age";

{% endhighlight %}

{% endtabs %}

* The `DisplayMemberPath` determines the suggestions to be shown in the dropdown. Setting the `SelectedValuePath` property will make the `SelectedValue` property return the value you have selected.

![Data source options](images/datasource.png)
