---
layout: post
title: Download and Installation in Mac | Xamarin.iOS | Syncfusion
description: Download and Installation in Mac
platform: xamarin.ios
control: Download and Installation 
documentation: ug
---

# Mac

## Download directly from website

You can also download the complete Xamarin.iOS component from [here](https://www.syncfusion.com/downloads/latest-version).

**MAC Installer (pkg)**

The following procedure illustrates how to install the installer of Syncfusion Xamarin components in Mac.

1. Double-click the Syncfusion Essential Studio for Xamarin Setup file. The Self-Extractor wizard opens, click continue.
2. After reading the terms in Software License Agreement, click continue.
3. Click Agree in the dialog box that appears to continue the installation.
4. Select a destination to install the software and click continue.
5. Choose the installation location and samples installation.
6. To install it in the displayed default location, click Install.
7. Click Close. The NuGet and samples locations are launched automatically.

### Explore the libraries package

You can find the Syncfusion libraries, samples and NuGet when extracting the downloaded zip package or from the installed location in Mac.

{Essential Studio installed location}\Syncfusion\Essential Studio\16.2.0.41\Xamarin

* **"lib"** folder - e.g., /Users/labuser/Documents/Syncfusion/16.2.0.41/Xamarin/lib

   It contains all the required libraries for Xamarin.iOS, Xamarin.Android, and Xamarin.Forms projects.

* **"nuget"** folder - e.g., /Users/labuser/Documents/Syncfusion/16.2.0.41/nuget

   It contains the above libraries as NuGet packages. The same NuGet packages also can be configured from online [nuget.org](https://api.nuget.org/v3/index.json).

* **"sample"** folder - e.g., /Users/labuser/Documents/Syncfusion/16.2.0.41/sample

   It contains the sample applications for our controls in Xamarin.iOS platforms in iOS folder.

### Add reference to the project

You can then add the assembly references to the Xamarin.iOS. The following is the location where you can locate assembly for Chart control and you can find assemblies for the other controls also from the same location.

lib\ios-unified\Syncfusion.SfChart.iOS.dll

I> After adding the reference, currently, an additional step is required for iOS and UWP projects. For example, if we are using SfKanban, we need to call the Init method of SfKanbanRenderer as shown in this [KB article](https://www.syncfusion.com/kb/7171).