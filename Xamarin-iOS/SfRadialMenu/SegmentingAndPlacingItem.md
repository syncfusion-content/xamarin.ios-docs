---
layout: post
title: Segmenting items in Syncfusion RadialMenu control for Xamarin.Android
description: How to Segment the rim and place the items using the layout types in SfRadialMenu control in Xamarin.Android.
platform: Xamarin.Android
control: SfRadialMenu
documentation: ug
---

# Layout Types

The following two different [LayoutTypes]](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS~Syncfusion.SfRadialMenu.iOS.SfRadialMenu~LayoutType.html) available available in the radial menu are:

* Default
* Custom

Both the layout types divide the available space equally among all the children in the circular panel.

## Default

The number of segments in the panel is determined by the children count in a level. As the segment count in each hierarchical level differs, radial menu items are arranged in a sequential order as added to the radial menu.

{% tabs %}
{% highlight c# %}

using Foundation;
using Syncfusion.SfRadialMenu.iOS;
using System;
using UIKit;

namespace RadialMenuNative
{
    public partial class ViewController : UIViewController
    {
        public ViewController(IntPtr handle) : base(handle)
        {
        }

        public override void ViewDidLoad()
        {
            base.ViewDidLoad();
            // Perform any additional setup after loading the view, typically from a nib.
            string[] layer = new string[] { "\uE9AB", "\uEB07", "\uEB73", "\uEBAE", "\uECD5", "\uEFAB" };
            string[] outerLayer = new string[] { "\uEC3B", "\uEC3A", "\uEC39", "\uEC38", "\uEC37" };
            SfRadialMenu sfRadialMenu = new SfRadialMenu();
            sfRadialMenu.CenterButtonText = "\uE9A5";
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            sfRadialMenu.LayoutType = SfRadialMenuLayoutType.Default;
            for (int i = 0; i < 5; i++)
            {
                //Adding Items
                SfRadialMenuItem item = new SfRadialMenuItem() { IconFont = UIFont.FromName("Sample", 20), FontIcon = layer[i] };
                //Adding Sub items
                for (int j = 0; j < 4; j++)
                {
                    SfRadialMenuItem item1 = new SfRadialMenuItem() { IconFont = UIFont.FromName("Sample", 20), FontIcon = outerLayer[j] };
                    item.Items.Add(item1);
                }
                sfRadialMenu.Items.Add(item);
            }

            sfRadialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center;
            this.View.AddSubview(sfRadialMenu);
        }

        public override void DidReceiveMemoryWarning()
        {
            base.DidReceiveMemoryWarning();
            // Release any cached data, images, etc that aren't in use.
        }
    }
}

{% endhighlight %}
{% endtabs %}

## Custom

The number of segments in the panel is determined using the [VisibleItemCount](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS~Syncfusion.SfRadialMenu.iOS.SfRadialMenu~VisibleItemCount.html) property. As the segment count in all the hierarchical levels is the same, radial menu items are arranged in any order based on the [SlottedIndex](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS~Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem~SlottedIndex.html) property.

{% tabs %}
{% highlight c# %}

using Foundation;
using Syncfusion.SfRadialMenu.iOS;
using System;
using UIKit;

namespace RadialMenuNative
{
    public partial class ViewController : UIViewController
    {
        public ViewController(IntPtr handle) : base(handle)
        {
        }

        public override void ViewDidLoad()
        {
            base.ViewDidLoad();
            // Perform any additional setup after loading the view, typically from a nib.
            string[] layer = new string[] { "\uE9AB", "\uEB07", "\uEB73", "\uEBAE", "\uECD5", "\uEFAB" };
            string[] outerLayer = new string[] { "\uEC3B", "\uEC3A", "\uEC39", "\uEC38", "\uEC37" };
            SfRadialMenu sfRadialMenu = new SfRadialMenu();
            sfRadialMenu.CenterButtonText = "\uE9A5";
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            sfRadialMenu.LayoutType = SfRadialMenuLayoutType.Custom;
            for (int i = 0; i < 5; i++)
            {
                //Adding Items
                SfRadialMenuItem item = new SfRadialMenuItem() { IconFont = UIFont.FromName("Sample", 20), FontIcon = layer[i] };
                //Adding Sub items
                for (int j = 0; j < 4; j++)
                {
                    SfRadialMenuItem item1 = new SfRadialMenuItem() { IconFont = UIFont.FromName("Sample", 20), FontIcon = outerLayer[j] };
                    item.Items.Add(item1);
                }
                sfRadialMenu.Items.Add(item);
            }

            sfRadialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center;
            this.View.AddSubview(sfRadialMenu);
        }

        public override void DidReceiveMemoryWarning()
        {
            base.DidReceiveMemoryWarning();
            // Release any cached data, images, etc that aren't in use.
        }
    }
}

{% endhighlight %}
{% endtabs %}

### VisibleItemCount

The [VisibleItemCount](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS~Syncfusion.SfRadialMenu.iOS.SfRadialMenu~VisibleItemCount.html) property is used to specify the number of segments available in the circular panel. When the children count is greater than the value given in the VisibleSegmentsCount property, the overflowing children are not arranged in the panel. When children count is lesser than the VisibleSegmentsCount property, the remaining segments are left free.

{% tabs %}
{% highlight c# %}

using Foundation;
using Syncfusion.SfRadialMenu.iOS;
using System;
using UIKit;

namespace RadialMenuNative
{
    public partial class ViewController : UIViewController
    {
        public ViewController(IntPtr handle) : base(handle)
        {
        }

        public override void ViewDidLoad()
        {
            base.ViewDidLoad();
            // Perform any additional setup after loading the view, typically from a nib.
            string[] layer = new string[] { "\uE9AB", "\uEB07", "\uEB73", "\uEBAE", "\uECD5", "\uEFAB" };
            string[] outerLayer = new string[] { "\uEC3B", "\uEC3A", "\uEC39", "\uEC38", "\uEC37" };
            SfRadialMenu sfRadialMenu = new SfRadialMenu();
            sfRadialMenu.CenterButtonText = "\uE9A5";
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            sfRadialMenu.LayoutType = SfRadialMenuLayoutType.Custom;
            sfRadialMenu.VisibleItemCount = 2;
            for (int i = 0; i < 5; i++)
            {
                //Adding Items
                SfRadialMenuItem item = new SfRadialMenuItem() { IconFont = UIFont.FromName("Sample", 20), FontIcon = layer[i] };
                //Adding Sub items
                for (int j = 0; j < 4; j++)
                {
                    SfRadialMenuItem item1 = new SfRadialMenuItem() { IconFont = UIFont.FromName("Sample", 20), FontIcon = outerLayer[j] };
                    item.Items.Add(item1);
                }
                sfRadialMenu.Items.Add(item);
            }

            sfRadialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center;
            this.View.AddSubview(sfRadialMenu);
        }

        public override void DidReceiveMemoryWarning()
        {
            base.DidReceiveMemoryWarning();
            // Release any cached data, images, etc that aren't in use.
        }
    }
}

{% endhighlight %}
{% endtabs %}


### SlottedIndex

The [SlottedIndex](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS~Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem~SlottedIndex.html) property is used to specify the index of the radial menu item in the circular panel. Based on the index, the radial menu items are inserted in the segment. When the SlottedIndex is not specified for a RadialMenuItem, the menu item is arranged in the next available free segment.

## Code snippets for VisibleItemCount and SegmentIndex

{% tabs %}
{% highlight c#%}

using Foundation;
using Syncfusion.SfRadialMenu.iOS;
using System;
using UIKit;

namespace RadialMenuNative
{
    public partial class ViewController : UIViewController
    {
        public ViewController(IntPtr handle) : base(handle)
        {
        }

        public override void ViewDidLoad()
        {
            base.ViewDidLoad();
            // Perform any additional setup after loading the view, typically from a nib.
            string[] layer = new string[] { "\uE9AB", "\uEB07", "\uEB73", "\uEBAE", "\uECD5", "\uEFAB" };
            int[] slottedIndex = { 1, 0, 2 };
            string[] outerLayer = { "\uEC3B", "\uEC3A", "\uEC39", "\uEC38", "\uEC37" };
            SfRadialMenu sfRadialMenu = new SfRadialMenu();
            sfRadialMenu.CenterButtonText = "\uE9A5";
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            sfRadialMenu.LayoutType = SfRadialMenuLayoutType.Custom;
            sfRadialMenu.VisibleItemCount = 3;
            for (int i=0; i< sfRadialMenu.VisibleItemCount; i++)
            {
                //Adding Items
                SfRadialMenuItem item = new SfRadialMenuItem() { IconFont = UIFont.FromName("Sample", 20), FontIcon = layer[i], SlottedIndex = slottedIndex[i] };
                sfRadialMenu.Items.Add(item);
            }

            sfRadialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center;
            this.View.AddSubview(sfRadialMenu);
        }

        public override void DidReceiveMemoryWarning()
        {
            base.DidReceiveMemoryWarning();
            // Release any cached data, images, etc that aren't in use.
        }
    }
}
	
{% endhighlight %}
{% endtabs %}

### StartAngle

The `StartAngle` property is used to set the angle from which the arrangement of radial menu items should start.

{% tabs %}
{% highlight c#%}

using Foundation;
using Syncfusion.SfRadialMenu.iOS;
using System;
using UIKit;

namespace RadialMenuNative
{
    public partial class ViewController : UIViewController
    {
        public ViewController(IntPtr handle) : base(handle)
        {
        }

        public override void ViewDidLoad()
        {
            base.ViewDidLoad();
            // Perform any additional setup after loading the view, typically from a nib.
            string[] layer = new string[] { "\uE9AB", "\uEB07", "\uEB73", "\uEBAE", "\uECD5", "\uEFAB" };
            int[] slottedIndex = { 1, 0, 2 };
            string[] outerLayer = { "\uEC3B", "\uEC3A", "\uEC39", "\uEC38", "\uEC37" };
            SfRadialMenu sfRadialMenu = new SfRadialMenu();
            sfRadialMenu.CenterButtonText = "\uE9A5";
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            sfRadialMenu.StartAngle = 90;
            //Adding Main menu Items

            string[] menuItems = new string[] { "\uE701", "\uE702", "\uEA8F", "\uE793", "\uE83F", "\uE7E8" };

            for (int i = 0; i < 6; i++)
            {
                SfRadialMenuItem mainMenuItems = new SfRadialMenuItem();
                mainMenuItems.FontIcon = menuItems[i];
                mainMenuItems.IconFont = UIFont.FromName("Sample", 30);
                sfRadialMenu.Items.Add(mainMenuItems);
            }

            sfRadialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center;
            this.View.AddSubview(sfRadialMenu);
        }

        public override void DidReceiveMemoryWarning()
        {
            base.DidReceiveMemoryWarning();
            // Release any cached data, images, etc that aren't in use.
        }
    }
}

{% endhighlight %}
{% endtabs %}

![images](images/StartAngle.png)