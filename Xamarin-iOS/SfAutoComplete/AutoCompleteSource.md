---
layout : post
title : AutoCompleteSource mode for Syncfusion AutoComplete control in Xamarin.iOS
description : Learn how to use AutoCompleteSource in AutoComplete
platform : Xamarin.iOS 
control : AutoComplete
documentation : ug
---

# Populating Items

SfAutoComplete control, supports binding to different data sources such as IList Data Source, Observable Collection Data Source. 

## Through AutoComplete Source Item 

* The `AutoCompleteSource` property in the SfAutoComplete control is used to set the list of strings to the suggestions dropdown.

* To create a Text Box that automatically completes input strings by comparing the prefix being entered to the prefixes of all strings in a maintained source. This is useful for Text Box controls in which URLs, addresses, file names, or commands will be frequently entered.

{% tabs %}

{% highlight C# %}

	NSMutableArray countryList=new NSMutableArray();
	countryList.Add((NSString)"Afghanistan");
	countryList.Add((NSString)"Akrotiri");
	countryList.Add((NSString)"Albania"); 
	countryAutoComplete.AutoCompleteSource=countryList;

{% endhighlight %}

{% endtabs %}

![](images/autocompletesource.png)

## Through Binding

DataSource is a collection of SfAutoComplete items which is capable of holding any objects and displays the items based on the provided `DisplayMemberPath` value.

To populate items using data source, create a model class with the properties that to be bound.

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

* Create Student collection using Student class and assign the collection to DataSource property of SfAutoComplete

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

* Here student collection has two properties so we should tell the control, by which property, it has to provide suggestions. In this case, let us make the control to provide suggestions based on Name.

{% tabs %}

{% highlight C# %}

			studentAutoComplete= new SfAutoComplete();
			studentAutoComplete.DataSource = StudentDetails;
			studentAutoComplete.DisplayMemberPath = "Name";
			studentAutoComplete.SelectedValuePath = "Age";

{% endhighlight %}

{% endtabs %}

* `DisplayMemberPath` decides the suggestions to be shown in dropdown. Setting the `SelectedValuePath` property will make `SelectedValue` property to return the value you have selected here. 

![](images/datasource.png)
