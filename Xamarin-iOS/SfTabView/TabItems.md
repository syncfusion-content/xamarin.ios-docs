---
layout: post
title: Tab Items
description: About Tab items in TabView control for Xamarin.iOS platform
platform: xamarin.ios
control: SfTabView
documentation: ug
---

# Tab Items

Tab items can be configured in TabView through the `Items` property of `SfTabView`, which holds the collection of `SfTabItem` through `TabItemCollection`.


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

## Share the Header Space Equally

To share the header space among the tabs equally, set the number of tabs that can be distributed in the available space through the `VisibleHeaderCount` property of `SfTabView`.

{% tabs %}

{% highlight C# %}

tabView.VisibleHeaderCount = 3;

{% endhighlight %}

{% endtabs %}


