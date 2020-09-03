---
layout: post
title: Data binding in Syncfusion RadialMenu control for Xamarin.iOS
description: Learn how to perform DataBinding, adding outer rim items, nested items, duration of the animation, and other property usages in SfRadialMenu.
platform: Xamarin.iOS
control: SfRadialMenu
documentation: ug
---

# Populating Items

This section explains how to populate items using the radial menu item and item source.

## Through radial menu items

By passing a collection of [SfRadialMenuItem](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html), you can get the view of the `SfRadialMenu` control. The radial menu item class provides various options such as custom views, font icons, and images to customize the items. You can also add radial menu items by hierarchy.

### Adding outer rim items of radial menu

The following code sample shows how to add the outer rim items of the radial menu.

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
            sfRadialMenu.CenterButtonText = "\uE713";
            sfRadialMenu.CenterButtonBackText = "\uE72B";
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);//
            for (int i = 0; i < 5; i++)
            {
                //Adding Items
                SfRadialMenuItem item = new SfRadialMenuItem() { IconFont = UIFont.FromName("Sample", 20), FontIcon = layer[i] };
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

### Adding nested items of a radial menu

You can populate the nested levels of items within a menu to group similar actions. For example, you can group the clipboard operations by adding clipboard as the main menu and cut, copy, and paste as its children.

The following code sample shows how to add the nested items of the radial menu.

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
            sfRadialMenu.CenterButtonText = "\uE713";
            sfRadialMenu.CenterButtonBackText = "\uE72B";
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);//
            for (int i = 0; i < 5; i++)
            {
                //Adding Items
                SfRadialMenuItem item = new SfRadialMenuItem() { IconFont = UIFont.FromName("Sample", 20), FontIcon = layer[i] };
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

## Animation duration

The duration of animation in the radial menu can be changed using the [AnimationDuration](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_AnimationDuration) property. It is used to change the speed of opening and closing of the radial menu.

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
            sfRadialMenu.CenterButtonText = "\uE713";
            sfRadialMenu.CenterButtonBackText = "\uE72B";
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            sfRadialMenu.AnimationDuration = 1000;
            for (int i = 0; i < 5; i++)
            {
                //Adding Items
                SfRadialMenuItem item = new SfRadialMenuItem() { IconFont = UIFont.FromName("Sample", 20), FontIcon = layer[i] };
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

## IsOpen

The [IsOpen](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_IsOpen) property indicates whether the radial menu is in an open or closed state.

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
            sfRadialMenu.CenterButtonText = "\uE713";
            sfRadialMenu.CenterButtonBackText = "\uE72B";
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            for (int i = 0; i < 5; i++)
            {
                //Adding Items
                SfRadialMenuItem item = new SfRadialMenuItem() { IconFont = UIFont.FromName("Sample", 20), FontIcon = layer[i] };
                for (int j = 0; j < 4; j++)
                {
                    SfRadialMenuItem item1 = new SfRadialMenuItem() { IconFont = UIFont.FromName("Sample", 20), FontIcon = outerLayer[j] };
                    item.Items.Add(item1);
                }
                sfRadialMenu.Items.Add(item);
            }

            sfRadialMenu.IsOpen = true;
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

![SfRadialMenu with Items Open](images/CenterButtonText.png)

## Selection color of the radial menu

The Selection color of an item can be changed using the [SelectionColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_SelectionColor) property of the radial menu.

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
            sfRadialMenu.CenterButtonText = "\uE713";
            sfRadialMenu.CenterButtonBackText = "\uE72B";
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            sfRadialMenu.SelectionColor = UIColor.FromRGB(232, 25, 156);
            for (int i = 0; i < 5; i++)
            {
                //Adding Items
                SfRadialMenuItem item = new SfRadialMenuItem() { IconFont = UIFont.FromName("Sample", 20), FontIcon = layer[i] };
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

![SelectionColor](images/SelectionColor.png)

## Separator thickness and color in the radial menu

The thickness of the strip between the two items can be changed using the [SeparatorThickness](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_SeparatorThickness) property, and the color of the strip can be changed using the [SeparatorColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_SeparatorColor) property.

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
            sfRadialMenu.CenterButtonText = "\uE713";
            sfRadialMenu.CenterButtonBackText = "\uE72B";
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            sfRadialMenu.SeparatorThickness = 10;
            sfRadialMenu.SeparatorColor = UIColor.Black;
            for (int i = 0; i < 5; i++)
            {
                //Adding Items
                SfRadialMenuItem item = new SfRadialMenuItem() { IconFont = UIFont.FromName("Sample", 20), FontIcon = layer[i] };
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

![SeparatorThickness](images/SeparatorThickness.png)

## Rim color and rim radius in radial menu

The radius of the rim can be changed using the [RimRadius](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_RimRadius) property, and the color of the rim can be changed using the [RimColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_RimColor) property.

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
            sfRadialMenu.CenterButtonText = "\uE713";
            sfRadialMenu.CenterButtonBackText = "\uE72B";
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            sfRadialMenu.RimRadius = 100;
            sfRadialMenu.RimColor = UIColor.FromRGB(240, 20, 40);
            for (int i = 0; i < 5; i++)
            {
                //Adding Items
                SfRadialMenuItem item = new SfRadialMenuItem() { IconFont = UIFont.FromName("Sample", 20), FontIcon = layer[i] };
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

![RimRadius](images/RimRadius.png)
