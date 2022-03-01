---
layout: post
title: Getting Started with Syncfusion RadialMenu control for Xamarin.Android 
description: A quick tour to the new users of Syncfusion RadialMenu control to get familiar with the control for Xamarin.Android platform.
platform: Xamarin.Android 
control: RadialMenu
documentation: ug
---

# Getting Started

This section explains the steps required to configure the SfRadialMenu control in a real-time scenario and provides a walk-through on some of the customization features available.

## Referencing Essential Studio components in your solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders.

{Syncfusion Installed location}\Essential Studio\14.XXXX.X.XX\lib

Add the following assembly references to the Android project.

ios-unified\Syncfusion.SfRadialMenu.iOS.dll

## Add SfRadialMenu

* Adding namespace to the added assemblies. 

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

## Adding RadialMenu items

SfRadialMenu provides the option to add a number of radial menu items. Add an external font icon typeface into the `Asset` folder, and then set its build action to Android assets. The Unicode can be passed as text to display icons in the SfRadialMenu item.

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