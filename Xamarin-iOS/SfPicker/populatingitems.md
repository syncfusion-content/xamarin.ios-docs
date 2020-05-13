---

layout: post
title: Populating Items with Syncfusion Picker control for Xamarin.iOS
description: A quick tour to populating items on Syncfusion Picker control for Xamarin.iOS platform.
platform: Xamarin.iOS
control: Picker
documentation: ug

---

# Populating items

This section explains about the ways of populating items for SfPicker control.

## Binding Data Source

SfPicker is bound the external data source to display the data's. It supports any collections that's implements the IEnumerable interface.

To bind data source in SfPIcker, set the `SfPicker.ItemSource` property as show in below code.

{% tabs %}

{% highlight C# %}

public partial class ViewController : UIViewController
{
    SfPicker pickerControl;

    public override void ViewDidLoad()
    {
        base.ViewDidLoad();
        #region SfPickerSettings
        pickerControl = new SfPicker();
        ColorInfo info = new ColorInfo();
        pickerControl.ItemsSource = info.Colors;
        View.AddSubview(pickerControl);
    }
}

{% endhighlight %}

{% endtabs %}

## Multi-Columns Items

The SfPicker automatically populate thw items as Multi-Column based on the Data Source.

Collection of items can be created and assigned to a Collection and each item Collection is a column of SfPicker.

The following code example illustrates about to populate Month, Day and Year values in each column of SfPicker.

{% tabs %}

{% highlight c# %}

    public partial class ViewController : UIViewController
    {
        protected ViewController(IntPtr handle) : base(handle)
        {
            // Note: this .ctor should not contain any initialization logic.
        }

        DatePicker datePicker;

        public override void ViewDidLoad()
        {
            base.ViewDidLoad();

            datePicker = new DatePicker();
            datePicker.ColumnHeaderHeight = 70;
            datePicker.PickerHeight = 400;
            datePicker.PickerWidth = 300;
            datePicker.PickerMode = PickerMode.Default;
            datePicker.BackgroundColor = UIColor.Blue;
            datePicker.SelectedItem = datePicker.StartDate;
            datePicker.Frame = new CoreGraphics.CGRect(0, 0, this.View.Frame.Width, this.View.Frame.Height);
            this.View.AddSubview(datePicker);
        }

        public override void DidReceiveMemoryWarning()
        {
            base.DidReceiveMemoryWarning();
            // Release any cached data, images, etc that aren't in use.
        }
    }

    public class DatePicker:SfPicker
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

        /// <summary>
        /// Headers API is holds the column name for every column in date picker
        /// </summary>
        /// <value>The Headers.</value>
        public ObservableCollection<string> Headers { get; set; }

        public ObservableCollection<object> StartDate;
        #endregion

        public DatePicker(IntPtr handle) : base(handle)
        {

            ObservableCollection<object> collection = new ObservableCollection<object>();

            //Select today dates
            collection.Add(CultureInfo.CurrentCulture.DateTimeFormat.GetMonthName(DateTime.Now.Date.Month).Substring(0, 3));
            if (DateTime.Now.Date.Day < 10)
                collection.Add("0" + DateTime.Now.Date.Day);
            else
                collection.Add(DateTime.Now.Date.Day.ToString());
            collection.Add(DateTime.Now.Date.Year.ToString());

            this.StartDate = collection;

            Months = new Dictionary<string, string>();
            Date = new ObservableCollection<object>();
            Day = new ObservableCollection<object>();
            Month = new ObservableCollection<object>();
            Year = new ObservableCollection<object>();
            Headers = new ObservableCollection<string>();
            Headers.Add("Month");
            Headers.Add("Day");
            Headers.Add("Year");
            HeaderText = "Date Picker";
            PopulateDateCollection();
            this.ItemsSource = Date;
            this.ColumnHeaderText = Headers;
            ShowFooter = true;
            ShowHeader = true;
            ShowColumnHeader = true;
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

            Date.Add(Month);
            Date.Add(Day);
            Date.Add(Year);
        }
    }

{% endhighlight %}

{% endtabs %}

You can get the multicolumn sample from the following link
Sample:

## Set items colors and font attributes customization

In SfPicker items text color and font for both selected and unselected item of SfPicker control can be customized as shown below.

### Selected item customization

#### Text Color

Selected item text color can be customized by setting `SfPicker.SelectedItemTextColor` property of SfPicker.

{% tabs %}

{% highlight c# %}

public partial class ViewController : UIViewController
    {
        SfPicker picker;
        
        public override void ViewDidLoad()
        {
            base.ViewDidLoad();

            picker = new SfPicker();
            picker.SelectedItemTextColor = UIColor.Red;
            this.View.AddSubview(picker);
        }
    }

{% endhighlight %}

{% endtabs %}

#### Font

This section will explains about the customization of selected item Font.

##### FontFamily

Selected item text FontFamily can be customized by setting  `SfPicker.SelectedItemFont` property of SfPicker.

{% tabs %}

{% highlight c# %}

public partial class ViewController : UIViewController
    {
        SfPicker picker;
        
        public override void ViewDidLoad()
        {
            base.ViewDidLoad();

            picker = new SfPicker();
            picker.SelectedItemFont = UIFont.FromName("sans-serif", 12f);;
            this.View.AddSubview(picker);
        }
    }

{% endhighlight %}

{% endtabs %}

### UnSelected item customization

#### Text color

Unselected item text color can be customized by setting `SfPicker.UnSelectedItemTextColor` property of SfPicker.

{% tabs %}

{% highlight c# %}

public partial class ViewController : UIViewController
    {
        SfPicker picker;
        
        public override void ViewDidLoad()
        {
            base.ViewDidLoad();

            picker = new SfPicker();
            picker.UnSelectedItemTextColor = UIColor.Blue;
            this.View.AddSubview(picker);
        }
    }

{% endhighlight %}

{% endtabs %}

### Font

This section will explains about the customization of UnSelected items Font.

##### FontFamily

JUnSelected item text FontFamily can be customized by setting  `SfPicker.UnSelectedItemFont` property of SfPicker.

{% tabs %}

{% highlight c# %}

public partial class ViewController : UIViewController
    {
        SfPicker picker;
        
        public override void ViewDidLoad()
        {
            base.ViewDidLoad();

            picker = new SfPicker();
            picker.UnSelectedItemFont = UIFont.FromName("sans-serif", 12f);;
            this.View.AddSubview(picker);
        }
    }

{% endhighlight %}

{% endtabs %}

## Adding custom view items

In SfPicker, the items can be customized with custom view of each item by adding all the item with custom view.

{% tabs %}

{% highlight c# %}

public partial class ViewController : UIViewController
    {
        UserInfo userInfo;
        SfPicker picker;
        
        public override void ViewDidLoad()
        {
            base.ViewDidLoad();

            userInfo = new UserInfo();
            picker.ItemsSource = userInfo.Users;
            picker.BackgroundColor = UIColor.Orange;
            picker.HeaderText = "Select a User";
            picker.HeaderBackgroundColor = UIColor.Black;
            picker.HeaderTextColor = UIColor.White;
            picker.ShowHeader = true;
            picker.ColumnHeaderText = "Users";
            picker.ShowColumnHeader = true;
            picker.ShowFooter = true;
            picker.PickerMode = PickerMode.Default;
            this.View.AddSubview(picker);
        }
    }

    public class UserInfo
    {
        private ObservableCollection<string> _user;

        public ObservableCollection<string> Users
        {
            get { return _user; }
            set { _user = value; }
        }

        public UserInfo()
        {
            Users = new ObservableCollection<string>();
            Users.Add("Maria Anders");
            Users.Add("Ana Trujillo");
            Users.Add("Ant Fuller");
            Users.Add("Martin King");
            Users.Add("Lenny Lin");
            Users.Add("John Carter");
            Users.Add("Laura King");
            Users.Add("Anne Wilson");
            Users.Add("Martin King");
            Users.Add("Gina Irene");
        }
    }

{% endhighlight %}

{% endtabs %}

You can get the sample from the following link.

Sample : https://www.syncfusion.com/downloads/support/directtrac/general/ze/DatePicker-1456447258.zip 