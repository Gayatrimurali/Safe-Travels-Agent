# Build and Enhance a Safe Travels Agent with Multi-Agent Orchestration

### Overall Estimated Duration: 1 Hour

## Overview

In this hands-on lab, you will build and configure a Safe Travels Agent using Microsoft Copilot Studio to assist employees with travel planning, policy queries, and approval workflows. The agent leverages multi-agent orchestration to seamlessly delegate specialized tasks, such as leave balance inquiries, to a dedicated Leave Manager Agent. By integrating with Microsoft Teams and Power Automate, you will create an intelligent, automated system that enhances employee experience and streamlines business processes.

## Objectives

By the end of this lab, you will:

- **Create and Deploy Safe Travels Agent:** Build a travel assistance agent using templates, integrate knowledge sources, and deploy to Microsoft Teams.

- **Implement Agent Flows for Business Automation:** Design and configure Power Automate flows that trigger travel approval processes and post notifications to Teams channels.

- **Build Multi-Agent Orchestration:** Create a specialized Leave Manager Agent and enable collaboration between multiple agents for comprehensive business solutions.

- **Test End-to-End Workflows:** Validate agent responses, flow executions, and cross-agent handoffs to ensure reliable operation.

## Prerequisites

- Basic Understanding of Conversational AI and Agentic AI Concepts
- Working Knowledge of Microsoft Copilot Studio
- Familiarity with Microsoft Teams and Power Platform

## Explanation of Components

- **Microsoft Copilot Studio:** Platform to build, configure, and manage conversational AI agents.

- **Dataverse:** Central data store for employee information, leave balances, and travel policies.

- **Power Platform Environment:** Secure workspace hosting agents, data tables, and workflows.

- **Power Automate:** Workflow automation engine for travel approval processes and Teams integration.

- **Microsoft Teams:** Collaboration hub where users interact with agents and receive approval notifications.

- **Multi-Agent Orchestration:** Framework enabling specialized agents to work together and route requests intelligently.

## Getting Started with the Lab

Welcome to your Build and Enhance a Safe Travels Agent with Multi-Agent Orchestration lab! We've prepared a seamless environment for you to explore and learn how to build, configure, and test intelligent travel assistance agents. This lab will guide you through creating AI agents, implementing business automation workflows, and establishing multi-agent orchestration to deliver a secure and efficient experience.

### Accessing Your Lab Environment

Once you're ready to dive in, your virtual machine and Lab guide will be right at your fingertips within your web browser.

![](../media/gs-travel-g5.png)

### Exploring Your Lab Resources

To get a better understanding of your Lab resources and credentials, navigate to the Environment tab.

![](../media/gs-leave-2.png)

### Utilizing the Split Window Feature

For convenience, you can open the Lab guide in a separate window by selecting the Split Window button from the top right corner

![](../media/gs-leave-3.png)

### Managing Your Virtual Machine

From the **Resources (1)** tab, you can easily **start, stop, restart, or connect (2)** to your virtual machine—your experience is in your hands!

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
