---
layout : post
title : ComboBoxSource mode for Syncfusion® ComboBox control in Xamarin.iOS
description : Learn how to use ComboBoxSource in ComboBox
platform : xamarin.ios 
control : ComboBox
documentation : ug
---

# Populating Items

The ComboBox control supports binding to different data sources such as IList Data Source and Observable Collection Data Source.

## Using ComboBox Source Item

* The `ComboBoxSource` property in the SfComboBox control is used to set the list of strings for the dropdown list.

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
combobox.ComboBoxSource = countryList; 

{% endhighlight %}

{% endtabs %}

![](images/ComboBoxsource.png)

## Using Data Binding

DataSource is a collection of SfComboBox items that can hold any objects and display the items based on the provided `DisplayMemberPath` value.

To populate items using a data source, create a model class with the properties to be bound.

{% tabs %}

{% highlight C# %}

public class Employee 
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

private string employee_ID; 
public string Employee_ID 
{ 
    get 
    { 
        return employee_ID; 
    } 

set 
    { 
        employee_ID = value; 
    } 
} 

public Employee(string name, string employee_ID) 
{ 
    this.Name = name; 
    this.Employee_ID = employee_ID; 

} 
public string getName() 
{ 
    return Name; 
} 
public string getEmployee_ID() 
{ 
    return Employee_ID; 
} 
} 
{% endhighlight %}

{% endtabs %}

* Create an Employee collection using the Employee class and assign the collection to the DataSource property of SfComboBox.

{% tabs %}

{% highlight C# %}

public ObservableCollection<Employee> EmployeeDetails 
{ 
    get; 
    set; 
} 
void GetEmployeeData() 
{ 
    EmployeeDetails = new ObservableCollection<Employee>(); 
    EmployeeDetails.Add(new Employee("Aldrin", "1"));
    EmployeeDetails.Add(new Employee("Frank", "2"));
    EmployeeDetails.Add(new Employee("Howard", "3"));
    EmployeeDetails.Add(new Employee("James", "4"));
    EmployeeDetails.Add(new Employee("John", "5"));
    EmployeeDetails.Add(new Employee("Michael", "6"));
    EmployeeDetails.Add(new Employee("Mark", "7")); 
    EmployeeDetails.Add(new Employee("Steve", "8"));
} 

		
{% endhighlight %}

{% endtabs %}

* Since the Employee collection has two properties, you need to specify which property should be used to filter suggestions and provide the dropdown list. In this case, configure the control to provide suggestions based on the Name property.

{% tabs %}

{% highlight C# %}

SfComboBox combobox = new SfComboBox(); 
this.GetEmployeeData(); 
combobox.DisplayMemberPath = (NSString)"Name"; 
combobox.SelectedValuePath = (NSString)"Employee_ID"; 
combobox.DataSource = EmployeeDetails; 

{% endhighlight %}

{% endtabs %}

* The `DisplayMemberPath` determines the suggestions to be shown in the dropdown. Setting the `SelectedValuePath` property makes the `SelectedValue` property return the value you have selected.

![](images/datasource.png)
