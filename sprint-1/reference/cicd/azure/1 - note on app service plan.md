# App Service Plan

An app always runs in an App Service Plan. An App Service Plan defines a set of compute resources for a web app to run.

When you create an App Service Plan in a certain region (for example, West Europe), a set of compute resources is created for that plan in that region. Whatever apps you put into this App Service Plan run on these compute resources as defined by your App Service Plan.

**Notice that apps that share an App Service Plan also share resources.**

More information can be found on this links:

* https://learn.microsoft.com/en-us/azure/app-service/overview-hosting-plans
* https://learn.microsoft.com/en-us/azure/app-service/app-service-plan-manage

## Free App Service Plans & Azure For Students

An Azure for Students account can only create one free App Service Plan per region.

See this link for all limitations:

*  https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/azure-subscription-service-limits#app-service-limits

## App Service Plan & Disk Usage

Our apps will run in an App Service Plan of the free tier by default. A free App Service Plan comes with 1GB of storage.

Normally, 1GB is more than enough but there are two ways to increase your available disk space:

* Use your free credits to create one App Service Plan in a paying tier (B1 gives 10GB of storage for example), and use this plan for all your apps.
* Define each app in a separate App Service Plan so that every app has 1GB of storage. If apps share the same App Service Plan, they also share the same storage. Every App Service Plan will have to be defined in a separate region.
    * In general, running apps in different regions is not the best idea. It can be a useful workaround if you have no more credits in your group to run a paying App Service Plan.