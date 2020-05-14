---
layout: post
title:  Creating DatePicker using Syncfusion SfPicker in Xamarin.iOS platform.
description: This section will explain about how to create DatePicker using Syncfusion SfPicker control in Xamarin.iOS platform.
platform: Xamarin.iOS
control: Picker
documentation: ug
---

# Date TIme Picker

in our Xamarin.Forms SfPicker control has multi column support. Using this we can populate day, month, year, and minute values of collection in SfPicker control.

We have demonstrate how to create custom DateTimePicker using Syncfusion `SfPicker` control in the following steps.

**Step** **1** **:** We have created custom class named as "DateTimePicker". This class should be inherited from SfPicker control.

{% tabs %}

{% highlight c# %}

public class DateTimePicker : SfPicker
{

}

{% endhighlight %}

{% endtabs %}

**Step****2** **:** After that create size Observable collection with object type in DateTimePicker class.

**Collection details** **:**

Day collection. Month collection, Year collection, Hour collection and Minute collection.

Day collection -> We have added current month days using DateTime.DaysInMonth.

Month collection -> We have added Jan to Dec months.

Year collection -> We have added 1990 to 2050 years.

Hour collection -> We have added 0 to24 hours.

Minute collection -> We have added 00 to 59 minutes.

Date collection -> We have added all the five collections.

Date collection is main collection we have assigned this collection to ItemsSource of Picker control.

The below code demonstrates Date collection creation.

{% tabs %}

{% highlight c# %}

public class DateTimePicker : SfPicker
{
    #region Public Properties

    // Months API is used to modify the Day collection as per change in Month
    internal Dictionary<string, string> Months { get; set; }

    /// <summary>
    /// Date is the actual DataSource for SfPicker control which will holds the collection of Day ,Month and Year
    /// </summary>
    /// <value>The date.</value>

    public ObservableCollection<object> Date { get; set; }

    //Day is the collection of day numbers
    internal ObservableCollection<object> Day { get; set; }

    //Month is the collection of Month Names
    internal ObservableCollection<object> Month { get; set; }

    //Year is the collection of Years from 1990 to 2042
    internal ObservableCollection<object> Year { get; set; }

    //Hour is the collection of Hours in Railway time format
    internal ObservableCollection<object> Hour { get; set; }
   
    //Minute is the collection of Minutes from 00 to 59
    internal ObservableCollection<object> Minute { get; set; }

    #endregion
    public DateTimePicker()
    {
        Months = new Dictionary<string, string>();
        Date = new ObservableCollection<object>();
        Day = new ObservableCollection<object>();
        Month = new ObservableCollection<object>();
        Year = new ObservableCollection<object>();
        Hour = new ObservableCollection<object>();
        Minute = new ObservableCollection<object>();
        PopulateDateCollection();
        this.ItemsSource = Date;
    }

    private void PopulateDateCollection()
    {
        //populate months
        for (int i = 1; i < 13; i++)
        {
            if (!Months.ContainsKey(CultureInfo.CurrentCulture.DateTimeFormat.GetMonthName(i).Substring(0, 3)))
                Months.Add(CultureInfo.CurrentCulture.DateTimeFormat.GetMonthName(i).Substring(0, 3), CultureInfo.CurrentCulture.DateTimeFormat.GetMonthName(i));
            Month.Add(CultureInfo.CurrentCulture.DateTimeFormat.GetMonthName(i).Substring(0, 3));
        }

        //populate year
        for (int i = 1990; i < 2050; i++)
        {
            Year.Add(i.ToString());
        }

        //populate Days
        for (int i = 1; i <= DateTime.DaysInMonth(DateTime.Now.Year, DateTime.Now.Month); i++)
        {
            if (i < 10)
            {
                Day.Add("0" + i);
            }

            else
                Day.Add(i.ToString());
        }

        //populate Hours
        for (int i = 1; i <= 24; i++)
        {
            if (i < 10)
            {
                Hour.Add("0" + i.ToString());
            }

            else
                Hour.Add(i.ToString());
        }

        //populate Minutes
        for (int j = 0; j < 60; j++)
        {
            if (j < 10)
            {
                Minute.Add("0" + j);
            }
            else
                Minute.Add(j.ToString());
        }

        Date.Add(Month);
        Date.Add(Day);
        Date.Add(Year);
        Date.Add(Hour);
        Date.Add(Minute);
    }
}

{% endhighlight %}

{% endtabs %}

**Step** **3** **:** We have updated the days value based on month and year value using SelectionChanged event of SfPicker control. since the days of each month differs we have to handle this collection.

{% tabs %}

{% highlight c# %}

public class DateTimePicker : SfPicker
{
    public DateTimePicker()
    {
        this.SelectionChanged += DateTimePicker_SelectionChanged; ;
    }

    private void DateTimePicker_SelectionChanged(object sender, SelectionChangedEventArgs e)
    {
        UpdateDays(Date, e);
    }

    //UpdateDays method is used to alter the Date collection as per selection change in Month column(if Feb is Selected day collection has value from 1 to 28)
    public void UpdateDays(ObservableCollection<object> Date, SelectionChangedEventArgs e)
    {
        try
        {
            bool isupdate = false;
            if (e.OldValue != null && e.NewValue != null && (e.OldValue as IList).Count > 0 && (e.NewValue as IList).Count > 0)
            {
                if ((e.OldValue as IList)[0] != (e.NewValue as IList)[0])
                {
                    isupdate = true;
                }

                if ((e.OldValue as IList)[2] != (e.NewValue as IList)[2])
                {
                    isupdate = true;
                }
            }

            if (isupdate)
            {
                ObservableCollection<object> days = new ObservableCollection<object>();
                int month = DateTime.ParseExact(Months[(e.NewValue as IList)[0].ToString()], "MMMM", CultureInfo.InvariantCulture).Month;
                int year = int.Parse((e.NewValue as IList)[2].ToString());
                for (int j = 1; j <= DateTime.DaysInMonth(year, month); j++)
                {
                    if (j < 10)
                    {
                        days.Add("0" + j);
                    }
                    else
                        days.Add(j.ToString());
                }

                if (days.Count > 0)
                {
                    Date.RemoveAt(1);
                    Date.Insert(1, days);
                    this.ItemsSource = Date;
                }
            }
        }
        catch
        {

        }
    }
}

{% endhighlight %}

{% endtabs %}

**Step** **4** **:** We have defined each column headers “MONTH”, “DAY”, “YEAR”, “HOUR” and “MINUTE” using ColumnHeaderText property of SfPicker control. The below code demonstrates how to define header for each column of SfPicker control.

{% tabs %}

{% highlight c#}

public class DateTimePicker : SfPicker
{
    /// <summary>
    /// Headers API is holds the column name for every column in date picker
    /// </summary>
    /// <value>The Headers.</value>
    public ObservableCollection<string> Headers { get; set; }

    public DateTimePicker()
    {
        Headers = new ObservableCollection<string>();
        Headers.Add("MONTH");
        Headers.Add("DAY");
        Headers.Add("YEAR");
        Headers.Add("HOUR");
        Headers.Add("MINUTE");

        //SfPicker header text
        HeaderText = "SELECT A DATE & TIME";

        // Column header text collection
        this.ColumnHeaderText = Headers;
    }
}

{% endhighlight %}

{% endtabs %}

**Step** **5** **:** Finally we have enabled SfPicker footer, header and ColumnHeader using ShowFooter, ShowColumnHeader properties.


{% tabs %}

{% highlight c# %}

public DateTimePicker()
{
    //Enable Footer
    ShowFooter = true;

    //Enable SfPicker Header
    ShowHeader = true;

    //Enable Column Header of SfPicker
    ShowColumnHeader = true;
}

{% endhighlight %}

{% endtabs %}

**Step** **6** **:** We have added the DateTimePicker control in ViewDidLoad page. Please refer the below code snippets.

{ % tabs %}

{% highlight c#}

public partial class ViewController : UIViewController
{

    DateTimePicker dateTimePicker;

    public ViewController(IntPtr handle) : base(handle)
    {
        dateTimePicker = new DateTimePicker();
    }

    public override void ViewDidLoad()
    {
        base.ViewDidLoad();

        dateTimePicker.ColumnHeaderHeight = 70;
        dateTimePicker.PickerMode = PickerMode.Default;
        dateTimePicker.PickerHeight = 400;
        dateTimePicker.PickerWidth = 300;
        dateTimePicker.SelectedItem = dateTimePicker.StartDate;
        dateTimePicker.BackgroundColor = UIColor.White;
        dateTimePicker.Frame = new CoreGraphics.CGRect(0, 0, this.View.Frame.Width - 50, this.View.Frame.Height / 2);
        this.View.AddSubview(dateTimePicker);
    }

    public override void DidReceiveMemoryWarning()
    {
        base.DidReceiveMemoryWarning();
        // Release any cached data, images, etc that aren't in use.
    }

}

{% endhighlight %}

{% endtabs %}

We have attached the DateTimePicker sample for reference. Please download the sample from the following link.

Sample link: https://www.syncfusion.com/downloads/support/directtrac/general/ze/PickerLooping871534620.zip 