---
layout: post
title: Pull To Refresh | SfDataGrid | Xamarin.iOS | Syncfusion
description: How to perform pull to refresh and it's properties and customizations in a SfDataGrid.
platform: xamarin.ios
control: SfDataGrid
documentation: UG
---

# Pull To Refresh

SfDataGrid lets you to enable the PullToRefresh option by setting the [SfDataGrid.AllowPullToRefresh](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~AllowPullToRefresh.html) property to `true` and by setting the [SfDataGrid.PullToRefreshCommand](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~PullToRefreshCommand.html) property. When the PullToRefresh is enabled, the SfDataGrid provides support for refreshing the data source in the runtime while doing the PullToRefresh action. 

## PullToRefreshCommand

SfDataGrid lets you refresh the data in view in runtime by triggering an `ICommand` binded to the `SfDataGrid.PullToRefreshCommand` property. While you perform PullToRefresh action, if the progress bar meets 100 %, then this command is triggered to refresh the records in view. 

You need to set the [SfDataGrid.IsBusy](http://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfDataGrid.iOS~Syncfusion.SfDataGrid.SfDataGrid~IsBusy.html) property to `true` before refreshing the records to notify the grid that PullToRefresh action is being performed and set the property to false after the view is refreshed. You can also alter the time for the PullToRefresh animation from the sample by setting a delay based on your requirement.

The following code example illustrates how to enable and perform PullToRefresh operation in SfDataGrid.

{% tabs %}

{% highlight c# %}
//Enable PullToRefresh in SfDataGrid
dataGrid.AllowPullToRefresh = true;
dataGrid.PullToRefreshCommand = new Command(ExecutePullToRefreshCommand);
 
private async void ExecutePullToRefreshCommand()
{
    this.dataGrid.IsBusy = true;
    await Task.Delay(new TimeSpan(0, 0, 5));
    viewModel.ItemsSourceRefresh ();
    this.dataGrid.IsBusy = false;
} 

//ViewModel.cs
internal void ItemsSourceRefresh()
{
    int count = random.Next (1, 6);

    for (int i = 11000; i < 11000 + count; i++) {
        int value = i + random.Next (100, 150);
        this.OrdersInfo.Insert (0, order.RefreshItemsSource (value));
    }
} 

//Command.cs
public class Command : ICommand
{
    private Action execute;
    private bool canExecute = true;

    public event EventHandler CanExecuteChanged;

    public Command(Action action)
    {
        execute = action;
    }

    public bool CanExecute(object parameter)
    {
        return canExecute;
    }

    public void Execute(object parameter)
    {
        changeCanExecute(true);
        execute.Invoke();
    }

    private void changeCanExecute(bool canExecute)
    {
        this.canExecute = canExecute;
        if (CanExecuteChanged != null)
            CanExecuteChanged(this, new EventArgs());
    }
}
{% endhighlight %}

{% endtabs %}

Running the application renders the following output.

![SfDataGrid_PullToRefresh](SfDataGrid_images/PullToRefresh.png)

## Host SfDataGrid inside SfPullToRefresh

SfPullToRefresh is a refresh control that allows you to interact and refresh the view loaded in it. When the SfDataGrid is hosted inside the SfPullToRefresh, it is used to refresh the item while performing the pull to refresh action. 

For more details and code example for hosting the SfDataGrid inside SfPullToRefresh, refer [here](https://help.syncfusion.com/xamarin-ios/sfpulltorefresh/customizing-pullablecontent#sfdatagrid)

The final output will look like on iOS, Android and Windows Phone devices as shown below.

![SfDatagrid_Refresh](SfDataGrid_images/SfDatagrid_Refresh_iOS.gif)
