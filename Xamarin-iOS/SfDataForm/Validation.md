---
layout: post
title: Validation | SfDataForm | Xamarin.iOS | Syncfusion
description: How to validate the data in SfDataForm.
platform: xamarin.ios
control: SfDataForm
documentation: ug
---

# Validation 

SfDataForm allows you to validate the data and display hints in case of validation is not passed. In case of invalid data, error message is shown at the bottom of the editor.

## Built in validations

Below are the supported built in validations.

* IDataErrorInfo
* INotifyDataErrorInfo
* Data annotation

### Using IDataErrorInfo

You can validate the data by implementing the [IDataErrorInfo](https://msdn.microsoft.com/en-us/library/system.componentmodel.idataerrorinfo.aspx) interface in the data object class.

{% tabs %}
{% highlight c# %}
public class EmployeeInfo : IDataErrorInfo, INotifyPropertyChanged
{
    private int _EmployeeID;
    private string _Name;
    private string _Title;       

    public event PropertyChangedEventHandler PropertyChanged;

    public EmployeeInfo()
    {

    }

    public int EmployeeID
    {
        get { return this._EmployeeID; }
        set
        {
            this._EmployeeID = value;
            this.RaisePropertyChanged("EmployeeID");        
        }
    }
    public string Name
    {
        get { return this._Name; }
        set
        {
            this._Name = value;
            this.RaisePropertyChanged("Name");
        }
    }


    public string Title
    {
        get { return this._Title; }
        set
        {
            this._Title = value;
            this.RaisePropertyChanged("Title");
        }
    }

    [Display(AutoGenerateField = false)]
    public string Error
    {
        get
        {
            return string.Empty;
        }
    }

    public string this[string columnName]
    {
        get
        {
            if (!columnName.Equals("Title"))
                return string.Empty;

            if (this.Title.Contains("Marketing"))
                return "Marketing is not allowed";

            return string.Empty;
        }
    }

    private void RaisePropertyChanged(string propertyName)
    {
        if (PropertyChanged != null)
            PropertyChanged(this, new PropertyChangedEventArgs(propertyName));
    }
}
{% endhighlight %}
{% endtabs %}

![Validation in Xamarin.iOS DataForm](SfDataForm_images/Validation1.png)

### Using INotifyDataErrorInfo

You can validate the data by implementing the [INotifyDataErrorInfo](https://msdn.microsoft.com/en-us/library/system.componentmodel.inotifydataerrorinfo.aspx) interface in the data object class.

{% tabs %}
{% highlight c# %}
public class EmployeeInfo : INotifyDataErrorInfo, INotifyPropertyChanged
{
    private int _EmployeeID;
    private string _Name;
    private string _Title;

    public event PropertyChangedEventHandler PropertyChanged;
    public event EventHandler<DataErrorsChangedEventArgs> ErrorsChanged;

    public EmployeeInfo()
    {

    }

    public int EmployeeID
    {
        get { return this._EmployeeID; }
        set
        {
            this._EmployeeID = value;
            this.RaisePropertyChanged("EmployeeID");
        }
    }

    public string Name
    {
        get { return this._Name; }
        set
        {
            this._Name = value;
            this.RaisePropertyChanged("Name");
        }
    }


    public string Title
    {
        get { return this._Title; }
        set
        {
            this._Title = value;
            this.RaisePropertyChanged("Title");
        }
    }


    [Display(AutoGenerateField = false)]
    public bool HasErrors
    {
        get
        {
            return false;
        }
    }


    private void RaisePropertyChanged(string propertyName)
    {
        if (PropertyChanged != null)
            PropertyChanged(this, new PropertyChangedEventArgs(propertyName));
    }

    public IEnumerable GetErrors(string propertyName)
    {
        var list = new List<string>();
        if (!propertyName.Equals("Title"))
            return list;

        if (this.Title.Contains("Marketing"))
            list.Add("Marketing is not allowed");
        return list;
    }
}
{% endhighlight %}
{% endtabs %}

### Data annotations

You can validate the data using data annotation attributes.
The numeric type like int, double, decimal properties can be validated using [Range](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.rangeattribute.aspx) attributes.

{% tabs %}
{% highlight c# %}
private int _EmployeeID;
[Range(1000, 1500, ErrorMessage = "EmployeeID should be between 1000 and 1500")]
public int EmployeeID
{
    get { return this._EmployeeID; }
    set
    {
        this._EmployeeID = value;
        this.RaisePropertyChanged("EmployeeID");
    }
}
{% endhighlight %}
{% endtabs %}

The string type property can be validated using [Required](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.requiredattribute.aspx), [StringLength](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.stringlengthattribute.aspx) attributes.

{% tabs %}
{% highlight c# %}
private string _Name;

[Required(AllowEmptyStrings = false, ErrorMessage = "Name should not be empty")]
[StringLength(10, ErrorMessage = "Name should not exceed 10 characters")]
public string Name
{
    get { return this._Name; }
    set
    {
        this._Name = value;
        this.RaisePropertyChanged("Name");
    }
}
{% endhighlight %}
{% endtabs %}

The data that has heterogeneous type (combination of number, special character) can be validated using [RegularExpressions](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.regularexpressionattribute.aspx).

{% tabs %}
{% highlight c# %}
string customerId;

[RegularExpressionAttribute(@"^[a-zA-Z]{1,40}$", ErrorMessage = "Numbers and special characters not allowed")]
public string CustomerID
{
    get { return customerId; }
    set { customerId = value; }
}
{% endhighlight %}
{% endtabs %}

**Date range attribute**

You can validate date time value using date range attribute.
{% tabs %}
{% highlight c# %}
private DateTime joinDate;
[DateRange(MinYear = 2010, MaxYear = 2017, ErrorMessage = "Join date is invalid")]
public DateTime JoinDate
{
    get
    {
        return joinDate;
    }
    set
    {
        joinDate = value;
    }
}
{% endhighlight %}
{% endtabs %}

![Date range validation in Xamarin.iOS DataForm](SfDataForm_images/Validation2.png)

## Validation mode

[ValidationMode](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataForm.iOS~Syncfusion.iOS.DataForm.SfDataForm~ValidationMode.html) determines when the value should be validated.

Below are the supported validation modes.

* LostFocus
* PropertyChanged
* Explicit

{% tabs %}
{% highlight c# %}
dataForm.ValidationMode = ValidationMode.LostFocus;
{% endhighlight %}
{% endtabs %}

**LostFocus**

If the commit mode is LostFocus, value will be validated when the editor lost its focus.

**PropertyChanged**

Value will be validated immediately when it is changed.

**Explicit**

Value should be validated manually by calling [SfDataForm.Validate](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataForm.iOS~Syncfusion.iOS.DataForm.SfDataForm~Validate().html) or [SfDataForm.Validate (propertyName)](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataForm.iOS~Syncfusion.iOS.DataForm.SfDataForm~Validate(String).html) method.

Below code validates the value of all the properties in data object.

{% tabs %}
{% highlight c# %}
dataForm.Validate();
{% endhighlight %}
{% endtabs %}

If you want to validate specific property value, you need to pass property name as argument.

{% tabs %}
{% highlight c# %}
dataForm.Validate("Name");
{% endhighlight %}
{% endtabs %}

You can determine whether DataForm or property is valid or not by using `Validate` method.
{% tabs %}
{% highlight c# %}
bool isValid = dataForm.Validate();
bool isPropertyValid = dataForm.Validate("Property");
{% endhighlight %}
{% endtabs %}

If DataForm or property is valid, `true` will be returned. Else `false` will be returned.

Note> For validating value, new value should be committed in data object. So `ValidationMode` takes higher priority than `CommitMode`.

**Custom validation through events**

You can validate the data using [Validating](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataForm.iOS~Syncfusion.iOS.DataForm.SfDataForm~Validating_EV.html) event of SfDataForm.

{% tabs %}
{% highlight c# %}
dataForm.Validating += DataForm_Validating;
private void DataForm_Validating(object sender, ValidatingEventArgs e)
{
    if (e.PropertyName == "Name")
    {
        if (e.Value != null && e.Value.ToString().Length > 8)
        {
            e.IsValid = false;
            e.ErrorMessage = "Name should not exceed 8 characters";
        }
    }            
}
{% endhighlight %}
{% endtabs %}

You can get the notification after completing validation using [Validated](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataForm.iOS~Syncfusion.iOS.DataForm.SfDataForm~Validated_EV.html) event of SfDataForm.

{% tabs %}
{% highlight c# %}
dataForm.Validated += DataForm_Validated;
private void DataForm_Validated(object sender, ValidatedEventArgs e)
{
    var isValid = e.IsValid;
    var propertyName = e.PropertyName;
}
{% endhighlight %}
{% endtabs %}

You can get the details of invalid DataFormItems when validating the data form as `Explicit` validation mode using `ValidationCompleted` event. This event contains `ValidationCompletedEventArgs` argument, which holds a list of DataFormItem as errors. 

{% tabs %}
{% highlight c# %}
dataForm.ValidationCompleted += DataForm_ValidationCompleted; 
… 

private void DataForm_ValidationCompleted(object sender, ValidationCompletedEventArgs e) 
{ 
var invalidItems = e.Errors; 
} 
{% endhighlight %}
{% endtabs %}

## Valid or Positive message

If the value meets the desired criteria, you can show [valid or positive message](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataForm.iOS~Syncfusion.iOS.DataForm.DisplayOptionsAttribute~ValidMessage.html).  Like error message, valid message also will be displayed in the bottom of the editor.

{% tabs %}
{% highlight c# %}
private string _Name;
[DisplayOptions(ValidMessage = "Name length is enough")]
[StringLength(10, ErrorMessage = "Name should not exceed 10 characters")]
public string Name
{
    get { return this._Name; }
    set
    {
        this._Name = value;
        this.RaisePropertyChanged("Name");
    }
}
{% endhighlight %}
{% endtabs %}

![Valid message for validation in Xamarin.iOS DataForm](SfDataForm_images/ValidMessage.png)

## How to validate property value based on another value

If you want to validate one property value based on another property value, you need to use [property changed event](https://msdn.microsoft.com/en-us/library/system.componentmodel.inotifypropertychanged.propertychanged.aspx) and [Validate](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataForm.iOS~Syncfusion.iOS.DataForm.SfDataForm~Validate(String).html) method.

Here, `AccountNumber` and `AccountNumber1` fields are validated.

{% tabs %}
{% highlight c# %}
dataForm.DataObject = new RecipientInfo();
(dataForm.DataObject as INotifyPropertyChanged).PropertyChanged += DataFormGettingStarted_PropertyChanged;

private void DataFormGettingStarted_PropertyChanged(object sender, PropertyChangedEventArgs e)
{
    if (e.PropertyName.Equals("AccountNumber"))
    {
        var value = (string)sender.GetType().GetProperty("AccountNumber1").GetValue(sender);
        if (!string.IsNullOrEmpty(value))
            dataForm.Validate("AccountNumber1");
    }
    else if (e.PropertyName.Equals("AccountNumber1"))
    {
        var value = (string)sender.GetType().GetProperty("AccountNumber").GetValue(sender);
        if (!string.IsNullOrEmpty(value))
            dataForm.Validate("AccountNumber");
    }
}

{% endhighlight %}
{% endtabs %}

## Customize validation message using DataFormLayoutManager

You can use custom [DataFormLayoutManager](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormLayoutManager.html) class to customize validation message by overriding [UpdateViewForValidation](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormLayoutManager~UpdateViewForValidation.html) method. It lets you to return different custom views for each validation message based on certain conditions.

{% tabs %}
{% highlight c# %}

dataForm.LayoutManager = new DataFormLayoutManagerExt(dataForm);
public class DataFormLayoutManagerExt : DataFormLayoutManager
    {
        public DataFormLayoutManagerExt(SfDataForm dataForm) : base(dataForm)
        {
        }
        protected override UIView UpdateViewForValidation(DataFormItem dataFormItem, CoreGraphics.CGRect bounds)
        {
            base.UpdateViewForValidation(dataFormItem, bounds);

            UIView validView = new UIView(bounds);
            UILabel validMessage = new UILabel() { BackgroundColor = UIColor.Green };
            validMessage.Text = "Field value is valid";
            validMessage.Font = UIFont.FromName("HelveticaNeue", 10);
            validMessage.Frame = bounds;
            validView.AddSubview(validMessage);


            UIView inValidView = new UIView(bounds);
            UILabel inValidMessage = new UILabel() { BackgroundColor = UIColor.Red };
            inValidMessage.Text = "Field should not be empty";
            inValidMessage.Font = UIFont.FromName("HelveticaNeue", 10);
            inValidMessage.Frame = bounds;
            inValidView.AddSubview(inValidMessage);

            if (dataFormItem.IsValid)
                return validView;
            else
                return inValidView;
        }
    }

{% endhighlight %}
{% endtabs %}