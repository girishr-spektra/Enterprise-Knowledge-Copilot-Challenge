# Cleanup: Remove Enterprise Knowledge Copilot Resources

## Overview

In this section, you will clean up all Azure and Microsoft resources created during this hackathon.

Performing cleanup after the challenge is important to avoid unintended ongoing charges, remove provisioned resources that are no longer needed, and leave the environment in a clean state. Please complete all steps below once you have finished the hackathon and submitted your artifacts.

---

## Steps to Complete

### 1. Delete the Copilot Studio Copilot

1. Navigate to Microsoft Copilot Studio at `https://copilotstudio.microsoft.com`.

1. From the list of copilots, locate the copilot you created during the challenge.

1. Select the copilot, click on the **Settings** or context menu, and choose **Delete**.

1. Confirm deletion when prompted.

---

### 2. Delete the Power Automate Flows

1. Navigate to Power Automate at `https://make.powerautomate.com`.

1. From the **My flows** section, locate the ingestion automation flow created during the challenge.

1. Select the flow and click **Delete**.

1. Confirm deletion when prompted.

---

### 3. Delete the Microsoft AI Foundry Project

1. Navigate to Microsoft AI Foundry at `https://ai.azure.com`.

1. Select your project from the project list.

1. Navigate to **Management** or **Settings** within the project.

1. Select the option to delete the project and confirm.

   > **Note:** Deleting the Foundry project will also remove deployed agents and flows associated with it.

---

### 4. Delete Azure Resources

1. In the Azure Portal, navigate to your assigned resource group.

1. Select **Delete resource group** from the top menu.

   ![](./media/cleanup1.png)

1. In the confirmation pane, type the name of the resource group and click **Delete**.

   ![](./media/cleanup2.png)

   This will delete all Azure resources provisioned during the challenge, including:

   - Azure Storage Account and all Blob containers
   - Azure AI Search instance and index
   - Azure Document Intelligence resource

1. Wait for the deletion to complete. You can monitor progress in the Azure Portal notifications panel.

---

### 5. Verify Cleanup

1. Confirm the resource group no longer appears in the Azure Portal.

1. Confirm the copilot is no longer listed in Copilot Studio.

1. Confirm the Power Automate flows are removed.

You have now successfully cleaned up all resources created during the Enterprise Knowledge & Document Intelligence Copilot challenge.
