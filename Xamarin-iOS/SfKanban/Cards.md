---
layout: post
title: Kanban Cards Customization
description: Kanban Cards
platform: xamarin.ios
control: Kanban
documentation: ug
---

# Cards

The default elements of a card can be customized using the below properties of [`KanbanModel`](http://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanModel.html).

* [`Title`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanModel.html#Syncfusion_SfKanban_iOS_KanbanModel_Title)         - Used to set the title of a card.
* [`ImageURL`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanModel.html#Syncfusion_SfKanban_iOS_KanbanModel_ImageURL)      - Used to set the image URL of a card. The image will be displayed at right side in default card template.
* [`Category`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanModel.html#Syncfusion_SfKanban_iOS_KanbanModel_Category)      - Used to set the category of a card. Based on the category the cards will be added to the respective columns. 
* [`Description`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanModel.html#Syncfusion_SfKanban_iOS_KanbanModel_Description)   - Used to set the description text of a card.
* [`ColorKey`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanModel.html#Syncfusion_SfKanban_iOS_KanbanModel_ColorKey)      - Used to specify the indicator color key. The [`Color`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanColorMapping.html#Syncfusion_SfKanban_iOS_KanbanColorMapping_Color) value of the corresponding [`Key`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanColorMapping.html#Syncfusion_SfKanban_iOS_KanbanColorMapping_Key) should be added in [`IndicatorColorPalette`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html#Syncfusion_SfKanban_iOS_SfKanban_IndicatorColorPalette) collection of [`SfKanban`](http://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html).
* [`Tags`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanModel.html#Syncfusion_SfKanban_iOS_KanbanModel_Tags)          - Used to specify the tags of a card. The tags will be displayed at bottom in default card template.
* [`ID`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanModel.html#Syncfusion_SfKanban_iOS_KanbanModel_ID)            - Used to set the ID of a card.

{% highlight C# %}

new KanbanModel()
{
    ID = 1,
    Title = "iOS - 1002",
    ImageURL = "Image1.png",
    Category = "Open",
    Description = "Analyze customer requirements",
    ColorKey = "Red",
    Tags = new string[] { "Incident", "Customer" }
});

{% endhighlight %}

Following code snippet is used to define the colors for each key.

{% highlight C# %}

List<KanbanColorMapping> colorModels = new List<KanbanColorMapping>();
colorModels.Add(new KanbanColorMapping("Green", Color.Green));
colorModels.Add(new KanbanColorMapping("Red", Color.Red));
colorModels.Add(new KanbanColorMapping("Aqua", Color.Aqua));
colorModels.Add(new KanbanColorMapping("Blue", Color.Blue));
kanban.IndicatorColorPalette = colorModels;

{% endhighlight %}

![Customization of cards in Xamarin.iOS Kanban](Kanban_images/CardCustomization.png)

## Template

You can replace the entire card template with your own design using [`SfKanban.KanbanDelegate`](http://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDelegate.html) 's [`GetItemViewCell`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDelegate.html#Syncfusion_SfKanban_iOS_KanbanDelegate_GetItemViewCell) override method . The following code snippet and screenshot illustrates this.

{% highlight C# %}

public class CustomDelegate : KanbanDelegate
{
	public override UIView GetItemViewCell(KanbanColumn column, object data, int position)
	{
	    KanbanModel model = (KanbanModel)data;

		UIView cell = new UIView();
		cell.BackgroundColor = UIColor.Gray;

		UILabel title = new UILabel();
		title.TextColor = UIColor.White;
		title.Text = model.Title;
		title.Font = UIFont.SystemFontOfSize(20);

		UITextView desc = new UITextView();
		desc.TextColor = UIColor.White;
		desc.Text = model.Description;
		desc.BackgroundColor = UIColor.Clear;
		desc.UserInteractionEnabled = false;
		desc.Font = UIFont.SystemFontOfSize(16);

		UIImageView avatar = new UIImageView();
		avatar.Image = UIImage.FromFile(model.ImageURL);

		title.Frame = new CoreGraphics.CGRect(10, 10, 250, 25);
		desc.Frame = new CoreGraphics.CGRect(2, 40, 170, 75);
		avatar.Frame = new CoreGraphics.CGRect(185, 45, 60, 60);

		cell.AddSubview(title);
		cell.AddSubview(desc);
		cell.AddSubview(avatar);

		return cell;
	}
}	

public partial class ViewController : UIViewController
{
	private SfKanban kanban;

	public override void ViewDidLoad()
	{
		base.ViewDidLoad();

		kanban = new SfKanban();
		kanban.Delegate = new CustomDelegate();
		kanban.ColumnWidth = 280;
	}
}

{% endhighlight %}

![Template support for cards in Xamarin.iOS Kanban](Kanban_images/CardTemplate.png)


