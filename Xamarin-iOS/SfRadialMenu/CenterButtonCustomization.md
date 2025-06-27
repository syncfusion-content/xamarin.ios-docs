---
layout: post
title: Center button customization with Syncfusion® RadialMenu control in Xamarin.iOS
description: Learn about customization options available for CenterButton and BackButton in SfRadialMenu for Xamarin.iOS
platform: xamarin.ios
control: SfRadialMenu
documentation: ug
---

# Center Button and Back Button Customization
The center button and back button in the radial menu are displayed at the center of the control. These buttons perform essential operations such as opening and closing the rim and navigating between menu levels. The SfRadialMenu allows you to customize the center button and back button with various options including font icons, custom views, and captions.

## CenterButtonText and CenterButtonBackText

The [CenterButtonText](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_CenterButtonText) property sets the text or icon for the center button in SfRadialMenu, while the [CenterButtonBackText](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_CenterButtonBackText) property sets the text or icon for the center back button.

{% tabs %}
{% highlight C# %}

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

![Center button text customization example](images/CenterButtonText.png)
## CenterButtonTextColor and CenterButtonBackTextColor

The [CenterButtonTextColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_CenterButtonTextColor) property changes the text color of the center button, while the [CenterButtonBackTextColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_CenterButtonBackTextColor) property changes the text color of the center back button in SfRadialMenu.
{% tabs %}
{% highlight C# %}

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
            sfRadialMenu.CenterButtonTextColor = UIColor.Blue;
            sfRadialMenu.CenterButtonBackTextColor = UIColor.Blue;
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

![CenterButtonTextColor](images/CenterButtonTextColor.png)

## CenterButtonBackground

The [CenterButtonBackgroundColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_CenterButtonBackgroundColor) changes the background color of the center button in [SfRadialMenu](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html).

{% tabs %}
{% highlight C# %}

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
            sfRadialMenu.CenterButtonBackgroundColor = UIColor.FromRGB(232, 25, 156);
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

![CenterButtonBackgroundColor](images/CenterButtonBackgroundColor.png)

## CenterButtonRadius

The [CenterButtonRadius](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_CenterButtonRadius) changes the radius of the center button in [SfRadialMenu](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html).

{% tabs %}
{% highlight C# %}

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
            sfRadialMenu.CenterButtonRadius = 20;
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

![CenterButtonRadius](images/CenterButtonRadius.png)

## CenterButtonIconFont

The [CenterButtonTypeface](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_CenterButtonIconFont) changes the font family of the center button in [SfRadialMenu](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html).

{% tabs %}
{% highlight C# %}

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
            sfRadialMenu.CenterButtonRadius = 20;
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

![CenterButtonIconFont](images/CenterButtonText.png)

## CenterButtonBorderColor

The [CenterButtonBorderColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_CenterButtonBorderColor) changes the border color of the center button in [SfRadialMenu](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html).

{% tabs %}
{% highlight C# %}

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
            sfRadialMenu.CenterButtonRadius = 20;
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            sfRadialMenu.CenterButtonBorderColor = UIColor.Black;
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

![CenterButtonBorderColor](images/CenterButtonBorderColor.png)

## CenterButtonBorderThickness

The [CenterButtonBorderThickness](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_CenterButtonBorderThickness) changes the border thickness of the center button in [SfRadialMenu](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html).

{% tabs %}
{% highlight C# %}

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
            sfRadialMenu.CenterButtonRadius = 20;
            sfRadialMenu.CenterButtonBorderThickness = 20;
            sfRadialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            sfRadialMenu.CenterButtonBorderColor = UIColor.Black;
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

![CenterButtonBorderThickness](images/CenterButtonBorderThickness.png)

## CenterButtonPlacement

The [CenterButtonPlacement](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_CenterButtonPlacement) changes the placement of the center button in [SfRadialMenu](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html).

{% tabs %}
{% highlight C# %}

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

## EnableCenterButtonAnimation

The [EnableCenterButtonAnimation](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_EnableCenterButtonAnimation) is used to either enable or disable animation of the center button in [SfRadialMenu](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html).

{% tabs %}
{% highlight C# %}

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
            sfRadialMenu.EnableCenterButtonAnimation = true;
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

