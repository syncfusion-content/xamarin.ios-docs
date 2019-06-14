---
layout: post
title: Adding custom items in Syncfusion Rating control for Xamarin.iOS
description: Learn how to add the Custom Items in rating control
platform: Xamarin.iOS
control: Rating
documentation: ug
---

# Custom Views

SfRating Items control provides support to add custom views.

## Add SfRating Items

Add the SfRating Items control with a required optimal name by using the included namespace.

{% highlight C# %}

SfRating rating= new SfRating(); 

SfRatingItem item = new SfRatingItem(rating);

{% endhighlight %}

## Set Selected View
 
The `SelectedView` property is used to apply the given SelectedView to selected rating item.

{% highlight C# %}

    UIImageView angrySelected = new UIImageView();
    angrySelected.Image = UIImage.FromBundle("Angry_selected.png");
    ratingItem.SelectedView = angrySelected;

{% endhighlight %}

## Set UnSelected View
 
The `UnSelectedView` property is used to apply the given UnSelectedView to unselected rating items.

{% highlight C# %}

    UIImageView angryUnselected = new UIImageView();
    angryUnselected.Image=UIImage.FromBundle("Angry_Unselected.png");
    ratingItem.UnSelectedView = angryUnselected;    

{% endhighlight %}

## Add Items

The `Items` property is used to hold the collection of SfRatingItem. 

N> SfRatingItem keeps both selected and unselected view respectively.

{% highlight C# %}

	NSMutableArray collection = new NSMutableArray();
	collection.Add(ratingItem);
	rating.Items = collection;

{% endhighlight %}

## Enable Custom Items

When `EnableCustomItems` property is enabled, it will display the custom items added in the rating item. 

{% highlight C# %}

    SfRating rating= new SfRating();
    rating.EnableCustomView = true;
    
    SfRatingItem angry = new SfRatingItem(rating);
    UIImageView angrySelected = new UIImageView();
    angrySelected.Image = UIImage.FromBundle("Angry_selected.png");
    angry.SelectedView = angrySelected;
    UIImageView angryUnselected = new UIImageView();
    angryUnselected.Image=UIImage.FromBundle("Angry_Unselected.png");
    angry.UnSelectedView = angryUnselected;

    SfRatingItem unhappy = new SfRatingItem(rating);
    UIImageView unhappySelected = new UIImageView();
    unhappySelected.Image = UIImage.FromBundle("UnHappy_selected.png");
    unhappy.SelectedView = unhappySelected;
    UIImageView unhappyUnselected = new UIImageView();
    unhappyUnselected.Image = UIImage.FromBundle("UnHappy_Unselected.png");
    unhappy.UnSelectedView = unhappyUnselected;

    SfRatingItem neutral = new SfRatingItem(rating);
    UIImageView neutralSelected = new UIImageView();
    neutralSelected.Image = UIImage.FromBundle("Neutral_selected.png");
    neutral.SelectedView = neutralSelected;
    UIImageView neutralUnselected = new UIImageView();
    neutralUnselected.Image = UIImage.FromBundle("Neutral_Unselected.png");
    neutral.UnSelectedView = neutralUnselected;

    SfRatingItem happy = new SfRatingItem(rating);
    UIImageView happySelected = new UIImageView();
    happySelected.Image = UIImage.FromBundle("Neutral_selected.png");
    happy.SelectedView = happySelected;
    UIImageView happyUnselected = new UIImageView();
    happyUnselected.Image = UIImage.FromBundle("Neutral_Unselected.png");
    happy.UnSelectedView = happyUnselected;

    SfRatingItem excited = new SfRatingItem(rating);
    UIImageView excitedSelected = new UIImageView();
    excitedSelected.Image = UIImage.FromBundle("Neutral_selected.png");
    excited.SelectedView = excitedSelected;
    UIImageView excitedUnselected = new UIImageView();
    excitedUnselected.Image = UIImage.FromBundle("Neutral_Unselected.png");
    excited.UnSelectedView = excitedUnselected;

    NSMutableArray ratingItemList = new NSMutableArray();
    ratingItemList.Add(angry);
    ratingItemList.Add(unhappy);
    ratingItemList.Add(neutral);
    ratingItemList.Add(happy);
    ratingItemList.Add(excited);
    rating.Items = ratingItemList;

{% endhighlight %}

![Custom rating item](images/CustomviewItems.png)
