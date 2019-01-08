---
layout: post
title: Getting started | SfDataForm | Xamarin.iOS | Syncfusion
description: Getting started with SfDataForm.
platform: xamarin.ios
control: SfDataForm
documentation: ug
---

# SfDataForm

SfDataForm control helps to edit data fields of any data object. It can be used to develop various forms such as login, reservation, data entry, and more. Key features include the following,

* Layout and Grouping - Support for linear and grid layout along with grouping support. Support to customize layout with different heights for each item.
* Caption Customization - Support to load images as captions for editor.
* Editors - Built-in support for text, numeric, numeric up-down, picker, date picker and time picker editors. 
* Custom Editor - Support for loading custom editors.
* Validation - Built-in support to validate data based on [IDataErrorInfo](https://msdn.microsoft.com/en-us/library/system.componentmodel.idataerrorinfo.aspx), [INotifyDataErrorInfo](https://msdn.microsoft.com/en-us/library/system.componentmodel.inotifydataerrorinfo.aspx), and data annotations. Also, supports to handle validation programmatically.

# Getting Started

The section explains you the quick overview to use `SfDataForm` for Xamarin.iOS in your application.

## Assembly Deployment

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,
{Syncfusion Essential Studio Installed location} \Essential Studio\15.x.x.x\Xamarin\lib
Eg: C:\Program Files (x86) \Syncfusion\Essential Studio\15.3.0.26\Xamarin\lib

N> Assemblies can be found in unzipped package location in Mac.

### Adding SfDataForm Reference

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfDataForm to your project, open the NuGet package manager in Visual Studio, and search for [Syncfusion.Xamarin.SfDataForm](https://www.nuget.org/packages/Syncfusion.Xamarin.SfDataForm.iOS/#), and then install it.

![](SfDataForm_images/SfDataForm_NuGet_iOS.png)

To know more about obtaining our components, refer to this [link](https://help.syncfusion.com/xamarin-ios/introduction/download-and-installation). Also, if you prefer to manually refer the assemblies instead of NuGet, refer the list of assemblies mentioned in the table below.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</td>
</tr>
<tr>
<td>
Xamarin.iOS
</td>
<td>
Syncfusion.SfNumericUpDown.iOS.dll<br/>Syncfusion.SfNumericTextBox.iOS.dll<br/>Syncfusion.SfDataForm.iOS.dll<br/></td>
</tr>
</table>

>**Important** 
Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Creating SfDataForm

In this section, you will create Xamarin.iOS application with `SfDataForm`. The SfDataForm needs to be configured entirely in C# code. You can also drag the SfDataForm from ToolBox and add it to your application.

* Creating the project.
* Adding SfDataForm in Xamarin.iOS.
* Creating DataObject.
* Setting DataObject.

### Creating the project

Create new iOS application in Xamarin Studio or Visual Studio for Xamarin.iOS.

### Adding SfDataForm in Xamarin.iOS

To add SfDataForm to your application, do the following steps.
1. Add required assemblies as discussed in Assembly Deployment section.
2. Import the `SfDataForm` namespace `Syncfusion.iOS.DataForm`.
3. Create instance of SfDataForm control and add as a SubView to a [UIViewController](https://developer.xamarin.com/api/type/MonoTouch.UIKit.UIViewController/).

{% tabs %}
{% highlight c# %}

using Syncfusion.iOS.DataForm;

public partial class ViewController : UIViewController
{
    public ViewController(IntPtr handle) : base(handle)
    {
    }

    public override void ViewDidLoad()
    {
        base.ViewDidLoad();
        var dataForm = new SfDataForm(new CoreGraphics.CGRect(0,45,this.View.Frame.Width, this.View.Frame.Height));
        View.AddSubview(dataForm);
    }

    public override void DidReceiveMemoryWarning()
    {
        base.DidReceiveMemoryWarning();
    }
}
{% endhighlight %}
{% endtabs %}

### Creating DataObject

`SfDataForm` is a data edit control. So, you need to create the data object that you want to get edit.
Here data object named **ContactsInfo** created with properties.

I> Ensure to set Preserve attribute to data object to resolve linker issues. For example, when linker behaviors is "Link All", you must set `Preserve` attribute to load the SfDataForm control. 

{% tabs %}
{% highlight c# %}
using Foundation;
[Preserve(AllMembers = true)]
public class ContactsInfo
{
    private string firstName;
    private string middleName;
    private string lastName;
    private string contactNo;
    private string email;
    private string address;
    private DateTime? birthDate;
    private string groupName;

    public ContactsInfo()
    {

    }

    public string FirstName
    {
        get { return this.firstName; }
        set
        {
            this.firstName = value;
        }
    }

    public string MiddleName
    {
        get { return this.middleName; }
        set
        {
            this.middleName = value;
        }
    }
    public string LastName
    {
        get { return this.lastName; }
        set
        {
            this.lastName = value;
        }
    }

    public string ContactNumber
    {
        get { return contactNo; }
        set
        {
            this.contactNo = value;
        }
    }

    public string Email
    {
        get { return email; }
        set
        {
            email = value;
        }
    }

    public string Address
    {
        get { return address; }
        set
        {
            address = value;
        }
    }

    public DateTime? BirthDate
    {
        get { return birthDate; }
        set
        {
            birthDate = value;
        }
    }

    public string GroupName
    {
        get { return groupName; }
        set
        {
            groupName = value;
        }
    }
}
{% endhighlight %}
{% endtabs %}

## Setting DataObject

In order, to populate labels and editors in SfDataForm, set `DataObject` property of SfDataForm.

{% tabs %}
{% highlight c# %}
dataForm.DataObject = new ContactsInfo();

{% endhighlight %}
{% endtabs %}

Now run the application to render the `SfDataForm` to edit the data object as like in below.

![](SfDataForm_images/Overview.png)

You can download the entire source code of this demo for Xamarin.Forms from here [DataFormGettingStarted](http://www.syncfusion.com/downloads/support/directtrac/general/ze/DataFormGettingStarted352892937.zip).

## Defining Editors

By default, SfDataForm control generates DataFormItems (which has UI settings of data field) automatically when data object set to `SfDataForm.DataObject` property. `DataFormItem` encapsulates the layout and editor setting for a data field appearing in `SfDataForm.DataObject`. 
The type of input editor generated depends on the type of property and attribute of the property. The following table lists the `DataFormItem` and its constraints for auto generation.

<table>
<tr>
<th>Generated DataFormItem Type</th>
<th>Data Type / Attribute</th>
</tr>
<tr>
<td>
DataFormTextItem
</td>
<td>
Property of type String and any other type apart from below specified cases.
[DataType(DataType.Text)]
[DataType(DataType.MultilineText)]
[DataType(DataType.Password)]
</td>
</tr>
<tr>
<td>
DataFormNumericItem
</td>
<td>
Property of type Int or Double.
[DataType(DataType.Currency)].
[DataType(DataType.Percent)].
</td>
</tr>
<tr>
<td>
DataFormDateItem
</td>
<td>
Property of type DateTime.
[DataType(DataType.Date)].
</td>
</tr>
<tr>
<td>
DataFormTimeItem
</td>
<td>
Property of type DateTime
[DataType(DataType.Time)].
</td>
</tr>
<tr>
<td>
DataFormPickerItem
</td>
<td>
Property of type enum.
[EnumDataTypeAttribute]
</td>
</tr>
</table>

When the `DataFormItems` are auto-generated, you can handle the SfDataForm.AutoGeneratingDataFormItem event to customize or cancel the DataFormItems before they are added to the `SfDataForm`.
Below is the list of editors supported for type and attribute.

<table>
<tr>
<th>Editor</th>
<th>Data Type/Attribute</th>
<th>Input control loaded</th>
</tr>
<tr>
<td>
Text
</td>
<td>
Property of type String and any other type apart from below specified cases.
</td>
<td>
{{'[UITextField](https://developer.apple.com/documentation/uikit/uitextfield)'| markdownify }}
</td>
</tr>
<tr>
<td>
MultilineText
</td>
<td>
Property of string type.
[DataType(DataType.Multiline)] 
</td>
<td>
{{'[UITextView](https://developer.apple.com/documentation/uikit/uitextview)'| markdownify }}
</td>
</tr>
<tr>
<td>
Numeric
</td>
<td>
Property of type Int or Double.
</td>
<td>
{{'[SfNumericTextBox](https://help.syncfusion.com/xamarin-ios/sfnumerictextbox/overview)'| markdownify }}
</td>
</tr>
<tr>
<td>
Percent
</td>
<td>
Property of type Int or Double. [DataType(DataType.Percent)].
</td>
<td>
{{'[SfNumericTextBox](https://help.syncfusion.com/xamarin-ios/sfnumerictextbox/overview)'| markdownify }}
</td>
</tr>
<tr>
<td>
Currency
</td>
<td>
Property of type Int or Double.
[DataType(DataType.Currency)].
</td>
<td>
{{'[SfNumericTextBox](https://help.syncfusion.com/xamarin-ios/sfnumerictextbox/overview)'| markdownify }}
</td>
</tr>
<tr>
<td>
Date
</td>
<td>
Property of type DateTime.
[DataType(DataType.Date)].
</td>
<td>
{{'[SfDatePicker](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataForm.iOS~Syncfusion.iOS.DataForm.Editors.SfDatePicker.html)'| markdownify }}
</td>
</tr>
<tr>
<td>
Time
</td>
<td>
Property of type DateTime.
[DataType(DataType.Time)].
</td>
<td>
{{'[SfTimePicker](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataForm.iOS~Syncfusion.iOS.DataForm.Editors.SfTimePicker.html)'| markdownify }}
</td>
</tr>
<tr>
<td>
NumericUpDown
</td>
<td>
Property of type Int or Double.
</td>
<td>
{{'[SfNumericUpDown](https://help.syncfusion.com/xamarin-ios/sfnumericupdown/overview)'| markdownify }}
</td>
</tr>
<tr>
<td>
Segment
</td>
<td>
Property of type enum.
</td>
<td>
{{'[UISegmentedControl](https://developer.apple.com/documentation/uikit/uisegmentedcontrol)'| markdownify }}
</td>
</tr>
<tr>
<td>
Bool
</td>
<td>
Property of type bool
</td>
<td>
{{'[UISwitch](https://developer.apple.com/documentation/uikit/uiswitch)'| markdownify }}
</td>
</tr>
<tr>
<td>
Picker
</td>
<td>
Property of type enum, list. 
[EnumDataTypeAttribute]
</td>
<td>
{{'[SfPicker](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataForm.iOS~Syncfusion.iOS.DataForm.Editors.SfPicker.html)'| markdownify }}
</td>
</tr>
<tr>
<td>
Password
</td>
<td>
The String type property with [DataType(DataType.Password)] attribute.
</td>
<td>
{{'[UITextField](https://developer.apple.com/documentation/uikit/uitextfield)'| markdownify }}
</td>
</tr>
</table>

## Layout options

### Label Position

By default, DataForm arrange the label at left side and input control at the right side. You can change the label position by setting SfDataForm.LabelPosition property. You can position the label from left to top of input control by setting `LabelPosition` as Top.

{% tabs %}
{% highlight c# %}

dataForm.LabelPosition = LabelPosition.Top;

{% endhighlight %}
{% endtabs %}

![](SfDataForm_images/LabelTop.png)

### Grid Layout

By default, DataForm arrange one data field per row. It is possible to have more than one date field per row by setting `ColumnCount` property which provide Grid like layout for DataForm.

{% tabs %}
{% highlight c# %}

dataForm.ColumnCount = 2;

{% endhighlight %}
{% endtabs %}

![](SfDataForm_images/DataFormGrid.png)

## Editing

By default, SfDataForm allows to edit the editors. You can disable edit by setting `IsReadOnly` property of SfDataForm.
Or, you can change the editing behavior by setting `IsReadOnly` property of `DataFormItem`. DataFormItem.IsReadOnly takes higher priority.
You can also have option to define the editing behavior from `SfDataForm.DataObject` definition using [EditableAttribute](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.editableattribute.aspx)
You can also define the editing behavior by defining `SfDataForm.DataObject` fields definition without `setter` or with `private set`.
