---
title: Set up Dynamics 365 Customer Insights - Journeys
description: How to run the setup wizard for Dynamics 365 Customer Insights - Journeys.
ms.date: 08/23/2023
ms.topic: article
author: alfergus
ms.author: alfergus
search.audienceType: 
  - admin
  - customizer
  - enduser
---

# Set up Dynamics 365 Customer Insights - Journeys

[!INCLUDE[consolidated-sku-rtm-only](./includes/consolidated-sku-rtm-only.md)]

This article explains how to set up a new Customer Insights - Journeys environment.

## Prerequisites and requirements

To run the setup wizard, you must meet all the following requirements:

- You must already have a Microsoft 365 tenant.
- An unconfigured Customer Insights - Journeys app must be available on your tenant.
- You must not already have a Customer Insights - Journeys app installed on your Dynamics 365 environment. You can have at most one Customer Insights - Journeys app per environment, and each Customer Insights - Journeys app can only be used with one Dynamics 365 environment.
- You must sign into your tenant with a user account that has all the following:
   - A security role (such as _Global admin_ or [_Service support admin_](/power-platform/admin/use-service-admin-role-manage-tenant)) that allows you to modify the target Dynamics 365 environment. (If you're reinstalling Customer Insights - Journeys on an environment where Customer Insights - Journeys was previously installed, then _Service support admin_ users [_Dynamics 365 administrator_ or _Power Platform administrator_] must use the same user ID as was used for the initial install. If you're not sure which ID was used for the initial install, or if you're getting errors, then try to install as a _Global admin_.)
   - Permissions to register applications in Azure. The global administrator always has this right, but other accounts can also have it. See [Do I have permissions to register applications on Azure?](setup-troubleshooting.yml#register-apps-azure) for information about how to confirm this setting for your account.
   - A Dynamics 365 license with the _System Administrator_ security role assigned on your target Dynamics 365 environment. (The Customer Insights - Journeys license agreement doesn't legally require the installing user to have this license, but a known technical issue currently makes it necessary.)
- You must be located in a country/region where the product is supported. To read the latest list of countries/regions where you can use Customer Insights - Journeys, download the [Microsoft Dynamics 365 International Availability](https://go.microsoft.com/fwlink/p/?linkid=875097) document (PDF).
- Close all other browser windows and tabs before starting.
- Clear your browser cache before starting.

If you run into trouble while working with the setup wizard, see the [Administration and setup FAQ](setup-troubleshooting.yml) for some possible solutions.

> [!IMPORTANT]
> Your system is constrained by certain limits and quotas that apply to the number of contacts you can market to, monthly email messages you can send, Litmus previews you can view, and more. Please familiarize yourself with the terms and limits of the product before you begin to use it. The limits are different based on whether you are running a trial or subscribed version of the product.
> 
> - For subscribed (paid) versions, please download the [Microsoft Dynamics 365 Licensing Guide](https://go.microsoft.com/fwlink/p/?linkid=866544) and visit the [Fair use policy](fair-use-policy.md) page.
> - For trials, see [Dynamics 365 Customer Insights - Journeys limits for trials](trial-preview-limits.md).
> 
> You can monitor your usage levels by going to  **Settings**  >  **Advanced settings**  >  **Other settings**  >  **Quota limits**  in Customer Insights - Journeys. More information: [Quota limits](quota-management.md)

## Add a Customer Insights - Journeys app to your Microsoft 365 tenant

There are many ways to add one or more Customer Insights - Journeys apps to your Microsoft 365 tenant. For example, you can purchase it from the [Dynamics 365 Customer Insights - Journeys overview page](https://dynamics.microsoft.com/marketing/overview/), or by going to **Billing** > **Purchase services** in your Microsoft 365 admin center, or by contacting your Microsoft sales representative or channel partner. On purchasing a license, an unconfigured Customer Insights - Journeys app will be automatically added to your tenant.

You can have any number of Customer Insights - Journeys apps available on your tenant. Initially, each of these apps will be unconfigured and unassigned to any Dynamics 365 environment. Later, you'll run the Customer Insights - Journeys setup wizard to assign the app to an environment and configure it.

<a name="run-wizard"></a>

## Run the Customer Insights - Journeys setup wizard

After purchasing your license for Customer Insights - Journeys, you'll have an unconfigured Customer Insights - Journeys app available on your tenant, but you still need to set it up for use. The Customer Insights - Journeys setup wizard will help you review all the relevant privacy policies and set up and integrate its various elements.

> [!TIP]
> If you have not installed other apps on the [Microsoft Power Platform admin center](/power-platform/admin/), you will need to create an environment before you can run the Customer Insights - Journeys setup wizard. Learn more: [Create and manage environments in the Power Platform admin center](/power-platform/admin/create-environment).

To set up a new Customer Insights - Journeys environment:

1. Go to [admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com) and sign in to your Microsoft 365 tenant using an administrator account that has a Customer Insights - Journeys license assigned.

1. Go to **Resources** > **Dynamics 365 apps** on the left navigation pane.

   ![Navigate to the Dynamics 365 apps.](media/purchase-setup-ppac-apps2.png "Navigate to the Dynamics 365 apps")

1. Find and select an unconfigured Customer Insights - Journeys application in the **Dynamics 365 apps** list. Then select the three dots between the **Name** and the **Status** columns for the Customer Insights - Journeys application.

    ![Choose an app and then select the Manage or Details link.](media/purchase-setup-ppac-manage.png "Choose an app and then select the Manage or Details link")

    - To launch the Customer Insights - Journeys setup wizard, choose **Manage** from the pop-up menu. A message will pop up informing you that you're going to the Customer Insights - Journeys admin page. To go to the page, select **OK**.
    
      ![Customer Insights - Journeys admin page prompt.](media/purchase-setup-ppac-prompt.png "Customer Insights - Journeys admin page prompt")
    
    - To view more details about the selected Customer Insights - Journeys application, choose **Details** from the pop-up menu.

    You may have more than one type of application available, so be sure to pick the one that meets your present needs. Both types of applications present the same setup wizard, as described in this procedure. They're identified as follows:

    - **Dynamics 365 Customer Insights - Journeys Application**: This is a full Customer Insights - Journeys application, including both solutions and services. It's intended for production use, but can also be used during development and testing.
    - **Dynamics 365 Customer Insights - Journeys - Solution Only**: This application provides the Customer Insights - Journeys solutions, including all database entities, but not the services. This means that marketing capabilities aren't available. It provides limited functionality but can be installed on as many test or development environments as needed for no additional charge. More information: [How Customer Insights - Journeys is licensed](purchase.md#how-licensed).

   > [!NOTE]
   > If you see the Customer Insights - Journeys app listed several times, you probably have several Customer Insights - Journeys apps available on your tenant. Customer Insights - Journeys apps that are already configured show an environment ID appended to the app name and show a value of **Configured** in the **Status** column. Customer Insights - Journeys apps that aren't assigned show a value of **Not configured** in the **Status** column and don't include an environment ID in their name.

1. The setup wizard launches, which you'll use to make initial settings for the app. The first page of the wizard lets you choose where you'll install the app and to choose whether to set up a portal to run your marketing pages and event website.

    > [!div class="mx-imgBorder"]
    > ![Choose an organization and name your portal.](media/setup-form-3-2.png)

1. From the top drop-down list, select the Dynamics 365 organization where you want to add Customer Insights - Journeys. (A Dynamics 365 *organization* is another name for a Dynamics 365 *environment*.)

1. Select one of the following **Web hosting** options (you can easily [change this later](portal-optional.md), at any time):

    - **Use your own webserver**: Select this option if you'll run your landing pages and event website on an external webserver or CMS system. This option doesn't require a portals license and won't install a portals trial. If you're not sure whether you'll need a portal, then you can choose this option for now and then come back and change it later if needed.
    - **Use Dynamics 365 Portals or a Power Apps portal**: Select this option if you'll run your landing pages and event website on a dedicated Dynamics 365 or Power Apps Portal running on your tenant and linked to  your Customer Insights - Journeys environment. Portals are licensed separately. If you already have an unconfigured Dynamics 365 Portals or a Power Apps portal license on your tenant, then Customer Insights - Journeys will claim that license and integrate with it. If you don't have any Dynamics 365 Portals or Power Apps portals licenses available, then the setup wizard will create a trial Power Apps Portals environment and integrate with that. The trial is free, but expires in 30 days, after which you must either begin paying for it or stop using it. (Power Apps Portals licenses are priced according to consumption (logins and page loads), while Dynamics 365 Portals licenses are priced per environment.) For details about portal licensing, see the [Power Apps and Flow licensing FAQ](/power-platform/admin/powerapps-flow-licensing-faq#can-you-share-more-details-regarding-the-new-powerapps-portals-licensing).

    More information: [Integrate Customer Insights - Journeys with a CMS system or Power Apps portals](portal-optional.md)

    > [!NOTE]
    > Power Apps portals aren't available in all countries/regions. If this applies to you, then the **Use Dynamics 365 Portals or a Power Apps portal** option won't be available and you'll see a notice here instead. For more information about how to run Customer Insights - Journeys without a portal, and how to switch to a portal if they later become available in your country/region, see [Integrate Customer Insights - Journeys with a CMS system or Power Apps portal](portal-optional.md).

1. If you selected to **Use Dynamics 365 Portals or a Power Apps portal**, then enter a prefix for your portal URL in the field provided (under **Where do you want to host your webpage?**). You can also see what the full URL will be here. All your portals are hosted on your tenant, which uses a Microsoft-owned domain name, plus the subdomain name that you choose here. Your contacts and customers can see the URL when they open a portal, so you should choose a subdomain name that they'll recognize, such as your organization's name. The subdomain that you choose must also be unique among all other subdomains in the same tenant; you'll be notified to try again if you pick one that's already in use. If you want to reuse a name that's reported as already in use, then you can reclaim it by resetting the relevant portal and then removing the binding to the existing name as described in [Reset any Power Apps portals connected to the uninstalled Customer Insights - Journeys app](uninstall-marketing.md#reset-portal).

1. Select  **Setup**  to start setting up the app. A page will open that tracks the setup progress, which typically takes about three hours to set up a paid environment.

## Privacy notice

[!INCLUDE[cc-privacy-marketing-fre](./includes/cc-privacy-marketing-fre.md)]

[!INCLUDE[footer-include](./includes/footer-banner.md)]