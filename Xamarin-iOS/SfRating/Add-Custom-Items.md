---
layout: post
title: Adding Custom Items in Syncfusion® Rating Control for Xamarin.iOS
description: Learn how to add custom items and configure their appearance in Rating control for Xamarin.iOS platform applications
platform: xamarin.ios
control: SfRating
documentation: ug
---

# Custom Views

The SfRating control provides support to add custom views for rating items.

## Add SfRating Items

Add the SfRating control with a required optimal name by using the included namespace.

{% highlight C# %}

SfRating rating= new SfRating(); 

SfRatingItem item = new SfRatingItem(rating);

{% endhighlight %}

## Set Selected View
 
The `SelectedView` property is used to apply the given selected view to the selected rating item.

{% highlight C# %}

    UIImageView angrySelected = new UIImageView();
    angrySelected.Image = UIImage.FromBundle("Angry_selected.png");
    ratingItem.SelectedView = angrySelected;

{% endhighlight %}

## Set UnSelected View
 
The `UnSelectedView` property is used to apply the given unselected view to unselected rating items.

{% highlight C# %}

    UIImageView angryUnselected = new UIImageView();
    angryUnselected.Image=UIImage.FromBundle("Angry_Unselected.png");
    ratingItem.UnSelectedView = angryUnselected;    

{% endhighlight %}

## Add Items

The `Items` property is used to hold the collection of SfRatingItem. 

> **Note:** SfRatingItem keeps both selected and unselected views respectively.

{% highlight C# %}

	NSMutableArray collection = new NSMutableArray();
	collection.Add(ratingItem);
	rating.Items = collection;

{% endhighlight %}

## Enable Custom Items

When the `EnableCustomView` property is enabled, it will display the custom items added in the rating control.

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
