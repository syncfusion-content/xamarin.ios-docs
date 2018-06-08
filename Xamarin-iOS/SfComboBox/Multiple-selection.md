---
layout : post
title : Multi Selection in Syncfusion SfComboBox control for Xamarin.iOS
description :  Learn how to select multiple items in SfComboBox
platform : Xamarin.iOS 
control : ComboBox
documentation : ug
---

# Multiple Selection

You can select multiple items from a drop-down list by following two ways. 
 
* Token representation

* Delimiter

## Token representation

Selected items will be displayed with a customizable token representation and the users can remove each tokenized item with the close button. 

{% tabs %}

{% highlight C# %}

sfCombo.MultiSelectMode = MultiSelectMode.Token; 

{% endhighlight %}

{% endtabs %}

### Wrap mode of token

The selected item can be displayed as token inside the combo box in the following two ways.

* `Wrap` - When the `TokensWrapMode` is set to `Wrap` the selected items will be wrapped to the next line of the combo box.

* `None` - When the `TokensWrapMode` is set to `None` the selected item will be wrapped in horizontal orientation.

{% tabs %}

{% highlight C# %}

//Create instance for SfComboBox

{ 
SfComboBox sfCombo = new SfComboBox(); 
sfCombo.IsEditable = true; 
sfCombo.SuggestionMode = SuggestionMode.StartsWith; 
sfCombo.Frame = new CoreGraphics.CGRect(25,100, UIScreen.MainScreen.Bounds.Width-50, 100); 
sfCombo.MultiSelectMode = MultiSelectMode.Token; 
sfCombo.TokensWrapMode = TokensWrapMode.Wrap; 
sfCombo.ItemHeight = 60; 
this.GetStudentData(); 
sfCombo.DisplayMemberPath = (NSString)"Name"; 
sfCombo.ImageMemberPath = "Image"; 
sfCombo.DataSource = StudentDetails; 
sfCombo.DropDownItemChanged += SfCombo_DropDownItemChanged; 
sfCombo.MaxDropDownHeight = 250; 
} 

string[] StudentNames = new string[] 
{ 
    "Alan", 
    "Alexander", 
    "Arthur", 
    "Amilia", 
    "Benjamin", 
    "Bobby", 
    "Carter", 
    "Caleb", 
    "Clara", 
    "Elena", 
    "Evelyn", 
    "Elizabeth", 
    "Freddie", 
    "Gracie", 
    "James", 
    "John", 
    "Joseph", 
    "Jacob", 
    "Victoria", 
    "Joy", 
    "Zachary", 
    "Ivy", 
    "Zara", 
}; 

void GetStudentData() 
{ 
    StudentDetails = new ObservableCollection<Student>(); 
    for (int i = 1; i <= StudentNames.Length; i++) 
    { 
        StudentDetails.Add(new Student(StudentNames[i-1], "Image"+i+".png")); 
    } 
} 

UIView SfCombo_DropDownItemChanged(object sender, DropDownItemEventArgs e) 
{ 
    UIView parentView = new UIView(); 
    SfComboBox auto = (sender as SfComboBox); 
    parentView.Frame = new CGRect(0, 0, auto.Bounds.Width, auto.ItemHeight); 
    UIImageView imageView = new UIImageView(); 
    imageView.Frame = new CGRect(5, 5, 50, auto.ItemHeight - 10); 
    UILabel resultLabel = new UILabel(); 
    resultLabel.Frame = new CGRect(60, auto.ItemHeight / 4, auto.Bounds.Width - 65, auto.ItemHeight / 2 - 5); 
    resultLabel.Font = UIFont.FromName("Helvetica", 20f); 
    resultLabel.TextAlignment = UITextAlignment.Left; 
    var item = auto.DataSource.ElementAt((int)e.Index); 
    var selectedObject = (item as Student); 
    imageView.Image = new UIImage(selectedObject.Image); 
    resultLabel.Text = selectedObject.Name; 
    parentView.AddSubview(imageView); 
    parentView.AddSubview(resultLabel); 
    e.View = parentView; 
    return e.View; 
} 
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

private string image; 
public string Image 
{ 
get 
{ 
    return image; 
} 

set 
{ 
    image = value; 
} 
} 

public Student(string name, string image) 
{ 
    this.Name = name; 
    this.Image = image; 
} 
} 

{% endhighlight %}

{% endtabs %}

![](images/TokenRepresentationWrap.png)

### Token customization

Token can be customized in the following ways.

* `TextColor` - Sets the color of the text inside the token.

* `FontSize` - Sets the size of the font inside the token.

* `FontFamily` - Sets the font family for the text inside the token.

* `BackgroundColor` - Sets the background color of the token.

* `SelectedBackgroundColor` - Sets the background color of the token when it is selected.

* `IsCloseButtonVisible` - Enables and disables the close button inside the combo Box.

* `DeleteButtonColor` - Sets the color of the close button inside the combo box.

* `CornerRadius` - Sets the corner radius for the token.

{% tabs %}

{% highlight C# %}

// Token Customization

TokenSettings token = new TokenSettings(); 
token.FontSize = 16; 
token.BackgroundColor = UIColor.FromRGB(102,204,255); 
token.TextColor = UIColor.White; 
token.SelectedBackgroundColor = UIColor.FromRGB(255,255,224); 
token.DeleteButtonColor = UIColor.Black; 
token.FontFamily = "Times New Roman"; 
token.IsCloseButtonVisible = true; 
token.CornerRadius = 10; 
sfCombo.TokenSettings = token;

{% endhighlight %}

{% endtabs %}


![](images/Token_iOS.png)

## Delimiter

When selecting the multiple items, the selected items can be divided with a desired character given for a delimiter. You can set delimiter character using the `Delimiter` property.

{% tabs %}

{% highlight C# %}

sfCombo.MultiSelectMode = MultiSelectMode.Delimiter; 
sfCombo.Delimiter="#";

{% endhighlight %}

{% endtabs %}

![](images/Delimiter.png)

