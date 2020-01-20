---
layout: post
title: Placing and Dragging Syncfusion RadialMenu control in Xamarin.iOS
description: Postioning and Dragging of Syncfusion RadialMenu control using Point, DragBegin and DragEnd respectively in Xamarin.iOS
platform: Xamarin.iOS
control: SfRadialMenu
documentation: ug
---

# Placing and dragging RadialMenu

You can place radial menu anywhere on its parent layout, and drag it with in the parent layout. 

## Dragging RadialMenu

You can enable/disable dragging using the [IsDragEnabled](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS~Syncfusion.SfRadialMenu.iOS.SfRadialMenu~IsDragEnabled.html) property.

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
            sfRadialMenu.IsDragEnabled = true;
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

## DragEvents

SfRadialMenu provides the DragBegin and DragEnd events, which occurs when the RadialMenu is dragged.

### DragBegin

This event occurs when RadialMenu is started to drag with `DragBeginEventArgs`.

* `Position` - Gets the start position of the RadialMenu.

* `Handled` - Gets or sets the boolean value for enabling and disabling the dragging of RadialMenu.

To hook the [DragBegin](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS~Syncfusion.SfRadialMenu.iOS.SfRadialMenu~DragBegin_EV.html) event and to get the start position and restrict dragging, refer to the following code example.

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
            sfRadialMenu.IsDragEnabled = true;
            sfRadialMenu.DragBegin += SfRadialMenu_DragBegin;
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

        private void SfRadialMenu_DragBegin(object sender, DragBeginEventArgs e)
        {
            var okAlertController = UIAlertController.Create("Alert", "DragBegin", UIAlertControllerStyle.Alert);
            //Add Action
            okAlertController.AddAction(UIAlertAction.Create("OK", UIAlertActionStyle.Default, null));
            //Present Alert
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

### DragEnd

This event occurs when end dragging in RadialMenu with `DragEndEventArgs`.

* `OldValue` - Gets the start position of the RadialMenu.

* `NewValue` - Gets the end position of the RadialMenu.

* `Handled` - Gets or sets the boolean value for restricting the RadialMenu from moving to another position.

To hook the [DragEnd](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS~Syncfusion.SfRadialMenu.iOS.SfRadialMenu~DragEnd_EV.html) event, to get the start position and end position, and to restrict the movement of RadialMenu, refer to the following code example.

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
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            sfRadialMenu.IsDragEnabled = true;
            sfRadialMenu.DragBegin += SfRadialMenu_DragBegin;
            sfRadialMenu.DragEnd += SfRadialMenu_DragEnd;
            sfRadialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.TopLeft;
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

            this.View.AddSubview(sfRadialMenu);
        }

       private void SfRadialMenu_DragBegin(object sender, DragBeginEventArgs e)
       {
           var okAlertController = UIAlertController.Create("Alert", "DragBegin", UIAlertControllerStyle.Alert);
           //Add Action
           okAlertController.AddAction(UIAlertAction.Create("OK", UIAlertActionStyle.Default, null));
           // Present Alert
           PresentViewController(okAlertController, true, null;
       }

	   private void SfRadialMenu_DragEnd(object sender, DragEndEventArgs e)
	   {
			e.Handled = true;
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

## Placement of RadialMenu

You can place the SfRadialMenu based on their CenterButton axis by providing the [CenterButtonPlacement](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS~Syncfusion.SfRadialMenu.iOS.SfRadialMenu~CenterButtonPlacement.html) enum property with TopLeft and Center positions.

`TopLeft` - Places the origin (0,0) of SfRadialMenu at the top-left corner.

`Center` - Places the origin (0,0) of SfRadialMenu at the center.

N> The default value of [CenterButtonPlacement](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS~Syncfusion.SfRadialMenu.iOS.SfRadialMenu~CenterButtonPlacement.html) property is Center.

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
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            sfRadialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.TopLeft;
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

## Placing RadialMenu

You can place radial menu anywhere on its parent layout using the [Position](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS~Syncfusion.SfRadialMenu.iOS.SfRadialMenu~Position.html) property. The position of Radial Menu is calculated based on the center point of parent layout.

{% tabs %}
{% highlight c# %}

using CoreGraphics;
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
            sfRadialMenu.CenterButtonText = "\uE9AB";
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            sfRadialMenu.IsDragEnabled = true;
            sfRadialMenu.Position = new CGPoint(100, 150);
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

![Image for position](images/position.png)