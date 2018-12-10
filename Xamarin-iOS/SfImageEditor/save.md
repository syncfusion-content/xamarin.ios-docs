---
layout : post
title : Save Image in Syncfusion SfImageEditor control in Xamarin.iOS
description : Learn how to save the image in ImageEditor for Xamarin.iOS
platform : xamarin.ios
control : ImageEditor
documentation : ug
---

## Save

You can save the image along with the current edits to the device using the `Save` method.

The saved image will be added in default pictures folder of the device.

{% tabs %}

{% highlight C# %}

     editor.Save();

{% endhighlight %}

{% endtabs %}

## Save events

The SfImageEditor has events when performing save operation namely `ImageSaving` and `ImageSaved`.

### ImageSaving

This event occurs before saving the image. You can control the save functionality using the `Cancel` argument.

* Cancel: 

It restricts saving image to the default location when set `Cancel` value to `true`.

{% highlight C# %}

        public override void ViewDidLoad()
        {
            editor.ImageSaving += Editor_ImageSaving;
        }

        private void Editor_ImageSaving(object sender, ImageSavingEventArgs e)
        {
            e.Cancel = true;
        }

{% endhighlight %}

* Stream

You can get current image edits as stream using this argument.

{% highlight C# %}
         
        private void Editor_ImageSaving(object sender, ImageSavingEventArgs e)
        {
            var stream = e.Stream;
        }

{% endhighlight %}

### ImageSaved

This event occurs after the image has been saved. To get the location of the saved image, use the location argument as shown in the following code.

{% highlight C# %}

        public override void ViewDidLoad()
        {            
            editor.ImageSaved += Editor_ImageSaved;
        }

        private void Editor_ImageSaved(object sender, ImageSavedEventArgs e)
        {
            string savedLocation = e.Location; // You can get the saved image location with the help of this argument
        }

{% endhighlight %}

## Saving Image with Custom Size and Format

The `Save` method in the SfImageEditor control allows user to save an image in different format such as `png`, `jpg` and `bmp`.

To choose the format while Saving the image.

{% tabs %}

{% highlight C# %}

editor.Save(".png");

{% endhighlight %}

{% endtabs %}

To choose the format and size while Saving the image as like below,

{% tabs %}

{% highlight C# %}

editor.Save(".png",new Size(913,764));

{% endhighlight %}

{% endtabs %}

N> Supported formats are `.png`, `.jpg` and `.bmp`.

## Reset

The `Reset` method resets the complete set of changes made in image and resets the image to original loaded image.

{% tabs %}

{% highlight C# %}

    editor.Reset();

{% endhighlight %}

{% endtabs %}

## Reset events

The SfImageEditor has events when performing reset operation namely `BeginReset` and `EndReset`.

### BeginReset

This event occurs before resetting the changes made in an image. You can control the reset functionality using the Cancel argument.


{% highlight C# %}

        public override void ViewDidLoad()
        {
            editor.BeginReset += Editor_BeginReset;
        }

        private void Editor_BeginReset(object sender, BeginResetEventArgs e)
        {
            e.Cancel = true; //It restricts resetting image to initial loaded image.
        }

{% endhighlight %}

### EndReset

This event occurs when reset has been completed.

{% highlight C# %}

        public override void ViewDidLoad()
        {
            editor.EndReset += Editor_EndReset;
        }

        private void Editor_EndReset(object sender, EndResetEventArgs e)
        {
            NavigationController.PushViewController(new ImageEditorViewController());  //Navigates to new page after completing the reset action.
        }

{% endhighlight %}

## ImageLoaded Event

This event will be triggered after the image has been loaded. By using this event, you can add any shapes or text over an image or crop an image while initially loading the image. 

{% highlight C# %}

        public override void ViewDidLoad()
        {
            editor.ImageLoaded += Editor_ImageLoaded;
        }

        private void Editor_ImageLoaded(object sender, ImageLoadedEventArgs e)
        {
            editor.AddShape(ShapeType.Circle, new PenSettings() { Color = UIColor.Red, Mode = Mode.Stroke });
        }

{% endhighlight %}

## ItemSelected Event

This event will be triggered whenever you tap the selected shapes (rectangle, circle, and arrow) and text. You can get the settings of each selected shapes and text using the ItemSelected argument. You can also change the settings that will affect the selected shape.

{% highlight C# %}

        public override void ViewDidLoad()
        {
            editor.ItemSelected += Editor_ItemSelected;
        }

        private void Editor_ItemSelected(object sender, ItemSelectedEventArgs e)
        {
            var Settings = e.Settings;

            if (Settings is PenSettings)
            {
                (Settings as PenSettings).Color = UIColor.Green;
            }
            else
            {
                (Settings as TextSettings).Color = UIColor.Red;
            }
        }

{% endhighlight %}

## ItemUnselected Event

This event will be triggered whenever you change the shape selections from one shape to another shape (rectangle, circle, arrow and text). You can get the settings of previous selected shape and text using the ItemUnselected event. You can also change the settings of previous selected shape.

{% highlight C# %}

        public override void ViewDidLoad()
        {
            editor.ItemUnselected += Editor_ItemUnselected;
        }

        private void Editor_ItemUnselected(object sender, ItemUnselectedEventArgs e)
        {
            var Settings = e.Settings;

            if (Settings is PenSettings)
            {
                (Settings as PenSettings).Color = UIColor.Green;
            }
            else
            {
                (Settings as TextSettings).Color = UIColor.Green;
            }
        }

{% endhighlight %}