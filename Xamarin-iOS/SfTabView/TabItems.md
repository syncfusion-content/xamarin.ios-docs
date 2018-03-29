---
layout: post
title: Tab Items
description: About Tab items in TabView control for Xamarin.iOS platform
platform: Xamarin.iOS
control: TabView
documentation: ug
---

# Tab Items

Tab items can be configured in tab view through the Items property of `SfTabView`, where it holds collection of `SfTabItem` through `TabItemsCollection`


{% tabs %}

{% highlight C# %}

        var tabItems = new TabItemCollection
        {
            new SfTabItem()
            {
                Title = "Calls",
                Content = allContactsUIView
            },
            new SfTabItem()
            {
                Title = "Favorites",
                Content = favoritesUIView
            },
            new SfTabItem()
            {
                Title = "Contacts",
                Content = contactsUIView
            }
        };

        tabView.Items = tabItems;
            

{% endhighlight %}

{% endtabs %}

## Share the header space equally

In order to share the header space equally for the , we can set the number of tabs which can be distributed in the available space though `VisibleHeaderCount` of SfTabView.

{% tabs %}

{% highlight C# %}

tabView.VisibleHeaderCount = 3;

{% endhighlight %}

{% endtabs %}


