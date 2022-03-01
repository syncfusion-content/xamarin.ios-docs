---
layout: post
title: Thumbs | SFDateTimeRangeNavigator | Xamarin.iOS | Syncfusion
description: How to customize the thumbs of range navigator
platform: xamarin.ios
control: SFDateTimeRangeNavigator
documentation: ug
---

# Thumbs

The [`LeftThumbStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeRangeNavigator.html#Syncfusion_SfChart_iOS_SFDateTimeRangeNavigator_LeftThumbStyle) and [`RightThumbStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeRangeNavigator.html#Syncfusion_SfChart_iOS_SFDateTimeRangeNavigator_RightThumbStyle) properties are used to configure the left and right thumbs of the [`SFDateTimeRangeNavigator`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeRangeNavigator.html). Following properties are available in thumb style to configure left and right thumbs individually. 

* [`BorderColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeNavigatorThumbStyle.html#Syncfusion_SfChart_iOS_SFRangeNavigatorThumbStyle_BorderColor) – used to change the stroke color of the thumb
* [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeNavigatorThumbStyle.html#Syncfusion_SfChart_iOS_SFRangeNavigatorThumbStyle_BackgroundColor) – used to change the background color of the thumb
* [`BorderWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeNavigatorThumbStyle.html#Syncfusion_SfChart_iOS_SFRangeNavigatorThumbStyle_BorderWidth) – used to change the stroke width of the thumb
* [`Width`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeNavigatorThumbStyle.html#Syncfusion_SfChart_iOS_SFRangeNavigatorThumbStyle_Width) – used to change the width of the thumb
* [`Height`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeNavigatorThumbStyle.html#Syncfusion_SfChart_iOS_SFRangeNavigatorThumbStyle_Height)  – used to change the height of the thumb
* [`LineColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeNavigatorThumbStyle.html#Syncfusion_SfChart_iOS_SFRangeNavigatorThumbStyle_LineColor) – used to change the line color of the thumb
* [`LineWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeNavigatorThumbStyle.html#Syncfusion_SfChart_iOS_SFRangeNavigatorThumbStyle_LineWidth) – used to change the line width of the thumb
* [`LineDashes`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeNavigatorThumbStyle.html#Syncfusion_SfChart_iOS_SFRangeNavigatorThumbStyle_LineDashes) – used to change the dash array of the thumb line
* [`Shape`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeNavigatorThumbStyle.html#Syncfusion_SfChart_iOS_SFRangeNavigatorThumbStyle_Shape) – used to set one of the predefined shapes for thumb like [`Default`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeNavigatorThumbShape.html), Circle, Square, Diamond, LeftArrow, RightArrow


{% highlight c# %}

SFDateTimeRangeNavigator rangeNavigator = new SFDateTimeRangeNavigator ();

rangeNavigator.LeftThumbStyle.LineColor = UIColor.Black;
rangeNavigator.LeftThumbStyle.LineWidth = 1;
rangeNavigator.LeftThumbStyle.BackgroundColor = UIColor.White;
rangeNavigator.LeftThumbStyle.BorderColor = UIColor.Purple;
rangeNavigator.LeftThumbStyle.BorderWidth = 5;
rangeNavigator.LeftThumbStyle.Height = 10;
rangeNavigator.LeftThumbStyle.Width = 10;
rangeNavigator.LeftThumbStyle.Shape = SFRangeNavigatorThumbShape.Circle;

rangeNavigator.RightThumbStyle.LineColor = UIColor.Purple;
NSNumber obj1 = new NSNumber (1);
NSNumber obj2 = new NSNumber (1);
rangeNavigator.RightThumbStyle.LineDashes = NSArray.FromObject (obj1, obj2);
rangeNavigator.RightThumbStyle.LineWidth = 2;
rangeNavigator.RightThumbStyle.BackgroundColor = UIColor.Yellow;
rangeNavigator.RightThumbStyle.BorderColor = UIColor.Green;
rangeNavigator.RightThumbStyle.BorderWidth = 2;
rangeNavigator.RightThumbStyle.Height = 15;
rangeNavigator.RightThumbStyle.Width = 15;
rangeNavigator.RightThumbStyle.Shape = SFRangeNavigatorThumbShape.Diamond;

this.View.AddSubview(rangeNavigator);

{% endhighlight %}

![Thumbs in Xamarin.iOS DateTimeRangeNavigator]( Thumb_images/Thumb1.png)

## Customization

User defined thumb layer can be created with SFDateTimeRangeNavigator. We can achieve this by creating a class that extends [`SFRangeNavigatorThumbLayer`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeNavigatorThumbLayer.html) and overriding the drawing methods of left and right thumbs.

{% highlight c# %}

public partial class ViewController : UIViewController
    {
        public ViewController (IntPtr handle) : base (handle)
        {
        }

        public override void ViewDidLoad ()
        {
            base.ViewDidLoad ();
            // Perform any additional setup after loading the view, typically from a nib.

            SFDateTimeRangeNavigator rangeNavigator = new SFDateTimeRangeNavigator ();

            CustomThumb thumbLayer = new CustomThumb ();
            rangeNavigator.ThumbLayer = thumbLayer;

            rangeNavigator.LeftThumbStyle.Width = 20;
            rangeNavigator.RightThumbStyle.Width = 20;

            this.View.AddSubview (rangeNavigator);
        }
    }


    public class CustomThumb : SFRangeNavigatorThumbLayer
    {
        public override void DrawLeftThumbInContext (CGContext context, CGPoint startPoint, CGPoint endPoint)
        {
            CGRect thumbRect = new CGRect (endPoint.X - 10, endPoint.Y, 20, 20);

            this.SetLeftThumbFrame (thumbRect);

            UIGraphics.PushContext (context);
            context.SetFillColor (UIColor.Red.CGColor);
            context.FillRect (thumbRect);
            UIGraphics.PopContext ();
        }

        public override void DrawRightThumbInContext (CGContext context, CGPoint startPoint, CGPoint endPoint)
        {
            CGRect thumbRect = new CGRect (endPoint.X - 10, endPoint.Y, 20, 20);

            this.SetRightThumbFrame (thumbRect);

            UIGraphics.PushContext (context);
            context.SetFillColor (UIColor.Red.CGColor);
            context.FillRect (thumbRect);
            UIGraphics.PopContext ();
        }

    }


{% endhighlight %}

![Customization of thumbs in Xamarin.iOS DateTimeRangeNavigator]( Thumb_images/Thumb2.png)
