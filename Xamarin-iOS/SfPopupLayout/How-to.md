---
layout: post
title: Popup Layouts | SfPopupLayout |Xamarin.iOS | Syncfusion
description: Layouts in SfPopupLayout
platform: Xamarin.iOS
control: SfPopupLayout
documentation: ug
--- 

# How to 

## Hide the header in the SfPopupLayout 

The SfPopupLayout allows hiding the header by using the [SfPopupLayout.PopupView.ShowHeader](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpopuplayout/Syncfusion.SfPopupLayout.iOS~Syncfusion.iOS.PopupLayout.PopupView~ShowHeader.html) property. The default value of this property is `true`.

To hide the header in the SfPopupLayout, follow the code example.

{% highlight c# %}

//MyViewController.cs

public MyViewController()
{
    ....
    popupLayout = new SfPopupLayout();
    popupLayout.Content = GetContentOfPopup();
    popupLayout.PopupView.ShowHeader = false;
    this.View.AddSubview(popupLayout);
    ....
}

{% endhighlight %}

Executing the above codes renders the following output in an iOS device.

![](PopupLayout_images/ShowHeader_False.png)

## Hide the footer in the SfPopupLayout 

The SfPopupLayout allows hiding the footer by using the [SfPopupLayout.PopupView.ShowFooter](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpopuplayout/Syncfusion.SfPopupLayout.iOS~Syncfusion.iOS.PopupLayout.PopupView~ShowFooter.html) property. The default value of this property is `true`.

To hide the footer in the SfPopupLayout, follow the code example.

{% highlight c# %}

//MyViewController.cs

public MyViewController()
{
    ....
    popupLayout = new SfPopupLayout();
    popupLayout.Content = GetContentOfPopup();
    popupLayout.PopupView.ShowFooter = false;
    this.View.AddSubview(popupLayout);
    ....
}

{% endhighlight %}

Executing the above codes renders the following output in an iOS device.

![](PopupLayout_images/ShowFooter_False.png)

## Hide the Close icon in the SfPopupLayout 

The SfPopupLayout allows hiding the Close icon by using the [SfPopupLayout.PopupView.ShowCloseButton](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpopuplayout/Syncfusion.SfPopupLayout.iOS~Syncfusion.iOS.PopupLayout.PopupView~ShowCloseButton.html) property. The default value of this property is `true`.

To hide the Close icon in SfPopupLayout, follow the code example.

{% highlight c# %}

//MyViewController.cs

public MyViewController()
{
    ....
    popupLayout = new SfPopupLayout();
    popupLayout.Content = GetContentOfPopup();
    popupLayout.PopupView.ShowCloseButton = false;
    this.View.AddSubview(popupLayout);
    ....
}

{% endhighlight %}

Executing the above codes renders the following output in an iOS device.

![](PopupLayout_images/ShowCloseButton_False.png)

## Loading SfPopupLayout in GridTappedEvent of SfDataGrid

Sfpopuplayout allows you to open popup in the grid tapped event of SfDataGrid

Refer the below code example to show the popup in Grid tapped event.

{% highlight c# %}

using Syncfusion.iOS.PopupLayout;

namespace GettingStarted
{
    public class MyViewController:UIViewController
    {
        SfPopupLayout popupLayout;
        SfDataGrid dataGrid;
        ViewModel viewModel;

        public MyViewController()
        {
            dataGrid = new SfDataGrid();
            viewModel = new ViewModel();
            dataGrid.ItemsSource = viewModel.OrdersInfo;
            dataGrid.GridTapped += DataGrid_GridTapped;

            popupLayout = new SfPopupLayout();
            popupLayout.Content = dataGrid;

            this.View.AddSubview(popupLayout);
        }
        
        private void DataGrid_GridTapped(object sender, GridTappedEventArgs e)
        {
            popupLayout.Show();
        }

        public override void ViewDidLayoutSubviews()
        {
            base.ViewDidLayoutSubviews();
            popupLayout.Frame = new CGRect(0, 20, this.View.Frame.Width, this.View.Frame.Height - 20);
        }
    }
}
{% endhighlight %}

Executing the above codes renders the following output in an iOS device.

![](PopupLayout_images/PopupInDataGrid.png)

## Loading SfPopupLayout in TouchesEnded event of UITableView

SfPopupLayout allows you to open it in the TouchesEnded event of UITableView.

Refer the below code example to show the popup in TouchesEnded event.

{% highlight c# %}

// CustomViewController.cs

public class CustomViewController:UIViewController
{
    UITableView tableView;
    ContactsViewModel viewModel;
    DataSource sfDataSource;
    internal static SfPopupLayout popupLayout;
   
    public CustomViewController()
    {
        tableView = new UITableView();
        tableView.RowHeight = 70;
       
        viewModel = new ContactsViewModel();
        sfDataSource = new DataSource();
        sfDataSource.Source = viewModel.ContactsList;
        tableView.Source = new PopupTableViewSource(sfDataSource);
      
        popupLayout = new SfPopupLayout();
        popupLayout.Content = tableView;
        this.View.BackgroundColor = UIColor.White;
        this.View.AddSubviews(popupLayout);
    }
   
    public override void ViewDidLayoutSubviews()
    {
        popupLayout.Frame = new CGRect(0, 20, this.View.Frame.Width, this.View.Frame.Height);
        
        base.ViewDidLayoutSubviews();
    }
}
{% endhighlight %}

{% highlight c# %}

// PopupContactCell.cs

public class PopupContactCell : UITableViewCell
{
    public override void TouchesEnded(NSSet touches, UIEvent evt)
    {
        base.TouchesEnded(touches, evt);
        CustomViewController.popupLayout.PopupView.ContentView = GetCustomPopupView();
        CustomViewController.popupLayout.Show();
       
    }
    private UIView GetCustomPopupView()
    {
        popupContentView = new UILabel();
        popupContentView.Text = "TableView items are tapped.";
        popupContentView.TextColor = UIColor.Black;
        popupContentView.Font = UIFont.SystemFontOfSize(16);        
        popupContentView.BackgroundColor = UIColor.White;
        popupContentView.TextAlignment = UITextAlignment.Center;
        return popupContentView;
    }
    #endregion
}
{% endhighlight %}

Executing the above codes renders the following output in an iOS device.

![](PopupLayout_images/PopupInTableView.png)

## Loading UITableView as a content view of SfPopupLayout

SfPopupLayout allows you to load UITableView as a content of the popup.

Refer the below code example to load UITableView in SfPopupLayout.

{% highlight c# %}

// CustomViewController.cs

public class CustomViewController : UIViewController
{
    UITableView tableView;
    ContactsViewModel viewModel;
    DataSource sfDataSource;
    internal static SfPopupLayout popupLayout;
    UIView view;
    UIButton showPopupButton;
    public CustomViewController()
    {
        tableView = new UITableView();
        tableView.RowHeight = 70;

        viewModel = new ContactsViewModel();
        sfDataSource = new DataSource();
        sfDataSource.Source = viewModel.ContactsList;
        tableView.Source = new PopupTableViewSource(sfDataSource);
     
        showPopupButton = new UIButton();
        showPopupButton.SetTitle("CLICK TO SHOW POPUP", UIControlState.Normal);
        showPopupButton.SetTitleColor(UIColor.Black, UIControlState.Normal);
        showPopupButton.BackgroundColor = UIColor.LightGray;
        showPopupButton.TouchDown += ShowPopupButton_TouchDown;
        
        view = new UIView();
        view.BackgroundColor = UIColor.White;
        view.AddSubviews(showPopupButton);

        popupLayout = new SfPopupLayout();
        popupLayout.Content = view;
        this.View.BackgroundColor = UIColor.White;
        this.View.AddSubviews(popupLayout);
    }
    private void ShowPopupButton_TouchDown(object sender, EventArgs e)
    {
        popupLayout.PopupView.HeaderTitle = "TableView";
        popupLayout.PopupView.ContentView = tableView;
        popupLayout.Show();
    }
    public override void ViewDidLayoutSubviews()
    {
        popupLayout.Frame = new CGRect(0, 20, this.View.Frame.Width, this.View.Frame.Height);
        showPopupButton.Frame = new CGRect(0, 20, this.View.Frame.Width, 40);
        base.ViewDidLayoutSubviews();
    }
}
{% endhighlight %}

Executing the above codes renders the following output in an iOS device.

![](PopupLayout_images/TableViewInpopup.png)