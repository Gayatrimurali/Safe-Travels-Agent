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

![](../media/eng16.png)

### Exploring Your Lab Resources

To get a better understanding of your Lab resources and credentials, navigate to the Environment tab.

![](../media/gs-leave-2.png)

### Utilizing the Split Window Feature

For convenience, you can open the Lab guide in a separate window by selecting the Split Window button from the top right corner

![](../media/eng18.png)

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

1. If the **Welcome to Power Apps** pop-up appears, leave the default country/region selection and select **Get started**.

   ![](../media/eng1.png)

1. You have now successfully logged in to the Power Apps portal. Keep the portal open.

   ![](../media/eng2.png)

   > **Note:** We are signing in to the Power Apps portal because it automatically assigns a Developer license, which is required to create and use a Developer environment in the next steps.

1. In the Power Apps portal, select **Tables (1)** from the left menu and select **Create a database (2)**.

   ![](../media/eng3.png)

   >**Note:** If you are not able to see **Create Database** option and you are able to see some tables already, please continue from **Step 10**.

1. In the new pane for creating a new database, select **Create my Database**.

   ![](../media/eng4.png)

1. Once done, select **Create with Excel or .CSV file**.

   ![](../media/eng5.png)

1. In the pop-up window to create an environment, select **Create**. This will create a new Power Platform developer environment.

   > **Note:** If you see a message stating you don’t have permission to create here, wait for a few minutes and refresh the page, as it may take some time for the environment to be ready.
   
1. If you are directly navigated to the **Upload an Excel or .CSV file pane**, please cancel the process.

1. Open a new browser tab and navigate to the Power Platform admin center by entering the following URL:

   ```
   https://admin.powerplatform.microsoft.com
   ```

1. In the **Power Platform admin center**, select **Manage (1)**, choose **Environments (2)**, and then select **ODL_User <inject key="DeploymentID" enableCopy="false"/>'s Environment (3)**.

   ![](../media/eng6.png)

   >Note: If you’re unable to see any environments, it may still be getting created in the background. This is expected behavior in Power Platform. Please wait 15–20 minutes and refresh the page to view the environment.

1. On the environment page, select **See all** under **S2S apps**.

   ![](../media/eng7.png)

1. In the next pane, select **+ New app user**.

   ![](../media/eng8.png)

1. In the **Create a new app user** pane, under **App**, select **+ Add an app**.

   ![](../media/eng9.png)

1. In the **Add an app from Microsoft Entra ID** pane, enter the URL provided below in the search box **(1)**, select the app from the results **(2)**, and then select **Add (3)**.

   ```
   https://cloudlabssandbox.onmicrosoft.com/cloudlabs.ai/
   ```

   ![](../media/eng10.png)

1. Under Business Unit, click on the text input field to view the available options, and then select any one of the listed business units.

   ![](../media/eng11.png)

1. Next to **Security roles**, select the **Edit** icon.

   ![](../media/eng12.png)

1. In the **Sync Permissions** pane, select **System Administrator (1)**, and then select **Save (2)**.

   ![](../media/eng13.png)

1. In the pop-up window, select **Save**.

   ![](../media/eng14.png)

1. Review all the details and select **Create**.

   ![](../media/eng15.png)

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.

Learner Support Contacts:

- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

Now, click on the **Next** from lower right corner to move on next page.

   ![](../media/a-gs-g1.png)

## Happy Learning!!
