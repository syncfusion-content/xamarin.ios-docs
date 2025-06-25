---
layout : post
title : Multiple Selection in Syncfusion® SfAutoComplete control for Xamarin.iOS
description : Learn how to select multiple items in SfAutoComplete
platform : xamarin.ios
control : AutoComplete
documentation : ug
---

# Multiple Selection

Select multiple items from a suggestion list. There are two ways to perform multiple selection in AutoComplete:

* Token Representation

* Delimiter

## Token Representation

Selected items will be displayed with a customizable token representation, and users can remove each tokenized item using the close button.

{% tabs %}

{% highlight C# %}

countryAutoComplete.MultiSelectMode=MultiSelectMode.Token;
countryAutoComplete.TokensWrapMode=TokensWrapMode.Wrap;

{% endhighlight %}

{% endtabs %}

### Wrap Mode of Token

The selected items can be displayed as tokens inside SfAutoComplete in two ways:

* **Wrap** - When `TokensWrapMode` is set to `Wrap`, the selected items will wrap to the next line of the SfAutoComplete.
* **None** - When `TokensWrapMode` is set to `None`, the selected items will be arranged in horizontal orientation.

{% tabs %}

{% highlight C# %}

//Create instance for SfAutoComplete

SfAutoComplete autoComplete;
public MultiSelection()
{
//autoComplete
autoComplete = new SfAutoComplete();
autoComplete.MultiSelectMode = MultiSelectMode.Token;

// Set TokesWrapMode into Wrap

autoComplete.TokensWrapMode = TokensWrapMode.Wrap;
autoComplete.DataSource = new ContactsInfoCollection().GetContactDetails();
autoComplete.DisplayMemberPath = (NSString)"ContactName";
autoComplete.ImageMemberPath = "ContactImage";
autoComplete.ItemHeight = 60;
autoComplete.SuggestionMode = SFAutoCompleteSuggestionMode.SFAutoCompleteSuggestionModeStartsWith;
autoComplete.DropDownItemChanged += NativeAutoComplete_DropDownItemChanged;
this.AddSubview(autoComplete);
}

UIView NativeAutoComplete_DropDownItemChanged(object sender, DropDownItemEventArgs e)
{
UIView parentView = new UIView();
SfAutoComplete auto = (sender as SfAutoComplete);
parentView.Frame = new CGRect(0, 0, auto.Bounds.Width, auto.ItemHeight);
UIImageView imageView = new UIImageView();
imageView.Frame = new CGRect(5, 5, 50, auto.ItemHeight - 10);
UILabel resultLabel = new UILabel();
resultLabel.Frame = new CGRect(60, auto.ItemHeight / 2, auto.Bounds.Width - 65, auto.ItemHeight / 2 - 5);
resultLabel.Font = UIFont.FromName("Helvetica", 12f);
resultLabel.TextAlignment = UITextAlignment.Left;
var item = auto.DataSource.ElementAt((int)e.Index);
var selectedObject = (item as ContactsInfo);

imageView.Image = new UIImage(selectedObject.ContactImage);
resultLabel.Text = selectedObject.ContactName;

parentView.AddSubview(imageView);
parentView.AddSubview(resultLabel);

e.View = parentView;

return e.View;
}

public override void LayoutSubviews()
{
foreach (var view in this.Subviews)
{
view.Frame = Bounds;

toAutoComplete.Frame = new CGRect(50, 60, view.Frame.Width - 60, 40);

}
}
}
public class ContactsInfo
{

private string contactName;
private string image;

public ContactsInfo()
{

}

public string ContactName
{
get { return this.contactName; }
set
{
this.contactName = value;

}
}

public string ContactImage
{
get { return this.image; }
set
{
this.image = value;
}
}
}
public class ContactsInfoCollection
{

private Random random = new Random();

public ContactsInfoCollection()
{

}
public ObservableCollection<ContactsInfo> GetContactDetails()
{
ObservableCollection<ContactsInfo> customerDetails = new ObservableCollection<ContactsInfo>();

for (int i = 0; i < CustomerNames2.Count(); i++)
{
var details = new ContactsInfo()
{
ContactName = CustomerNames2[i],
ContactImage = "b" + (i % 14) + ".png",
};
customerDetails.Add(details);
if (i < 23)
{
details = new ContactsInfo()
{
ContactName = CustomerNames1[i],
ContactImage = "a" + (i % 6) + ".png",
};
customerDetails.Add(details);
}
}
return customerDetails;
}

string[] CustomerNames1 = new string[]
{
"James",
"Victoria",
"John",
"James",
"Jacob",
"Joy",
};

string[] CustomerNames2 = new string[]
{
"Clara",
"Irene",
"Ellie",
"Gabriella",
"Nora",
};
}

}

{% endhighlight %}

{% endtabs %}

![](images/TokenRepresentationWrap.png)

### Token Customization

Tokens can be customized in various ways using the following properties:
* **TextColor** - Sets the color of the text inside the token.
* **FontSize** - Sets the size of the font inside the token.
* **FontFamily** - Sets the font family for the text inside the token.
* **BackgroundColor** - Sets the background color of the token.
* **SelectedBackgroundColor** - Sets the background color of the token when it is selected.
* **IsCloseButtonVisible** - Enables and disables the close button inside the token.
* **DeleteButtonColor** - Sets the color of the close button inside the token.
* **CornerRadius** - Sets the corner radius for the token.

{% tabs %}

{% highlight C# %}

// Token Customization

TokenSettings token = new TokenSettings();
token.FontSize = 16;
token.BackgroundColor = Color.FromHex("#66ccff");
token.TextColor = Color.White;
token.SelectedBackgroundColor = Color.FromHex("#ffffe0");
token.DeleteButtonColor = Color.Brown;
token.FontFamily= "Times New Roman";
token.IsCloseButtonVisible = true;
token.CornerRadius = 3;
autoComplete.TokenSettings = token;

{% endhighlight %}

{% endtabs %}


![](images/Token_iOS.png)

## Delimiter

When selecting multiple items, the selected items can be separated with a desired character specified as a delimiter. You can set the delimiter character using the `Delimiter` property.

{% tabs %}

{% highlight C# %}

countryAutoComplete.MultiSelectMode=MultiSelectMode.Delimiter;
countryAutoComplete.Delimiter="#";

{% endhighlight %}

{% endtabs %}

![](images/Delimiter.png)

