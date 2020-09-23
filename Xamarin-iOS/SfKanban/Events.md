---
layout: post
title: Events in Xamarin.iOS Kanban control
description: Kanban Events
platform: xamarin.ios
control: Kanban
documentation: ug
---

## Events

# ItemTapped

[`ItemTapped`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html) event is triggered when you tap on any card. The argument contains the following information.

* [`Column`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanTappedEventArgs.html#Syncfusion_SfKanban_iOS_KanbanTappedEventArgs_Column)          - Used to get the column of the card.
* [`Data`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanTappedEventArgs.html#Syncfusion_SfKanban_iOS_KanbanTappedEventArgs_Data) 			- Used to get the underlying model of the card.
* [`Index`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanTappedEventArgs.html#Syncfusion_SfKanban_iOS_KanbanTappedEventArgs_Index) 			- Used to get the index of the card in a column.
* [`ViewCell`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanTappedEventArgs.html#Syncfusion_SfKanban_iOS_KanbanTappedEventArgs_ViewCell)        - Used to get the tapped items view.

# DragStart

[`DragStart`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html) event is triggered when you start to drag a card. The argument contains the following information.

* [`Cancel`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragStartEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragStartEventArgs_Cancel)			- Used to cancel the drag action.
* [`Data`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEventArgs_Data)			- Used to get the underlying model of the card.
* [`KeepItem`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragStartEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragStartEventArgs_KeepItem)		- Determines whether to keep the dragged card in the source location itself, until it is dropped in a new location. When it is true, the preview of the card will be created for dragging.
* [`SourceColumn`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEventArgs_SourceColumn) 	- Used to get the source column of card.
* [`SourceIndex`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEventArgs_SourceIndex)		- Used to get the index of the card in source column.   

# DragEnd  

[`DragEnd`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html) event is triggered whenever the card is dropped or dragging action is canceled. The argument contains the following information.

* [`Cancel`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEndEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEndEventArgs_Cancel)			- Used to cancel the drag action.
* [`Data`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEventArgs_Data)			- Used to get the underlying model of the card.
* [`SourceColumn`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEventArgs_SourceColumn) 	- Used to get the source column of the card.
* [`SourceIndex`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEventArgs_SourceIndex)		- Used to get the index of the card in source column.
* [`TargetCategory`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEndEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEndEventArgs_TargetCategory) 	- Used to get the category of the column where the card is going to be dropped.
* [`TargetColumn`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEndEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEndEventArgs_TargetColumn)	- Used to get the current column which is the drop target for the card.
* [`TargetIndex`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEndEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEndEventArgs_TargetIndex)		- Used to get the index of the card in target column.

# DragEnter 

[`DragEnter`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html) event is triggered when a card enters into a column while dragging. The argument contains the following information.

* [`Cancel`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEnterEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEnterEventArgs_Cancel)				- Used to cancel the drag action.
* [`Data`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEventArgs_Data)				- Used to get the underlying model of the card.
* [`IsAboveMaximumLimit`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEnterEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEnterEventArgs_IsAboveMaximumLimit)	- Used to know whether the total cards count of the target column will be above the maximum limit if you drop the card in target column. You can define the maximum limit of the cards using KanbanColumn.MaximumLimit. 
* [`SourceColumn`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEventArgs_SourceColumn) 		- Used to get the source column of the card.
* [`SourceIndex`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEventArgs_SourceIndex)			- Used to get the index of the card in source column.
* [`TargetColumn`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEnterEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEnterEventArgs_TargetColumn)		- Used to get the column upon which the card enters.
* [`TargetIndex`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEnterEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEnterEventArgs_TargetIndex)			- Used to get the index of the card in target column.

# DragLeave 

[`DragLeave`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html) event is triggered when a card leaves a column while dragging. The argument contains the following information.

* [`Data`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEventArgs_Data)                - Used to get the underlying model of the card.
* [`IsBelowMinimumLimit`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragLeaveEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragLeaveEventArgs_IsBelowMinimumLimit) - Used to know whether the total cards count of the target column will be below the minimum limit if you remove the card from target column. You can define the minimum limit of the cards using KanbanColumn.MinimumLimit.
* [`SourceColumn`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEventArgs_SourceColumn)        - Used to get the source column of the card.
* [`SourceIndex`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEventArgs_SourceIndex)         - Used to get the index of the card in source column.
* [`TargetColumn`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragLeaveEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragLeaveEventArgs_TargetColumn)		- Used to get the column from which the card leaves.

# DragOver

[`DragOver`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html) event is triggered when a card is dragged to a new index within a column. The argument contains the following information.

* [`Cancel`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragOverEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragOverEventArgs_Cancel)			- Used to cancel the drag action.
* [`Data`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEventArgs_Data)			- Used to get the underlying model of the card.
* [`SourceColumn`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEventArgs_SourceColumn) 	- Used to get the source column of the card.
* [`SourceIndex`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragEventArgs_SourceIndex)		- Used to get the index of the card in source column.
* [`TargetColumn`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragOverEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragOverEventArgs_TargetColumn)	- Used to get the current column which is the drop target for the card.
* [`TargetIndex`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.KanbanDragOverEventArgs.html#Syncfusion_SfKanban_iOS_KanbanDragOverEventArgs_TargetIndex)		- Used to get the new index of the card in target column.

# ColumnsGenerated 

[`ColumnsGenerated`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html) event will be fired after the columns are generated automatically. You can access the auto-generated columns using [`SfKanban.ActualColumns`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfKanban.iOS.SfKanban.html#Syncfusion_SfKanban_iOS_SfKanban_ActualColumns) property.
