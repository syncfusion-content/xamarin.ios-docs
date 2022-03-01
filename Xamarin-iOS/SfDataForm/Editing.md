---
layout: post
title: Editing | SfDataForm | Xamarin.iOS | Syncfusion
description: Editing in SfDataForm.
platform: xamarin.ios
control: SfDataForm
documentation: ug
---

# Editing 

SfDataForm provides support for several built-in editors.

## Supported editors and associated DataFormItem

<table>
<tr>
<th>
Editor name
</th>
<th>
Editor class
</th>
<th>
Data Type/Attribute
</th>
<th>
Input control loaded
</th>
</tr>
<tr>
<td>
Text
</td>
<td>
{{'[DataFormTextEditor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.DataFormTextEditor.html)'| markdownify }}
</td>
<td>
Property of type string and any other type apart from below specified cases.
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
{{'[DataFormMultiLineTextEditor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.DataFormMultiLineTextEditor.html)'| markdownify }}
</td>
<td>
Property of string type with Multiline text.
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
{{'[DataFormNumericEditor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.DataFormNumericEditor.html)'| markdownify }}
</td>
<td>
Property of type int, double, float, decimal, long types and its nullable also properties with below attributes.
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
{{'[DataFormNumericEditor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.DataFormNumericEditor.html)'| markdownify }}
</td>
<td>
Property of type int, double, float, decimal, long types and its nullable also properties with below attributes. [DataType(“Percent”)].
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
{{'[DataFormNumericEditor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.DataFormNumericEditor.html)'| markdownify }}
</td>
<td>
Property of type int, double, float, decimal, long types and its nullable also properties with below attributes. [DataType(DataType.Currency)].
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
{{'[DataFormDateEditor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.DataFormDateEditor.html)'| markdownify }}
</td>
<td>
Property of type DateTime and Property with below attribute
[DataType(DataType.Date)].
[DataType(DataType.DateTime)]
</td>
<td>
{{'[SfDatePicker](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.SfDatePicker.html)'| markdownify }}
</td>
</tr>
<tr>
<td>
Time
</td>
<td>
{{'[DataFormTimeEditor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.DataFormTimeEditor.html)'| markdownify }}
</td>
<td>
Property with below attribute.
[DataType(DataType.Time)].
</td>
<td>
{{'[SfTimePicker](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.SfTimePicker.html)'| markdownify }}
</td>
</tr>
<tr>
<td>
NumericUpDown
</td>
<td>
{{'[DataFormNumericUpDownEditor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.DataFormNumericUpDownEditor.html)'| markdownify }}
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
{{'[DataFormSegmentedEditor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.DataFormSegmentedEditor.html)'| markdownify }}
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
{{'[DataFormSwitchEditor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.DataFormSwitchEditor.html)'| markdownify }}
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
{{'[DataFormPickerEditor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.DataFormPickerEditor.html)'| markdownify }}
</td>
<td>
Property of type enum and list. 
[EnumDataTypeAttribute]
</td>
<td>
{{'[SfPicker](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.SfPicker.html)'| markdownify }}
</td>
</tr>
<tr>
<td>
Password
</td>
<td>
{{'[DataFormPasswordEditor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.DataFormPasswordEditor.html)'| markdownify }}
</td>
<td>
The String type property and property with 
[DataType(DataType.Password)] attribute.
</td>
<td>
{{'[UITextField](https://developer.apple.com/documentation/uikit/uitextfield)'| markdownify }}
</td>
</tr>
</table>

## Changing editor for type

By default, editors will be loaded based on above table. If you want to change the editor for any type, you need to use [RegisterEditor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.SfDataForm.html#Syncfusion_iOS_DataForm_SfDataForm_RegisterEditor_System_Type_System_String_) method and specify type and editor.

{% tabs %}
{% highlight c# %}
dataForm.RegisterEditor(typeof(int), "NumericUpDown");
{% endhighlight %}
{% endtabs %}

Here, `NumericUpDown` editor will be loaded for integer type instead of numeric editor.

## Changing editor for property

If you want to change the editor for any property, you need to use [RegisterEditor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.SfDataForm.html#Syncfusion_iOS_DataForm_SfDataForm_RegisterEditor_System_String_System_String_) method and specify property name and editor.

{% tabs %}
{% highlight c# %}
dataForm.RegisterEditor("Name", "DropDown");
{% endhighlight %}
{% endtabs %}

Here, Switch editor will be loaded for `Name` property (Enum type) instead of `Picker` editor.

## Customizing existing editor

You can customize the existing editors defined in above table, by overriding default editors.

Here,[DataFormTextEditor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.DataFormTextEditor.html) is customized to set different foreground for FirstName property text editor.

{% tabs %}
{% highlight c# %}
public class CustomTextEditor : DataFormTextEditor
{
    public CustomTextEditor(SfDataForm dataForm) : base(dataForm)
    {
    }

    protected override void OnInitializeView(DataFormItem dataFormItem, UITextField view)
    {
        if (dataFormItem.Name == "FirstName")
            view.TextColor = UIColor.Green;
        base.OnInitializeView(dataFormItem, view);
    }
}
dataForm.RegisterEditor("Text", new CustomTextEditor(dataForm));
{% endhighlight %}
{% endtabs %}

![Customizing existing editor of data form item in Xamarin.iOS DataForm](SfDataForm_images/EditorCustomization.png)

## Creating new custom editor

You can create custom editor by overriding [DataFormEditor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.DataFormEditor-1.html) class.
Property settings, commit, data validation can be handled by overriding required methods. Here, `UITextField` is loaded for `Age` editor.

{% tabs %}
{% highlight c# %}
public class CustomTextEditor : DataFormEditor<UITextField>
{
	public CustomTextEditor(SfDataForm dataForm) : base(dataForm)
	{
	}

	protected override UITextField OnCreateEditorView()
	{
		return new UITextField();
	}
	protected override void OnInitializeView(DataFormItem dataFormItem, UITextField view)
	{
		base.OnInitializeView(dataFormItem, view);
	}

	protected override void OnWireEvents(UITextField view)
	{
		view.ValueChanged+= OnViewValueChanged;
	}

	private void OnViewValueChanged(object sender, EventArgs e)
	{
		var view = sender as UITextField;
		if (DataForm.CommitMode == CommitMode.PropertyChanged || DataForm.ValidationMode == ValidationMode.PropertyChanged)
			this.OnValidateValue(view);
		if (this.DataForm.CommitMode != CommitMode.PropertyChanged) return;
		this.OnCommitValue(view);
		OnValidateValue(sender as UITextField);
	}


	private void OnViewPropertyChanged(object sender, PropertyChangedEventArgs e)
	{
		OnValidateValue(sender as UITextField);
	}


	protected override bool OnValidateValue(UITextField view)
	{
		return this.DataForm.Validate("Age");
	}

	protected override void OnCommitValue(UITextField view)
	{
		var dataFormItemView = view.Superview as DataFormItemView;
		this.DataForm.ItemManager.SetValue(dataFormItemView.DataFormItem, view.Text);
	}

	protected override void OnUnWireEvents(UITextField view)
	{
		view.ValueChanged -= OnViewValueChanged;
	}
}

dataForm.RegisterEditor("numeric", new CustomTextEditor(dataForm));
dataForm.RegisterEditor("Age", "numeric");
dataForm.ValidationMode = ValidationMode.LostFocus;
{% endhighlight %}
{% endtabs %}

You should manually commit the custom DataFormItem editor value by using [OnCommitValue](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.DataFormEditor-1.html#Syncfusion_iOS_DataForm_Editors_DataFormEditor_1_OnCommitValue__0_) override method of [DataFormEditor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.DataFormEditor-1.html) class on custom editor `Value` or `Focus changed` event which is used to update the custom editor value in respective property in [DataObject](https://help.syncfusion.com/xamarin-ios/sfdataform/getting-started#setting-dataobject) based on dataform [commit mode](https://help.syncfusion.com/xamarin-ios/sfdataform/editing#commit-mode) set. 

Also , you should manually validate the custom editor value in by using [OnValidateValue](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.Editors.DataFormEditor-1.html#Syncfusion_iOS_DataForm_Editors_DataFormEditor_1_OnValidateValue__0_) override method of `DataFormEditor` class on custom editor `Value` or `Focus changed` event which is used to validate the custom editor value based on data form [validation mode](https://help.syncfusion.com/xamarin-ios/sfdataform/validation?cs-save-lang=1&cs-lang=xaml#validation-mode) set. In the override method for OnValidateValue, you need to return [DataForm.Validate(string)](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.SfDataForm.html#Syncfusion_iOS_DataForm_SfDataForm_Validate) method in order to validate the particular data item.

![Creating custom editor for the data form item in Xamarin.iOS DataForm](SfDataForm_images/DataFormCustomEditor.png)

## Support for Email editor

You can load Email editor by changing `KeyBoardType` in [AutoGeneratingDataFormItem](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.SfDataForm.html) event.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Email")
    {
        (e.DataFormItem as DataFormTextItem).KeyBoardType = UIKeyboardType.EmailAddress;
    }
}
{% endhighlight %}
{% endtabs %}

![Loading Email editor to the data form item in Xamarin.iOS DataForm](SfDataForm_images/EmailEditor.png)

## Commit mode

[CommitMode](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.SfDataForm.html#Syncfusion_iOS_DataForm_SfDataForm_CommitMode) determines when the value should be committed to data object.

Below are the supported commit modes.

* LostFocus
* PropertyChanged
* Explicit

{% tabs %}
{% highlight c# %}
dataForm.CommitMode = CommitMode.LostFocus;
{% endhighlight %}
{% endtabs %}

**LostFocus**

If the commit mode is LostFocus, value is committed when the editor lost its focus.

**PropertyChanged**

Value is committed immediately when it is changed.

**Explicit**

Value should be committed manually by calling [SfDataForm.Commit](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.SfDataForm.html#Syncfusion_iOS_DataForm_SfDataForm_Commit) or [SfDataForm.Commit(propertyName)](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.SfDataForm.html#Syncfusion_iOS_DataForm_SfDataForm_Commit_System_String_) method.

Below code commits the value of all the properties in data object.

{% tabs %}
{% highlight c# %}
dataForm.Commit();
{% endhighlight %}
{% endtabs %}

If you want to commit specific property value, you need to pass property name as argument.

{% tabs %}
{% highlight c# %}
dataForm.Commit("Name");
{% endhighlight %}
{% endtabs %}

## Update editor value based on another editor

You can the update the editor value by using [SfDataForm.UpdateEditor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.SfDataForm.html#Syncfusion_iOS_DataForm_SfDataForm_UpdateEditor_System_String_) method at runtime.

{% tabs %}
{% highlight c# %}
var expenseInfo = new ExpenseInfo();
expenseInfo.PropertyChanged += ExpenseInfo_PropertyChanged;
dataForm.DataObject = expenseInfo;
SetContentView(dataForm);

private void ExpenseInfo_PropertyChanged(object sender, PropertyChangedEventArgs e)
{
    if (e.PropertyName == "Budget" || e.PropertyName == "Expense")
    {
        var item = sender as ExpenseInfo;
        item.Balance = item.Budget - item.Expense;
        dataForm.UpdateEditor("Balance");               
    }
}
{% endhighlight %}
{% endtabs %}

Here, `Balance` property value is updated based on `Budget` and `Expense` properties. For updating value in editor, `UpdateEditor` method is called.
You can download the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/UpdateEditor-2039559641).

## Converter

If you want to show the original value in different format or as different value, you need to use [Converter](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.ConverterAttribute.html) attribute.

### Changing original value of the DataForm property value using converter

Here, original value is multiplied by 10 and shown in editor. While committing, it is divided by 10 and stored in data object.

{% tabs %}
{% highlight c# %}
public class ValueConverterExt : IPropertyValueConverter
{
    public object Convert(object value)
    {            
        var amount = double.Parse(value.ToString());
        return amount * 10;
    }

    public object ConvertBack(object value)
    {
        var amount = double.Parse(value.ToString());
        return amount / 10;
    }
}

private double? amount = 1000;

[Converter(typeof(ValueConverterExt))]
public double? Amount
{
    get
    {
        return amount;
    }
    set
    {
        amount = value;
        RaisePropertyChanged("Amount");
    }
}
{% endhighlight %}
{% endtabs %}

### Using date editor for DateTimeOffset DataForm property data type

In SfDataForm, you cannot use date editor for `DateTimeOffset` property data type. To overcome this, you need to use `Converter` attribute to convert `DateTimeOffset` to `DateTime` value and vice-versa.

{% tabs %}
{% highlight c# %}

private DateTimeOffset displayDate;

[Converter(typeof(ValueConverterExt))]
public DateTimeOffset DisplayDate
{
    get
    {
        return displayDate;
    }
    set
    {
        displayDate = value;
    }
}
public class ValueConverterExt : IPropertyValueConverter
{
    public object Convert(object value)
    {
        DateTime baseTime = new DateTime(2008, 6, 19, 7, 0, 0);
        DateTime targetTime;

        var dateTimeOffset = (DateTimeOffset)value;
        dateTimeOffset = new DateTimeOffset(baseTime,
                                            TimeZoneInfo.Local.GetUtcOffset(baseTime));
        targetTime = dateTimeOffset.DateTime;
        return targetTime;
    }
    public object ConvertBack(object value)
    {
        var dateTime = (DateTime)value;
        dateTime = new DateTime(2008, 6, 19, 7, 0, 0);
        dateTime = DateTime.SpecifyKind(dateTime, DateTimeKind.Local);
        DateTimeOffset dateTimeOffset = dateTime;
        return dateTimeOffset;
    }
}
{% endhighlight %}
{% endtabs %}

You can download the source code of this demo from here [DateTimeOffsetConverter](https://github.com/SyncfusionExamples/Convert-DateTimeOffset-into-DateTime-and-back-in-Xamarin-DataForm)

## Disable editing

You can disable edit by setting [IsReadOnly](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.SfDataForm.html#Syncfusion_iOS_DataForm_SfDataForm_IsReadOnly) property of SfDataForm.

{% tabs %}
{% highlight c# %}
dataForm.IsReadOnly = true;
{% endhighlight %}
{% endtabs %}

You can also change the editing behavior by setting [IsReadOnly](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.DataFormItem.html#Syncfusion_iOS_DataForm_DataFormItem_IsReadOnly) property of [DataFormItem](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.DataFormItem.html).

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (e.DataFormItem.Name == "Salary")
            e.DataFormItem.IsReadOnly = true;
    }
}
{% endhighlight %}
{% endtabs %}

You can change the editing behavior at runtime also.

{% tabs %}
{% highlight c# %}

private void Button_Click(object sender, System.EventArgs e)
{
    var dataFormItem = dataForm.ItemManager.DataFormItems["FirstName"];
    dataFormItem.IsReadOnly = true;
}

{% endhighlight %}
{% endtabs %}

N> [DataFormItem.IsReadOnly](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.DataFormItem.html#Syncfusion_iOS_DataForm_DataFormItem_IsReadOnly) takes higher priority than [SfDataForm.IsReadOnly](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.SfDataForm.html#Syncfusion_iOS_DataForm_SfDataForm_IsReadOnly).
You can also have option to define the editing behavior from `SfDataForm.DataObject` definition using [ReadOnly](https://msdn.microsoft.com/en-us/library/system.componentmodel.readonlyattribute.aspx) attribute and [EditableAttribute](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.editableattribute.aspx)

{% tabs %}
{% highlight c# %}

private double? balance;
[ReadOnly(true)]
public double? Balance
{
    get
    {
        return balance;
    }
    set
    {
        balance = value;
        RaisePropertyChanged("Balance");
    }
}
private double? balance;
[Editable(false)]
public double? Balance
{
    get
    {
        return balance;
    }
    set
    {
        balance = value;
        RaisePropertyChanged("Balance");
    }
}

{% endhighlight %}
{% endtabs %}

You can also define the editing behavior by defining [SfDataForm.DataObject](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.iOS.DataForm.SfDataForm.html#Syncfusion_iOS_DataForm_SfDataForm_DataObject) fields definition without `setter` or with `private set`.

{% tabs %}
{% highlight c# %}
private double? balance;
public double? Balance
{
    get
    {
        return balance;
    }    
}
private double? balance;
public double? Balance
{
    get
    {
        return balance;
    }
    private set
    {
        balance = value;
    }
}
{% endhighlight %}
{% endtabs %}
