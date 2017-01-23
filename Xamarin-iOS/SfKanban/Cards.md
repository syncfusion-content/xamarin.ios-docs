---
layout: post
title: Kanban Cards Customization
description: Kanban Cards
platform: xamarin.ios
control: Kanban
documentation: ug
---

# Cards

The default elements of a card can be customized using the below properties of ['KanbanModel'](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfkanban/Syncfusion.SfKanban.iOS~Syncfusion.SfKanban.iOS.KanbanModel.html).

* ['Title'](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfkanban/Syncfusion.SfKanban.iOS~Syncfusion.SfKanban.iOS.KanbanModel~Title.html)         - Used to set the title of a card.
* ['ImageURL'](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfkanban/Syncfusion.SfKanban.iOS~Syncfusion.SfKanban.iOS.KanbanModel~ImageURL.html)      - Used to set the image URL of a card. The image will be displayed at right side in default card template.
* ['Category'](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfkanban/Syncfusion.SfKanban.iOS~Syncfusion.SfKanban.iOS.KanbanModel~Category.html)      - Used to set the category of a card. Based on the category the cards will be added to the respective columns. 
* ['Description'](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfkanban/Syncfusion.SfKanban.iOS~Syncfusion.SfKanban.iOS.KanbanModel~Description.html)   - Used to set the description text of a card.
* ['ColorKey'](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfkanban/Syncfusion.SfKanban.iOS~Syncfusion.SfKanban.iOS.KanbanModel~ColorKey.html)      - Used to specify the indicator color key. The color value of the corresponding key should be added in ['ColorModel'](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfkanban/Syncfusion.SfKanban.iOS~Syncfusion.SfKanban.iOS.SfKanban~ColorModel.html) collection of [SfKanban](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfkanban/Syncfusion.SfKanban.iOS~Syncfusion.SfKanban.iOS.SfKanban.html).
* ['Tags'](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfkanban/Syncfusion.SfKanban.iOS~Syncfusion.SfKanban.iOS.KanbanModel~Tags.html)          - Used to specify the tags of a card. The tags will be displayed at bottom in default card template.
* ['ID'](http://help.syncfusion.com/cr/cref_files/xamarin-ios/sfkanban/Syncfusion.SfKanban.iOS~Syncfusion.SfKanban.iOS.KanbanModel~ID.html)            - Used to set the ID of a card.

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

List<KanbanColorMapping> colormodels = new List<KanbanColorMapping>();
colormodels.Add(new KanbanColorMapping("Green", Color.Green));
colormodels.Add(new KanbanColorMapping("Red", Color.Red));
colormodels.Add(new KanbanColorMapping("Aqua", Color.Aqua));
colormodels.Add(new KanbanColorMapping("Blue", Color.Blue));
kanban.IndicatorColorPalette = colormodels;

{% endhighlight %}

![](Kanban_images/CardCustomization.png)

