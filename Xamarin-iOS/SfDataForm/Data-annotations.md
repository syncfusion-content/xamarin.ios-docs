---
layout: post
title: Data annotations | SfDataForm | Xamarin.iOS | Syncfusion
description: Supported Data annotations in SfDataForm.
platform: Xamarin.iOS
control: SfDataForm
documentation: UG
---

# Data annotations

DataForm provides support for below attributes.

## Display attribute

<table>
<tr>
<th>Property</th>
<th>Details</th>
</tr>
<tr>
<td>
Name
</td>
<td>
Specifies label text
</td>
</tr>
<tr>
<td>
GroupName
</td>
<td>
Specifies the group name which is used to group fields in DataForm. Refer here for more details.
</td>
</tr>
<tr>
<td>
ShortName
</td>
<td>
Specifies label text. It takes higher priority than Name.
</td>
</tr>
<tr>
<td>
AutoGenerateField
</td>
<td>
Specifies whether the field should be auto generated or not.
Refer here for more details.
</td>
</tr>
<tr>
<td>
Prompt
</td>
<td>
Specifies watermark text for editor. Refer here for more details.
</td>
</tr>
<tr>
<td>
Order
</td>
<td>
Specifies the order of the field in data form.
Refer here for more details.
</td>
</tr>
</table>

## Validation attributes

<table>
<tr>
<th>Property</th>
<th>Details</th>
</tr>
<tr>
<td>
MinLenth

</td>
<td>
Specifies the minimum required length.
Refer here for more details.
</td>
</tr>
<tr>
<td>
MaxLength

</td>
<td>
Specifies the maximum required length.
Refer here for more details.
</td>
</tr>
<tr>
<td>
Required

</td>
<td>
Specifies data field value is required.
Refer here for more details.
</td>
</tr>
<tr>
<td>
RegularExpression

</td>
<td>
Specified value must match the specific pattern.
Refer here for more details.
</td>
</tr>
<tr>
<td>
Range

</td>
<td>
Specifies the maximum and minimum value.
Refer here for more details.
</td>
</tr>
</table>

## Bindable Attribute

It specifies whether the field should be auto generated or not. Refer here for more details.

## Editable Attribute

It specifies data field is editable or not. Refer here for more details. Refer here for more details.

## ReadOnly Attribute

It specifies data field is read only or not. Refer here for more details. Refer here for more details.

## EnumDataType Attribute

It specifies enum type for data field. Refer here for more details.

## DataType Attribute

It specifies data type for the field.
Supported data types - Text, MultilineText, Date, DateTime, Time, Currency.
Refer here for more details.

## CustomDataType Attribute

Percent data type is supported. Refer here for more details.

### DisplayOptions Attribute

<table>
<tr>
<th>Property</th>
<th>Details</th>
</tr>
<tr>
<td>
RowSpan
</td>
<td>
Specifies the row span for the data form item.
Refer here for more details.
</td>
</tr>
<tr>
<td>
ColumnSpan
</td>
<td>
Specifies the column span for the data form item.
Refer here for more details.
</td>
</tr>
<tr>
<td>
ValidMessage
</td>
<td>
Specifies positive message to be shown when validation is passed. Refer here for more details.
</td>
</tr>
<tr>
<td>
ImageSource
</td>
<td>
Specifies the image source for loading image instead of label.
Refer here for more details.
</td>
</tr>
<tr>
<td>
ShowLabel
</td>
<td>
Specifies whether label should be visible or not.
Refer here for more details.
</td>
</tr>
</table>

### ConverterAttribute

<table>
<tr>
<th>Property</th>
<th>Details</th>
</tr>
<tr>
<td>
ConverterType
</td>
<td>
Specifies Converter type. It is used to convert the original value in different format or as different value.
Refer here for more details.
</td>
</tr>
</table>

### DateRange Attribute

<table>
<tr>
<th>Property</th>
<th>Details</th>
</tr>
<tr>
<td>
MinYear
</td>
<td>
Specifies required minimum year
</td>
</tr>
<tr>
<td>
MinMonth
</td>
<td>
Specifies required minimum month
</td>
</tr>
<tr>
<td>
MinDay
</td>
<td>
Specifies required minimum day
</td>
</tr>
<tr>
<td>
MaxYear
</td>
<td>
Specifies required maximum year
</td>
</tr>
<tr>
<td>
MaxMonth
</td>
<td>
Specifies required maximum month
</td>
</tr>
<tr>
<td>
MaxDay
</td>
<td>
Specifies required maximum day
</td>
</tr>
</table>

Refer here for more details.
