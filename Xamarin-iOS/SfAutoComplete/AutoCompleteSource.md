---
layout : post
title : AutoCompleteSource mode for Syncfusion AutoComplete control in Xamarin.iOS
description : Learn how to use AutoCompleteSource in AutoComplete
platform : Xamarin.iOS 
control : AutoComplete
documentation : ug
---

# Populating Items

## AutoCompleteSource 

* The `AutoCompleteSource` property in the AutoComplete control is used to set the list of strings to the suggestions dropdown.

* To create a Text Box that automatically completes input strings by comparing the prefix being entered to the prefixes of all strings in a maintained source. This is useful for Text Box controls in which URLs, addresses, file names, or commands will be frequently entered.


{% highlight C# %}

	NSMutableArray countryList=new NSMutableArray();
	countryList.Add((NSString)"Afghanistan");
	countryList.Add((NSString)"Akrotiri");
	countryList.Add((NSString)"Albania"); 
	countryAutoComplete.AutoCompleteSource=countryList;

{% endhighlight %}


![](images/autocompletesource.png)

## DataSource

The `DataSource` property is used to set list of objects to the AutoComplete control. 

* Create Student class with two properties Name and Age.

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

* Create Student collection using Student class and assign the collection to DataSource property of AutoComplete

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

* Here student collection has two properties so we should tell the control, by which property, it has to provide suggestions. In this case, let us make the control to provide suggestions based on Name.

{% highlight C# %}

			studentAutoComplete= new SfAutoComplete();
			studentAutoComplete.DataSource = StudentDetails;
			studentAutoComplete.DisplayMemberPath = "Name";
			studentAutoComplete.SelectedValuePath = "Age";

{% endhighlight %}

* `DisplayMemberPath` decides the suggestions to be shown in dropdown. `SelectedValuePath`  Setting this will make the property `SelectedValue` return the value of the property you have selected here. 

![](images/datasource.png)
