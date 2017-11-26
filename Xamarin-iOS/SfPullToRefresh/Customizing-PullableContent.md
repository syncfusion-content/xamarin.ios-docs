---
layout: post
title: Customizing PullableContent | SfPullToRefresh | Xamarin.iOS | Syncfusion
description: Customizing the PullableContent of SfPullToRefresh
platform: Xamarin.iOS
control: SfPullToRefresh
documentation: ug
--- 

# Customizing PullableContent

SfPullToRefresh supports various views as its pullable content. 

This section explains how to refresh the following views by hosting as a pullable content of SfPullToRefresh:

* [CollectionView](#collectionview) 
* [SfDataGrid](#sfdatagrid) 
* [Custom view](#custom-view) 

## CollectionView

SfPullToRefresh can host the CollectionView as its pullable content and refresh the view. 

### CollectionView customizations

Refer to the following code example for creating and customizing a CollectionView:

{% highlight c# %}

//MyViewController.cs

UICollectionView collectionView;
CollectionViewSource collectionViewSource;
UICollectionViewFlowLayout collectionViewFlowLayout;

public MyViewController()
{
    ....
    this.collectionViewFlowLayout = new UICollectionViewFlowLayout()
    {
        MinimumLineSpacing = 0.5f,
        ScrollDirection = UICollectionViewScrollDirection.Vertical,
    };
    this.collectionView = new UICollectionView(CGRect.Empty, collectionViewFlowLayout);
    this.collectionView.ShowsHorizontalScrollIndicator = false;
    this.collectionViewSource = new CollectionViewSource();
    this.collectionView.DataSource = this.collectionViewSource;
    this.collectionView.RegisterClassForCell(typeof(CollectionViewCell), CollectionViewCell.CellID);
    ....
}

{% endhighlight %}

The example code of the CollectionViewSource and the CollectionViewCell of the CollectionView are not displayed here. However, the source code of this sample can be downloaded here.

### Adapting CollectionView in SfPullToRefresh

To add CollectionView as a pullable content and to refresh the pullable content, refer to the following code example:

{% highlight c# %}

//MyViewController.cs

SfPullToRefresh pullToRefresh;

public MyViewController()
{
    ....
    pullToRefresh = new SfPullToRefresh(this);
    pullToRefresh.TransitionType = TransitionType.Push;
    pullToRefresh.Refreshing += PullToRefresh_Refreshing;
    pullToRefresh.PullableContent = collectionView;
    View.AddSubview(this.pullToRefresh);
    ....
}

private async void PullToRefresh_Refreshing(object sender, RefreshingEventArgs e)
{
    await Task.Delay(3000);
    this.collectionViewSource.repository.RefreshItemSource();
    this.collectionView.ReloadData();
    e.Refreshed = true;
}

//InboxRepository.cs 

private Random random;

public ObservableCollection<Mail> InboxItems{ get; set; }

public void RefreshItemSource()
{
    int count = random.Next(1, 6);

    for (int i = 0; i < count; i++)
    {
        int randomNumber = random.Next(0, 9);
        Mail mail = new Mail();
        mail.Sender = sender[random.Next(0, 24)];
        mail.Subject = subject[randomNumber];
        mail.Details = details[randomNumber];
        mail.BackgroundColor = colors[randomNumber];
        InboxItems.Insert(i, mail);
    }
}

{% endhighlight %}

The final output of the sample of SfPullToRefresh adapting CollectionView as its pullable content is as follows:

<div style="text-align:center" markdown="1">
![](CustomizingPullableContent_images/CollectionView_Refresh_iOS.gif)
</div>

## SfDataGrid

SfPullToRefresh can host the `SfDataGrid` as its pullable content and refresh it.

### SfDataGrid customizations

Click [here](https://help.syncfusion.com/xamarin-ios/sfdatagrid/getting-started) to explore SfDataGrid. Refer to the following code example to create and customize SfDataGrid:

{% highlight c# %}

//MyViewController.cs

SfDataGrid SfGrid;
GridGettingStartedViewModel viewModel;

public MyViewController()
{
    ....
    sfGrid = new SfDataGrid(this);
    SfGrid.ItemsSource = viewModel.OrdersInfo;
    SfGrid.HeaderRowHeight = 45;
    SfGrid.RowHeight = 45;
    viewModel = new GridGettingStartedViewModel();
    sfGrid.AutoGenerateColumns = false;
    GridGenerateColumns();
    sfGrid.ColumnSizer = ColumnSizer.Star;
    ....
}

void GridGenerateColumns()
{
    sfGrid.Columns.Add(new GridTextColumn() { MappingName = "OrderID", HeaderText = "Order ID" });
    sfGrid.Columns.Add(new GridTextColumn() { MappingName = "CustomerID", HeaderText = "Customer ID", TextAlignment = GravityFlags.CenterVertical });
    sfGrid.Columns.Add(new GridTextColumn() { MappingName = "Freight", Format = "C", CultureInfo = new CultureInfo("en-US"), TextAlignment = GravityFlags.Center });
    sfGrid.Columns.Add(new GridTextColumn() { MappingName = "ShipCity", HeaderText = "Ship City", TextAlignment = GravityFlags.CenterVertical });
}

{% endhighlight %}

The example code of the ViewModel is not displayed here. However, the source code of this sample can be downloaded here.

### Adapting SfDataGrid in SfPullToRefresh

To add SfDataGrid as a pullable content and to refresh the pullable content, refer to the following the code example: 

{% highlight c# %}

//MyViewController.cs

SfPullToRefresh pullToRefresh;

public MyViewController()
{
    ....
    pullToRefresh = new SfPullToRefresh(this);
    pullToRefresh.Refreshing += PullToRefresh_Refreshing;
    pullToRefresh.RefreshContentThreshold = 45;
    pullToRefresh.PullableContent = sfGrid;
    View.AddSubview(this.pullToRefresh);
    ....
}

private async void PullToRefresh_Refreshing(object sender, RefreshingEventArgs e)
{
    await Task.Delay(3000);
    viewModel.ItemsSourceRefresh();
    e.Refreshed = true;
}

{% endhighlight %}

The final output of the sample of SfPullToRefresh adapting SfDataGrid as its pullable content is as follows:

<div style="text-align:center" markdown="1">
![](CustomizingPullableContent_images/SfDataGrid_Refresh_iOS.gif)
</div>

## Custom view

A view can be customized and added as the pullable content of SfPullToRefresh. 

The code example of the customized view is as follows:

{% highlight c# %}

public class CustomView : UIView
{
    BaseView baseView;
    CustomScrollView customScrollView;
    UILabel cityLabel;

    public CustomView(BaseView view, CustomScrollView scrollView, UILabel city) : base()
    {
        baseView = view;
        customScrollView = scrollView;
        cityLabel = city;
        this.AddSubview(view);
        this.AddSubview(scrollView);
        this.AddSubview(city);
    }

    public override void LayoutSubviews()
    {
        base.LayoutSubviews();
        cityLabel.Frame = new CGRect(0, 20, this.Frame.Width, 50);
        baseView.Frame = new CGRect(0, (Frame.Height / 4), Frame.Width, Frame.Height / 2);
        customScrollView.Frame = new CGRect(0, this.Frame.Height - 150, this.Frame.Width, 150);
    }
}

{% endhighlight %}

The example code of the other custom views are not displayed here. However, the source code of this sample can be downloaded here.

### Adapting custom view in SfPullToRefresh

To add the above custom view as a pullable content and to refresh the pullable content, refer to the following code example:

{% highlight c# %}

public MyViewController()
{
    ....
    pullToRefresh = new SfPullToRefresh();
    //The custom view is set as the pullable content of SfPullToRefresh.
    pullToRefresh.PullableContent = customView;
    pullToRefresh.Refreshing += PullToRefresh_Refreshing;
    ....
}

private void PullToRefresh_Refreshing(object sender, RefreshingEventArgs e)
{
    NSTimer.CreateScheduledTimer(TimeSpan.FromSeconds(3), new Action<NSTimer>(delegate {
        baseView.model.Temperature = (NSString)new Random().Next(10, 40).ToString();
        baseView.UpdateBaseView();
        baseView.selectedView.SelectView();
        baseView.selectedView.UpdateTemperature();
        e.Refreshed = true;
    }));
}

{% endhighlight %}

The final output of the above sample is as follows:

<div style="text-align:center" markdown="1">
![](overview_images/WeatherData_Refresh_iOS.gif)
</div>

## Samples

Download the source code of the sample from the following link:

* [CollectionView](http://www.syncfusion.com/downloads/support/directtrac/general/ze/CollectionViewRefresh_UG969564409)
* [SfDataGrid](http://www.syncfusion.com/downloads/support/directtrac/general/ze/SfDataGridRefresh_UG701964204)
* [Custom view](http://www.syncfusion.com/downloads/support/directtrac/general/ze/WeatherDataRefresh_UG79834653)
