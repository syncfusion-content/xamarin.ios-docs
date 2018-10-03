---
layout: post
title: Popup Layouts | SfPopupLayout |Xamarin.iOS | Syncfusion
description: Layouts in SfPopupLayout
platform: Xamarin.iOS
control: SfPopupLayout
documentation: ug
--- 

# Renderer the SfPopupLayout on storyboard

This section explains how to renderer SfPopupLayout using storyboard with simple sample.

## This following steps will illustrates how to use SfPopupLayout on storyboard

1. Create a new view controller. 
 
3. Drag the SfPopupLayout from tool box and drop into storyboard.

4. Since this is hosting control so it does not has preview on designer page. You can see the Popupview only when deploy on the device.

5. Drag Button from tool box and drop into inside of SfPopupLayout on stroyboard.

6. Place the cursor on SfPopupLayout and go to Properties window.

7. Set the StaysOpen property as true on Properties window. 

![](SfPopupLayout_images/axml_support_sfpopuplayout.png)storyboard_staysopen_sfpopup_ios.jpg)

8. Ensure the behavior

The below code will illustrate to display the Popup on button click.

{% highlight %}
using UIKit;

namespace Storyboard_SfpopupLayout_ios
{
    public partial class MyViewController : UIViewController
    {
        partial void buttonclicked(UIButton sender)
        {
            sfpopup.Show();
        }

        public MyViewController() : base("MyViewController", null)
        {
        }

        public override void ViewDidLoad()
        {
            base.ViewDidLoad();
            // Perform any additional setup after loading the view, typically from a nib.
        }

        public override void DidReceiveMemoryWarning()
        {
            base.DidReceiveMemoryWarning();
            // Release any cached data, images, etc that aren't in use.
        }
    }
}
{% endhighlight %}

Now, run the application to render the following output.

You can download the entire source code of this demo for Xamarin.ios from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Storyboard_SfpopupLayout_ios-281954337).

![](SfPopupLayout_images/storyBoard_support_sfPopuplayout_ios.png)


