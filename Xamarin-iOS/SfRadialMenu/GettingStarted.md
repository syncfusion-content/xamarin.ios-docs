---
layout: post
title: Getting Started with Syncfusion® RadialMenu control for Xamarin.iOS
description: A quick tour for new users of Syncfusion® RadialMenu control to get familiar with the control for Xamarin.iOS platform.
platform: xamarin.ios 
control: RadialMenu
documentation: ug
---

# Getting Started

This section explains the steps required to configure the SfRadialMenu control in a real-time scenario and provides a walk-through of some of the customization features available in Xamarin.iOS applications.

## Assembly References
After installing Essential Studio® for Xamarin, you can find all the required assemblies in the installation folders:

{Syncfusion Installed location}\Essential Studio\{Version}\lib

Add the following assembly reference to the iOS project:

ios-unified\Syncfusion.SfRadialMenu.iOS.dll

## Initialize SfRadialMenu

### Adding Namespace
Add the namespace for the included assemblies:

{% tabs %}
{% highlight c# %}

using Syncfusion.SfRadialMenu.iOS;

{% endhighlight %}
{% endtabs %}

* Now, instantiate and add the SfRadialMenu control with a required optimal name.

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
                SfRadialMenu sfRadialMenu = new SfRadialMenu();
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

## Adding RadialMenu Items

The SfRadialMenu provides options to add multiple radial menu items with hierarchical structure. You can use font icons by adding an external font file to your iOS project bundle and referencing it through Unicode characters.

### Font Setup

1. Add your custom font file to the iOS project bundle
2. Ensure the font is properly registered in your iOS application
3. Use Unicode characters to display icons in RadialMenu items

### Adding Items with Sub-Items
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
                sfRadialMenu.CenterButtonBackText = "\uE703";
                sfRadialMenu.CenterButtonTextColor = UIColor.Black;
                sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);//
                for (int i = 0; i < 5; i++)
                {
                    //Adding Items
                    SfRadialMenuItem item = new SfRadialMenuItem() { IconFont = UIFont.FromName("Sample", 20), FontIcon = layer[i]};
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

![gettingstarted](images/overview.png)