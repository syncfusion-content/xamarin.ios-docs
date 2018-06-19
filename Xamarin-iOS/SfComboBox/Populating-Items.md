---
layout : post
title : ComboBoxSource mode for Syncfusion ComboBox control in Xamarin.iOS
description : Learn how to use ComboBoxSource in ComboBox
platform : Xamarin.iOS 
control : ComboBox
documentation : ug
---

# Populating items

The combo box control, supports binding to different data sources such as IList Data Source and Observable Collection Data Source. 

## Using combo box source item 

* The ComboBoxSource property in the SfComboBox control is used to set the list of strings to the dropdown list.

{% tabs %}

{% highlight C# %}

NSMutableArray countryList = new NSMutableArray();          
countryList.Add((NSString)"Argentina"); 
countryList.Add((NSString)"Australia"); 
countryList.Add((NSString)"Belgium"); 
countryList.Add((NSString)"Brazil"); 
countryList.Add((NSString)"Canada"); 
countryList.Add((NSString)"China"); 
countryList.Add((NSString)"Denmark"); 
countryList.Add((NSString)"Dominica"); 
sfCombo.ComboBoxSource = countryList; 

{% endhighlight %}

{% endtabs %}

![](images/ComboBoxsource.png)

## Using binding

DataSource is a collection of SfComboBox items which is capable of holding any objects and displaying the items based on the provided `DisplayMemberPath` value. 

To populate items using data source, create a model class with the properties that to be bound. 

{% tabs %}

{% highlight C# %}

public class Student 
{ 
private string name; 
public string Name 
{ 
    get 
    { 
        return name; 
    } 

set 
    { 
        name = value; 
    }          
} 

private string age; 
public string Age 
{ 
    get 
    { 
        return age; 
    } 

set 
    { 
        age = value; 
    } 
} 

public Student(string name, string age) 
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

* Create student collection using student class and assign the collection to the DataSource property of SfComboBox

{% tabs %}

{% highlight C# %}

public ObservableCollection<Student> StudentDetails 
{ 
    get; 
    set; 
} 
void GetStudentData() 
{ 
    StudentDetails = new ObservableCollection<Student>(); 
    StudentDetails.Add(new Student("John", "24")); 
    StudentDetails.Add(new Student("James", "37")); 
} 

		
{% endhighlight %}

{% endtabs %}

* Here student collection has two properties. So you should intimate by which property it should filter suggestions, it must provide the drop-down list. In this case, make the control to provide suggestions based on Name.

{% tabs %}

{% highlight C# %}

SfComboBox sfCombo = new SfComboBox(); 
this.GetStudentData(); 
sfCombo.DisplayMemberPath = (NSString)"Name"; 
sfCombo.SelectedValuePath = (NSString)"Age"; 
sfCombo.DataSource = StudentDetails; 

{% endhighlight %}

{% endtabs %}

* `DisplayMemberPath` decides the suggestions to be shown in dropdown. Setting the `SelectedValuePath` property makes the `SelectedValue` property to return the value you have selected here. 

![](images/datasource.png)
