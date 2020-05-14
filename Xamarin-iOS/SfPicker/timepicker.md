---
layout: post
title: Creating TimePicker using Syncfusion SfPicker in Xamarin.iOS platform.
description: This section will explain about how to create Custom TimePicekr using Syncfusion SfPicker control in Xamarin.iOS platform.
platform: Xamarin.iOS
control: Picker
documentation: ug
---

# Custom TimePicker using SfPicker

This section will explain about how create `TimePicker` using `SfPicker` control in the following steps.

## Steps

**Step****1** **:** We have created custom class named as `TimePicker`. This should be inherited from `SfPicker` control.

{% tabs %}

{% highlight c# %}

public class TimePicker : SfPicker
{

}

{% endhighlight %}

{% endtabs %}

**Step** **2** **:** After creating that four ObservableCollection with object type in TimePicker class.

**Collection** **details** **:**

TIme Collection, Minute Collection, Hour Collection and Format Collection.

Time Collection -> We have added all the three collections.

Minute Collection -> We have added minutes from 0 to 59.

Hour Collection -> We have added hours from 0\1 to 12.

Format Collection -> We have added two format AM and PM.

The below code demonstrates Time collection creation.

{% tabs %}

{% highlight c# %}

public class TimePicker : SfPicker
{

    /// <summary>
    /// Header API is holds the column name for every column in time picker
    /// </summary>
    public ObservableCollection<string> Headers { get; set; }
    public TimePicker()
    {
        Headers = new ObservableCollection<string>();
        Headers.Add("HOUR");
        Headers.Add("MINUTE");
        Headers.Add("FORMAT");

        //SfPicker header text
        HeaderText = "TIME PICKER";
        
        // Column header text collection
        this.ColumnHeaderText = Headers;
    }
}

{% endhighlight %}

{% endtabs %}

**Step** **3** **:** We have defined each column header "Hour", "Minute" and "Format" using ColumnHeaderText property of SfPicker control. The below code demonstrates how to define header for each column of SfPicker control.

{% tabs %}

{% highlight c# %}

public class TimePicker : SfPicker
{
    /// <summary>
    /// Header API is holds the column name for every column in time picker
    /// </summary>
    public ObservableCollection<string> Headers { get; set; }

    public TimePicker()
    {
        Headers = new ObservableCollection<string>();
        Headers.Add("Hour");
        Headers.Add("Minute");
        Headers.Add("Format");
        
        //SfPicker header text
        HeaderText = "Time Picker";

        // Column header text collection
        this.ColumnHeaderText = Headers;
    }
}

{% endhighlight %}

{% endtabs %}

**Step** **4** **:** Finally we have enabled SfPicker footer, header and Column header using ShowFooter, ShowHeader and ShowColumnHeader properties.

{% tabs %}

{% highlight c# %}

public TimePicker()
{
    //Enable Footer of SfPicker
    ShowFooter = true;
    
    //Enable Header of SfPicker
    ShowHeader = true;

    //Enable Column Header of SfPicker
    ShowColumnHeader = true;
}

{% endhighlight %}

{% endtabs %}

**Step** **5** **:** We have added the TimePicker control in ViewDidLoad page. Please refer the below code snippets.

{% tabs %}

{% highlight c# %}

public partial class ViewController : UIViewController
{

    TimePicker timePicker;

    public ViewController(IntPtr handle) : base(handle)
    {
        timePicker = new TimePicker();
    }

    public override void ViewDidLoad()
    {
        base.ViewDidLoad();

        timePicker.BackgroundColor = UIColor.White;
        timePicker.ColumnHeaderHeight = 70;
        timePicker.PickerHeight = 400;
        timePicker.PickerWidth = 300;
        timePicker.PickerMode = PickerMode.Default;
        timePicker.SelectedItem = timePicker.SelectedTime;
        timePicker.Frame = new CoreGraphics.CGRect(0, 0, this.View.Frame.Width - 50, this.View.Frame.Height / 2);
        this.View.AddSubview(timePicker);
    }
}

{% endhighlight %}

{% endtabs %}

We have attached TimePicker sample for reference. Please download the sample from the following link.

Sample link: https://www.syncfusion.com/downloads/support/directtrac/general/ze/TimePicker-737192613.zip 