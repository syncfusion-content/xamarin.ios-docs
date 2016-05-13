---
layout: post
title: Thumbs | SFDateTimeRangeNavigator | Xamarin.iOS | Syncfusion
description: How to customize the thumbs of range navigator
platform: xamarin.ios
control: SFDateTimeRangeNavigator
documentation: ug
---

# Thumbs

The `LeftThumbStyle` and `RightThumbStyle` properties are used to configure the left and right thumbs of the `SFDateTimeRangeNavigator`. Following properties are available in thumb style to configure left and right thumbs individually. 

* `BorderColor`  – used to change the stroke color of the thumb
* `BackgroundColor`  – used to change the background color of the thumb
* `BorderWidth`  – used to change the stroke width of the thumb
* `Width`  – used to change the width of the thumb
* `Height`   – used to change the height of the thumb
* `LineColor`  – used to change the line color of the thumb
* `LineWidth` – used to change the line width of the thumb
* `LineDashes` – used to change the dash array of the thumb line
* `Shape` – used to set one of the predefined shapes for thumb like Default, Circle, Square, Diamond, LeftArrow, RightArrow


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

![]( Thumb_images/Thumb1.png)

## Cusotmization

User defined thumb layer can be created with SFDateTimeRangeNavigator. We can achieve this by creating a class that extends `SFRangeNavigatorThumbLayer` and overriding the drawing methods of left and right thumbs.

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
        public override void DrawLeftThumbInContext (CGContext ctx, CGPoint startPoint, CGPoint endPoint)
        {
            CGRect thumbRect = new CGRect (endPoint.X - 10, endPoint.Y, 20, 20);

            this.SetLeftThumbFrame (thumbRect);

            UIGraphics.PushContext (ctx);
            ctx.SetFillColor (UIColor.Red.CGColor);
            ctx.FillRect (thumbRect);
            UIGraphics.PopContext ();
        }

        public override void DrawRightThumbInContext (CGContext ctx, CGPoint startPoint, CGPoint endPoint)
        {
            CGRect thumbRect = new CGRect (endPoint.X - 10, endPoint.Y, 20, 20);

            this.SetRightThumbFrame (thumbRect);

            UIGraphics.PushContext (ctx);
            ctx.SetFillColor (UIColor.Red.CGColor);
            ctx.FillRect (thumbRect);
            UIGraphics.PopContext ();
        }

    }


{% endhighlight %}

![]( Thumb_images/Thumb2.png)
