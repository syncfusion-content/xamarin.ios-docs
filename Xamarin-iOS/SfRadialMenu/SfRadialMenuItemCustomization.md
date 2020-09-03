---
layout: post
title: Syncfusion RadialMenu item customization in Xamarin.iOS
description: Working with Syncfusion RadialMenu customization of items, text, text color, background color, and view in Xamarin.iOS.
platform: Xamarin.iOS
control: SfRadialMenu
documentation: ug
---

# SfRadialMenuItem Customization

The [SfRadialMenuItem](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html) class provides various options such as `Custom Views`, `FontIcons`, and `Images` to customize the items. You can add radial menu items by hierarchy. To add a SfRadialMenuItem with SfRadialMenu, create an instance of SfRadialMenuItem, and add it to the [Items](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_Items) property that is available in SfRadialMenu.

## Items

The [Items](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenu.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenu_Items) ) property populates the items of an inner rim in `SfRadialMenu` when the items of an outer rim are tapped.

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
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            radialMenu.CenterButtonText = "\uE713";
            radialMenu.Items.Add(new SfRadialMenuItem() { Text = "Cut" });
            radialMenu.Items.Add(new SfRadialMenuItem() { Text = "Copy" });
            radialMenu.Items[0].Items.Add(new SfRadialMenuItem() { Text = "Paste" });
            radialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center;
            this.View.AddSubview(radialMenu);
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

## Text

The [Text](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenuItem_Text) property provides text to the [SfRadialMenuItem](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html).

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
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            radialMenu.CenterButtonText = "\uE713";
            radialMenu.Items.Add(new SfRadialMenuItem() { Text = "Cut" });
            radialMenu.Items.Add(new SfRadialMenuItem() { Text = "Copy" });
            radialMenu.Items[0].Items.Add(new SfRadialMenuItem() { Text = "Paste" });
            radialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center;
            this.View.AddSubview(radialMenu);
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

## Height

The [Height](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenuItem_Height) changes the height of the [SfRadialMenuItem](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html).

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
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            radialMenu.CenterButtonText = "\uE713";
            radialMenu.Items.Add(new SfRadialMenuItem() { Text = "Cut", Height = 50 });
            radialMenu.Items.Add(new SfRadialMenuItem() { Text = "Cut", Height = 50 });
            radialMenu.Items[0].Items.Add(new SfRadialMenuItem() { Text = "Paste" });
            radialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center;
            this.View.AddSubview(radialMenu);
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

## Width

The [Width](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenuItem_Width) property changes the width of the [https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS~Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html).

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
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            radialMenu.CenterButtonText = "\uE713";
            radialMenu.Items.Add(new SfRadialMenuItem() { Text = "Cut", Width = 100 });
            radialMenu.Items.Add(new SfRadialMenuItem() { Text = "Cut", Width = 100});
            radialMenu.Items[0].Items.Add(new SfRadialMenuItem() { Text = "Paste" });
            radialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center;
            this.View.AddSubview(radialMenu);
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

![SfRadialMenu with Items](images/Items.png)

## BackgroundColor

The [BackgroundColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenuItem_BackgroundColor) property changes the background color of the [SfRadialMenuItem](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html).

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
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            radialMenu.CenterButtonText = "\uE713";
            radialMenu.Items.Add(new SfRadialMenuItem() { Text = "Cut", BackgroundColor = UIColor.FromRGB(232, 25, 156) });
            radialMenu.Items.Add(new SfRadialMenuItem() { Text = "Copy", BackgroundColor = UIColor.FromRGB(232, 25, 156) });
            radialMenu.Items[0].Items.Add(new SfRadialMenuItem() { Text = "Paste" });
            radialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center;
            this.View.AddSubview(radialMenu);
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

![SfRadialMenu with BackgroundColor](images/BackgroundColor.png)

## Font

The [Font](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenuItem_Font) property changes the font family of text in [SfRadialMenuItem](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html).

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
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            radialMenu.CenterButtonText = "\uE713";
            radialMenu.Items.Add(new SfRadialMenuItem() { Text = "Cut", Font = UIFont.FromName("Times New Roman", 15) });
            radialMenu.Items.Add(new SfRadialMenuItem() { Text = "Copy", Font = UIFont.FromName("Times New Roman", 15) });
            radialMenu.Items[0].Items.Add(new SfRadialMenuItem() { Text = "Paste" });
            radialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center;
            this.View.AddSubview(radialMenu);
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

## FontSize

The [FontSize](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenuItem_FontSize) property changes the text size of the [SfRadialMenuItem](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html).

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
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            radialMenu.CenterButtonText = "\uE713";
            radialMenu.Items.Add(new SfRadialMenuItem() { Text = "Cut", IconFont = UIFont.FromName("Times New Roman", 30), FontSize = 15 });
            radialMenu.Items.Add(new SfRadialMenuItem() { Text = "Copy", IconFont = UIFont.FromName("Times New Roman", 30),FontSize = 15 });
            radialMenu.Items[0].Items.Add(new SfRadialMenuItem() { Text = "Paste" });
            radialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center;
            this.View.AddSubview(radialMenu);
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

![SfRadialMenu with Font](images/Font.png)

## Image

The [Image](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenuItem_Image) property provides image support to the [SfRadialMenuItem](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html).

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
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            radialMenu.CenterButtonText = "\uE713";
            radialMenu.RimRadius = 100;
            radialMenu.Items.Add(new SfRadialMenuItem() { Image = "HomePageLibrary.png" });
            radialMenu.Items.Add(new SfRadialMenuItem() { Image = "eServices.png" });
            radialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center;
            this.View.AddSubview(radialMenu);
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

![SfRadialMenu with Image](images/Image.png)

## BackgroundImage

The [BackgroundImage](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenuItem_BackgroundImage) property provides the background image support to the [SfRadialMenuItem](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html).

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
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            radialMenu.CenterButtonText = "\uE713";
            radialMenu.RimRadius = 100;
            radialMenu.Items.Add(new SfRadialMenuItem() { BackgroundImage = "HomePageLibrary.png" });
            radialMenu.Items.Add(new SfRadialMenuItem() { BackgroundImage = "eServices.png" });
            radialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center;
            this.View.AddSubview(radialMenu);
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

## FontIcon

The [FontIcon](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenuItem_FontIcon) property provides font icon support to the [SfRadialMenuItem](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html).

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
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            radialMenu.CenterButtonText = "\uE713";
            radialMenu.RimRadius = 100;
            radialMenu.Items.Add(new SfRadialMenuItem() { FontIcon = "\uE9AB", IconFont = UIFont.FromName("Sample", 20) });
            radialMenu.Items.Add(new SfRadialMenuItem() { FontIcon = "\uEB73", IconFont = UIFont.FromName("Sample", 20) });
            radialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center;
            this.View.AddSubview(radialMenu);
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

![SfRadialMenu with FontIcon](images/FontIcon.png)

## FontIconColor

The [FontIconColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenuItem_FontIconColor) property changes the color of font icon in [SfRadialMenuItem](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html).

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
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            radialMenu.CenterButtonText = "\uE713";
            radialMenu.RimRadius = 100;
            radialMenu.Items.Add(new SfRadialMenuItem() { FontIcon = "\uE9AB", IconFont = UIFont.FromName("Sample", 20) , FontIconColor = UIColor.FromRGB(232, 25, 156) });
            radialMenu.Items.Add(new SfRadialMenuItem() { FontIcon = "\uEB73", IconFont = UIFont.FromName("Sample", 20), FontIconColor = UIColor.FromRGB(232, 25, 156) });
            radialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center;
            this.View.AddSubview(radialMenu);
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

![SfRadialMenu with FontIconColor](images/FontIconColor.png)

## FontSize

The [FontSize](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenuItem_FontSize) property changes the size of font icon in the [SfRadialMenuItem](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html).

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
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            radialMenu.CenterButtonText = "\uE713";
            radialMenu.RimRadius = 100;
            radialMenu.Items.Add(new SfRadialMenuItem() { FontIcon = "\uE9AB", IconFont = UIFont.FromName("Sample", 20) });
            radialMenu.Items.Add(new SfRadialMenuItem() { FontIcon = "\uEB73", IconFont = UIFont.FromName("Sample", 20) });
            radialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center;
            this.View.AddSubview(radialMenu);
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

## IconFont

The [IconFont](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html#Syncfusion_SfRadialMenu_iOS_SfRadialMenuItem_IconFont) property changes the font family of font icon in the [SfRadialMenuItem](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfRadialMenu.iOS.SfRadialMenuItem.html).

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
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.CenterButtonIconFont = UIFont.FromName("Sample", 30);
            radialMenu.CenterButtonText = "\uE713";
            radialMenu.RimRadius = 100;
            radialMenu.Items.Add(new SfRadialMenuItem() { FontIcon = "\uE9AB", IconFont = UIFont.FromName("Sample", 20) });
            radialMenu.Items.Add(new SfRadialMenuItem() { FontIcon = "\uEB73", IconFont = UIFont.FromName("Sample", 20) });
            radialMenu.CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center;
            this.View.AddSubview(radialMenu);
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
