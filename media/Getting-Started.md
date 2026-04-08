# Leave Management System with Microsoft Copilot Studio

### Overall Estimated Duration: 4 Hours

## Overview

In this hands-on lab, you will configure and explore a Leave Management Agent that automates employee leave applications, approvals, and balance tracking. The agent enforces strict security and business rules to ensure that requests are handled fairly, securely, and consistently. Employees can apply for leave, check their balance, and track past requests all through a controlled Dataverse integration that respects row-level security and manager approval flows.

## Objectives

By the end of this lab, you will be able to:

- **Set up Prerequisites for Leave Management Agent:** Provision a Power Platform environment, sign into Copilot Studio, and configure a new agent’s basic settings.

- **Design Advanced Topics:** Define the agent’s purpose, connect knowledge sources, and enable AI-powered responses for leave management.

- **Power Automate Approval Workflow:** Implement leave approval logic based on company policy and record finalized requests.

- **End-to-End Testing:** Execute prompts and scenarios to verify the agent updates leave request data correctly in Dataverse.

- **Publish & Share:** Publish the agent to Microsoft Teams and ensure it is accessible and responsive to basic prompts.

## Prerequisites

Participants should have:

- Basic Understanding of Agentic AI Concepts
- Working knowledge on Microsoft Copilot Studio

## Architecture

The Leave Management Agent is built on Microsoft Copilot Studio, integrated with Dataverse for storing leave requests and user data. Power Automate connects business logic by enabling automated approval workflows based on company policies. The agent is then published to Microsoft Teams, allowing employees to interact seamlessly within their work environment. This architecture ensures an end-to-end AI-driven solution that streamlines leave management.

## Architecture Diagram

![](../media/arch-v2.png)

## Explanation of Components

- **Microsoft Copilot Studio:** Platform to build, configure, and manage the leave management agent.

- **Dataverse:** Central data store for leave requests, user details, and policy records.

- **Power Platform Environment:** Secure workspace hosting the agent, data, and workflows.

- **Outlook:** Communication channel for sending leave notifications and approvals.

- **Microsoft Teams:** Collaboration hub where users interact directly with the agent.

## Getting Started with the Lab

Welcome to your Leave Management System with Microsoft Copilot Studio lab! We've prepared a seamless environment for you to explore and learn how to build, configure, and test an intelligent leave management agent. This lab will guide you through applying business rules, handling approvals, and integrating with Dataverse to deliver a secure and efficient experience.

### Accessing Your Lab Environment

Once you're ready to dive in, your virtual machine and Lab guide will be right at your fingertips within your web browser.

![](../media/gs-leave-1.png)

### Exploring Your Lab Resources

To get a better understanding of your Lab resources and credentials, navigate to the Environment tab.

![](../media/gs-leave-2.png)

### Utilizing the Split Window Feature

For convenience, you can open the Lab guide in a separate window by selecting the Split Window button from the Top right corner

![](../media/gs-leave-3.png)

### Managing Your Virtual Machine

From the **Resources (1)** tab, you can easily **start, stop, restart, or connect (2)** to your virtual machine. Your experience is in your hands!

![](../media/gs-leave-4.png)

## Let's Get Started with Power Apps Portal

1. In the JumpVM, click on the **Microsoft Edge** browser shortcut on the desktop.

   ![](../media/zgr-gt.png)

1. Open a new browser tab and navigate to the Power Apps portal by entering the following URL:

   ```
   https://make.powerapps.com/
   ```

1. On the **Sign into Microsoft** tab, enter the following email **(1)** in the email field, and then click **Next (2)** to proceed.

   - Email: **<inject key="AzureAdUserEmail"></inject>**

     ![](../media/gs-lab3-g2.png)

1. On the **Enter Temporary Access Pass** screen, enter the following **Temporary Access Pass**, and then click **Sign in (2)**.

   - Temporary Access Pass: **<inject key="AzureAdUserPassword"></inject>**

     ![](../media/gs-lab3-g3.png)
     
1. If you see the pop-up **Stay Signed in?**, click **No**.

   ![](../media/gs-4.png)

1. If the **Welcome to Power Apps** pop-up appears, leave the default country/region selection and click **Get started**.

   ![](../media/gs-travel-g1.png)

1. You have now successfully logged in to the Power Apps portal. Keep the portal open.

   ![](../media/gs-5.png)

   > **Note:** We are signing in to the Power Apps portal because it automatically assigns a Developer license, which is required to create and use a Developer environment in the next steps.

1. Open a new browser tab and navigate to the Power Platform admin center by entering the following URL:

   ```
   https://admin.powerplatform.microsoft.com
   ```

1. In the **Power Platform admin center**, select **Manage** from the left navigation pane.

   ![](../media/nd-d2-cor-g-1.png)

1. In the Power Platform admin center, select **Environments (1)** from the left navigation pane, and then choose **New (2)** to create a new environment.

   ![](../media/d2-coor-gs-g2.png)

1. In the **New environment** pane, configure the environment with the following settings, and then select **Next (3)**:

   - Select **Developer (1)** from the **Type** dropdown.
   - Enter **ODL_User <inject key="DeploymentID" enableCopy="false"></inject>'s Environment** in the **Name (2)** field.

      ![](../media/lev-mgmt-sb-gs-g1.png)

1. In the **Add Dataverse** pane, leave all settings as default, and then select **Save**.

   ![](../media/lev-mgmt-sb-gs-g2.png)

   > **Environment Foundation:** This step creates the foundational environment that will support your agents with company-specific data and knowledge sources.

   > **Note:** Environment provisioning may take 10-15 minutes to complete. Wait until the status shows as ready before proceeding.

   > **Note:** If you see an error stating that the environment list cannot be displayed, this is expected while the environment is being created in the background. After 10-15 minutes, refresh the browser and the environment should appear.

1. In the **Power Platform admin center**, select **Manage (1)**, choose **Environments (2)**, and then click **ODL_User <inject key="DeploymentID" enableCopy="false"/>'s Environment (3)**.

   ![](../media/uppowadminimg1.png)

1. In the environment page, click on **See all** under **S2S apps**.

   ![](../media/pro-activ-gg-g3.png)

1. In the next pane, click on **+ New app user**.

   ![](../media/uppowadminimg3.png)

1. In the create a new app user pane, under **App**, click on **+ Add an app**.

   ![](../media/pro-activ-gg-g4.png)

1. In the **Add an app from Microsoft Entra ID** pane, enter the URL provided below in the search box **(1)**, select the app from the results **(2)**, and then click **Add (3)**.

   ```
   https://cloudlabssandbox.onmicrosoft.com/cloudlabs.ai/
   ```

   ![](../media/pro-activ-gg-g5.png)

1. Under **Business unit**, enter **org (1)** in the search box, and then select the available business unit from the list **(2)**.

   ![](../media/pro-activ-gg-g6.png)

1. Beside **Security roles** click on **Edit** icon.

   ![](../media/pro-activ-gg-g7.png)

1. In the **Sync Permissions** pane, select **System Administrator (1)**, and then click **Save (2)**.

   ![](../media/pro-activ-gg-g8.png)

1. In the pop-up window, select **save**.

   ![](../media/pro-activ-gg-g9.png)

1. Review all the details and click on **Create**.

   ![](../media/pro-activ-gg-g10.png)

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.

Learner Support Contacts:

- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

Now, click on the **Next** from lower right corner to move on next page.

   ![](../media/a-gs-g1.png)

## Happy Learning!!
