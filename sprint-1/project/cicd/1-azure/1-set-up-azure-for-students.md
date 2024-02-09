# Set up Azure for Students

In this course we will use Azure as a deployment platform for our environments.

Azure is a paying cloud platform, but as long as you have access to a student email, you can get free credits for Azure every year.

Each team should setup an Azure environment under the personal account of one team-member. This environment will be used to deploy your application so that it is publicly available.

We will do our best to minimize credit usage in this course. It can happen that you run out of credits (most probably due to a misconfiguration), in that case set-up a new environment under the account of a different team member. You will then need to change build pipelines so that they deploy to the new environment.

## 1. Acceptance Criteria

Your team has access to an Azure environment with student credit available.

## 2. Implementation Details

1. Go to [Azure for Students](https://azure.microsoft.com/en-us/free/students)
1. Click on the `Start free` button and follow the wizard (use your UCLL-account)
1. [Azure portal](https://portal.azure.com/) allows you to view your created resources and used credits
    * Normally the amount of credits should almost not decrease, since we will only use free or very cheap resources
1. Create [a Resource Group](https://learn.microsoft.com/en-us/azure/role-based-access-control/quickstart-assign-role-user-portal) for all resources under your Azure for Students subscription
    * Choose West Europe as the region
    * A Resource Group is a logical namespace for resources, we will add everything we create to the same resource group.
    * You can try to give access to other team members, but this is not necessary. The amount of actions we need to do directly on Azure is limited.

### Extremely Important Notice

**Do not fill in any payment information on Azure!!** 

* Without entering payment information, if your credits are spent you will lose access to your resources. 
* With payment information, if your credits are spent you will keep access but start receiving bills. Should you vastly misconfigure (overscale) your resources, the costs can be (very) high.

**Do not fill in any payment information on Azure!!** 