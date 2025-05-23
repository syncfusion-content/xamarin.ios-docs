---
layout: post
title: Overview of Syncfusion® license and unlock keys - Syncfusion®
description: Learn here about the Syncfusion® license and unlock keys and difference between license and unlock keys.
platform: xamarin.ios
control: Essential Studio<sup>®</sup>
documentation: ug
---


<style>
#license {
    font-size: .88em!important;
margin-top: 1.5em;     margin-bottom: 1.5em;
    background-color: #fbefca;
    padding: 10px 17px 14px;
}
</style>

# Syncfusion<sup>®</sup> Licensing Overview

We have introduced a new licensing system starting with version 16.2.0.x release of Essential Studio<sup>®</sup>. These modifications apply to all evaluators and only to paid customers who use NuGet packages from [nuget.org](https://www.nuget.org/). Starting with v16.2.0.x, if you use the evaluation installer or the NuGet feed to reference Syncfusion<sup>®</sup> assemblies, you must also include the corresponding platform and version license key in your projects.

## Difference between unlock key and license key

Please note that this license key is different from the installer unlock key that you might have used in the past and needs to be separately generated from Syncfusion<sup>®</sup> website. Refer [this](https://www.syncfusion.com/kb/8950/difference-between-the-unlock-key-and-licensing-key) KB article to know more about difference between the Syncfusion<sup>®</sup> Unlock Key and the Syncfusion<sup>®</sup> License Key.

Following licensing error will be shown if the license key is not registered in your projects, while using assemblies from evaluation installer or from the nuget.org.

<div id="license">

This application was built using a trial version of Syncfusion<sup>®</sup> Essential Studio<sup>®</sup>. Please include a valid license to permanently remove this license validation message. You can also obtain a free 30 day evaluation license to temporarily remove this message during the evaluation period. Please refer to this <a href="/xamarin-ios/licensing/overview">help topic</a> for more information

</div>

## Registering Syncfusion<sup>®</sup> license keys in Build server

| Source of Syncfusion<sup>®</sup> assemblies | Details | License Key needs to be registered? | Where to get license key from |
| ------------- | ------------- | ------------- | ------------- |
| **NuGet package** | If the Syncfusion<sup>®</sup> assemblies used in Build Server were from the Syncfusion<sup>®</sup> NuGet packages, then no need to install any Syncfusion<sup>®</sup> installer. We can directly use the required Syncfusion<sup>®</sup> NuGet packages at [nuget.org](http://nuget.org/). <br><br>But, if using NuGet packages from the [nuget.org](https://www.nuget.org/packages?q=syncfusion), then we should register the Syncfusion<sup>®</sup> license key in the application.| Yes | Use any developer license to [generate](https://help.syncfusion.com/xamarin-ios/licensing/how-to-generate) keys for Build Environments as well. |
| **Trial installer** | If the Syncfusion<sup>®</sup> assemblies used in Build Server were from Trial Installer, we should register the license key in the application for the corresponding version and platforms, to avoid trial license warning. | Yes | Use any developer trial license to [generate](https://help.syncfusion.com/xamarin-ios/licensing/how-to-generate) keys for Build Environments as well. |
| **Licensed installer** |If the Syncfusion<sup>®</sup> assemblies used in Build Server were from Licensed Installer, then there is no need to register the license keys.<br><br>You can [download](https://help.syncfusion.com/xamarin-ios/installation/web-installer/how-to-download#download-the-license-version) and [install](https://help.syncfusion.com/xamarin-ios/installation/web-installer/how-to-install) the licensed version of our installer. | No | Not applicable |

## See Also

* [How to Generate Syncfusion<sup>®</sup> Xamarin.iOS License Key?](https://help.syncfusion.com/xamarin-ios/licensing/how-to-generate)
* [How to Register Syncfusion<sup>®</sup> License Key in Xamarin.iOS Application?](https://help.syncfusion.com/xamarin-ios/licensing/how-to-register-in-an-application)
