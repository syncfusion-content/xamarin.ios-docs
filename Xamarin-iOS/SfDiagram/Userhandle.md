---
title: Userhadles for Essential Xamarin.iOS Diagram | Syncfusion
description: Learn how to add userhandles ,userhandles customization and its event handle in diagram for Xamarin.iOS
platform: Xamarin.iOS
control: SfDiagram
documentation: UG
keywords: 
---
# User handles
User handles are customizable handles which can be used to perform custom actions and also default clipboard actions. You can able to customize the user handles using:
* SfGraphicPath
* Image
* UIView
The following code illustrates how to add custom user handle in diagram:
{% tabs %}
{% highlight c# %}
//Add Graphic path into custom handle
SfGraphics graph = new SfGraphics();
Pen stroke = new Pen();
stroke.Brush = new SolidBrush(UIColor.Clear);
stroke.StrokeWidth = 3;
stroke.StrokeBrush = new SolidBrush(UIColor.FromRGB(24, 161, 237));
graph.DrawEllipse(stroke, new System.Drawing.Rectangle(10, 0, 20, 20));
graph.DrawArc(stroke, 0, 20, 40, 40, 180, 180);

//Add image into custom handle
var image = new UIImageView(UIImage.FromBundle("delete.png"));
image.BackgroundColor = UIColor.Clear;

//Add UIView into custom handle
diagram.UserHandles.Add(new UserHandle("UIView", UserHandlePosition.Left, new UIView() { BackgroundColor = UIColor.Purple }));

diagram.UserHandles.Add(new UserHandle("delete", UserHandlePosition.Bottom, image) { });

diagram.UserHandles.Add(new UserHandle("right", UserHandlePosition.Right,graph){ });


{% endhighlight %}
{% endtabs %}

## User handles clicked event
The following code illustrate how to define user handles clicked event and its action.
{% tabs %}
{% highlight c# %}
//User handles clicked event
diagram.UserHandleClicked += Diagram_UserHandleClicked;

private void Diagram_UserHandleClicked(object sender, UserHandleClickedEventArgs args)
{
     // Delete custom handle action
     if (args.Item.Name == "delete")
     {
        diagram.Delete();
    }
}

{% endhighlight %}
{% endtabs %}
![Userhandle in Xamarin.iOS diagram](Userhandle_images/Userhandle_img1.jpeg)

## Customizing user handle position
User handle position can be moved or adjusted from its default position. The following code shows how to adjust the position using the “MoveBy” method.
{% tabs %}
{% highlight c# %}
     //Define the user handle 

            UserHandleCollection userHandles = new UserHandleCollection();
            UserHandle left = new UserHandle("Left", UserHandlePosition.Left, plusTemplate) { Visible = true };
     //Customize the user handle position using move by method
            left.MoveBy(-10, -10);
            userHandles.Add(left);
            userHandles.Add(new UserHandle("Right", UserHandlePosition.Right, m_expandTemplate) { Visible = true });
            userHandles.Add(new UserHandle("Delete", UserHandlePosition.Bottom, deleteTemplate) { Visible = true });
            diagram.UserHandles = userHandles;
{% endhighlight %}
{% endtabs %}
![Customize user handle position in Xamarin.iOS diagram](Userhandle_images/Userhandle_img2.jpeg)

