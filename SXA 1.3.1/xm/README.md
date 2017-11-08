# Sitecore Experience Accelerator module for Sitecore XM Environment


This template deploys Sitecore Experience Accelerator and PowerShell Extensions modules into a Sitecore XM Environment.

## Parameters

The **deploymentId** parameter is filled in by the PowerShell script.

| Parameter                                    | Description
-----------------------------------------------|------------------------------------------------
| sqlServerLogin                               | The name of the administrator account for the newly created Azure SQL server.
| sqlServerPassword                            | The password for the administrator account for Azure SQL server.
| cdSxaMsDeployPackageUrl                      | The blob storage URL of Sitecore Experience Accelerator 1.3 rev. 170519 for 8.2.scwdp.zip.
| cmSxaMsDeployPackageUrl                      | The blob storage URL of Sitecore Experience Accelerator 1.3 rev. 170519 for 8.2 CD.scwdp.zip
| speMsDeployPackageUrl                        | The blob storage URL of Powershell Extensions-4.5 for Sitecore 8.scwdp.zip.

## Deploying as part of Sitecore deployment

In order to configure Sitecore deployment parameters to include Sitecore Experience Accelerator:

  * Configure Bootloader module according to [Modules.md](../../Modules.md)
  * Add the following snippet to the `modules` parameter:

```JSON
{
    "name": "sxa",
    "templateLink": "https://raw.githubusercontent.com/Sitecore/sitecore-azure-quickstart-templates/master/SXA/xm/azuredeploy.json",
    "parameters": {
        "cdSxaMsDeployPackageUrl" : "<URL of the WDP file Sitecore Experience Accelerator * CD.scwdp.zip>",
        "cmSxaMsDeployPackageUrl" : "<URL of the WDP file Sitecore Experience Accelerator *.scwdp.zip>",
        "speMsDeployPackageUrl" : "<URL of the WDP file Sitecore PowerShell Extensions *.scwdp.zip>"
    }
}
```
