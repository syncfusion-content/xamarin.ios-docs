---
layout : post
title : Events in Syncfusion RadialMenu control for Xamarin.iOS
description : Learn how to perform events like navigating, opening, navigated, opened, center button tapped and when the center button back has been tapped in SfRadialMenu
platform : Xamarin.iOS
control : SfRadialMenu
documentation : ug
---

# Events

## Perform an action when navigating to next level

In radial menu, you can perform an action when navigating from one level to another level. The `Navigating` event occurs when navigating from one level to another level, and the `Navigated` event occurs after navigating to another level.

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
            sfRadialMenu.Navigated += SfRadialMenu_Navigated;
            sfRadialMenu.Navigating += sfRadialMenu_Navigating;
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            for (int i = 0; i < 5; i++)
            {
                //Adding�Items
                SfRadialMenuItem item = new SfRadialMenuItem() { IconFont = UIFont.FromName("Sample", 20), FontIcon = layer[i] };
                //Adding�Sub items
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

        private void sfRadialMenu_Navigating(object sender, RadialMenuEventArgs e)
        {
            var okAlertController = UIAlertController.Create("Alert", "ItemNavigating", UIAlertControllerStyle.Alert);
            //Add Action
            okAlertController.AddAction(UIAlertAction.Create("OK", UIAlertActionStyle.Default, null));
            // Present Alert
            PresentViewController(okAlertController, true, null);

        }

        private void SfRadialMenu_Navigated(object sender, EventArgs e)
        {
            var okAlertController = UIAlertController.Create("Alert", "ItemNavigated", UIAlertControllerStyle.Alert);
            //Add Action
            okAlertController.AddAction(UIAlertAction.Create("OK", UIAlertActionStyle.Default, null));
            // Present Alert
            PresentViewController(okAlertController, true, null);
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

N> You can cancel navigation using the `Cancel` event argument.

## Perform an action when opening the radial menu

You can perform an action when opening the radial menu. The `Opening` event occurs when opening the radial menu, and the `Opened` event occurs after opening the radial menu.

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
            sfRadialMenu.Opening += SfRadialMenu_Opening;
            sfRadialMenu.Opened += sfRadialMenu_Opened;
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
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

        private void sfRadialMenu_Opened(object sender, EventArgs e)
        {
            var okAlertController = UIAlertController.Create("Alert", "Opened", UIAlertControllerStyle.Alert);
            //Add Action
            okAlertController.AddAction(UIAlertAction.Create("OK", UIAlertActionStyle.Default, null));
            // Present Alert
            PresentViewController(okAlertController, true, null);

        }

        private void SfRadialMenu_Opening(object sender, EventArgs e)
        {
            var okAlertController = UIAlertController.Create("Alert", "Opening", UIAlertControllerStyle.Alert);
            //Add Action
            okAlertController.AddAction(UIAlertAction.Create("OK", UIAlertActionStyle.Default, null));
            // Present Alert
            PresentViewController(okAlertController, true, null);
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

## Perform an action when closing radial menu

You can perform an action when closing the radial menu. The `Closing` event occurs when closing the radial menu, and the `Closed` event occurs after closing the radial menu.

N> You can cancel the opening of radial menu using the `Cancel` event argument.

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
            sfRadialMenu.Closing += SfRadialMenu_Closing;
            sfRadialMenu.Closed += sfRadialMenu_Closed;
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
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
            private void sfRadialMenu_Closed(object sender, EventArgs e)
            {
                var okAlertController = UIAlertController.Create("Alert", "Closed", UIAlertControllerStyle.Alert);
                //Add Action
                okAlertController.AddAction(UIAlertAction.Create("OK", UIAlertActionStyle.Default, null));
                // Present Alert
                PresentViewController(okAlertController, true, null);

            }

            private void SfRadialMenu_Closing(object sender, EventArgs e)
            {
                var okAlertController = UIAlertController.Create("Alert", "Closing", UIAlertControllerStyle.Alert);
                //Add Action
                okAlertController.AddAction(UIAlertAction.Create("OK", UIAlertActionStyle.Default, null));
                // Present Alert
                PresentViewController(okAlertController, true, null);
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

N> You can close navigation using the `Cancel` event argument.

## Perform an action when tapping the center button

You can perform an action when tapping the center button of the radial menu. The `CenterButtonTapped` event occurs when tapping the center button of the radial menu.

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
            sfRadialMenu.CenterButtonTapped += SfRadialMenu_CenterButtonTapped;
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
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

            private void SfRadialMenu_CenterButtonTapped(object sender, EventArgs e)
            {
                var okAlertController = UIAlertController.Create("Alert", "CenterButtonTapped", UIAlertControllerStyle.Alert);
                //Add Action
                okAlertController.AddAction(UIAlertAction.Create("OK", UIAlertActionStyle.Default, null));
                // Present Alert
                PresentViewController(okAlertController, true, null);
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