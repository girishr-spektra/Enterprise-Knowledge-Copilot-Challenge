## Day 01 - Afternoon

# Challenge 2: Copilot Experience - Interface, Automation & Web Deployment

## Goal

Take the intelligence backend you built in Challenge 1 and wrap it into a finished, deployable enterprise product. You will build the conversational copilot that employees interact with, automate the ingestion pipeline so it runs without human intervention, and publish the copilot as a live web channel accessible from any browser. The challenge is complete when a real person can open a URL, ask an enterprise knowledge question, and receive a grounded, cited answer.

---

## Challenge Overview

The AI is working. The index is loaded. The Foundry agent is tested. Now the question is: who can actually use it?

This challenge is about closing the last mile. You have an intelligent backend - your job now is to give it a face employees can interact with, a pipeline that keeps itself current, and a deployment that makes the copilot accessible without IT involvement.

This is also where most enterprise AI projects fail. The backend works in the playground, but the product never ships. You will ship it.

In this challenge, you will:

- Wire Microsoft Copilot Studio to the Foundry agent and build the conversation flows that define the employee experience.
- Automate document ingestion using Power Automate so new files uploaded to Blob Storage are processed and become queryable without manual steps.
- Publish the copilot to the Copilot Studio web channel, giving it a shareable public URL.
- Run three structured end-to-end validation scenarios through the live web channel to confirm the complete system works from URL to cited answer.

The challenge is complete only when the web channel URL is live, produces correct grounded responses, and the automation pipeline has a confirmed successful run history.

---

## Objectives

### 1. Enterprise Copilot Interface

Build the employee-facing conversational interface in Microsoft Copilot Studio, connected to the Foundry agent, with conversation flows that map to real employee use cases.

- Create a new copilot in Microsoft Copilot Studio.
- Connect the copilot to your Microsoft AI Foundry agent as the primary generative AI backend.
- Design and implement at minimum three distinct conversation topics covering the following scenarios:
  - **Document Lookup and Summary:** The employee describes what they need. The copilot retrieves and summarizes the relevant document with a source citation.
  - **Policy Comparison:** The employee names two policies or documents. The copilot returns a structured comparison with references to both source documents.
  - **Recommendation Under a Scenario:** The employee describes a business situation. The copilot recommends the applicable policy, template, or procedure and explains the rationale.
- Configure fallback behavior for out-of-scope queries. The copilot must not fabricate answers or present ungrounded content as fact.
- Enable multi-turn conversation so employees can ask follow-up questions within a session without losing context.
- Test each topic through at least two full conversation flows before moving to the web channel deployment step.

Consider how ambiguous queries should be handled - whether the copilot should ask a clarifying question or attempt resolution based on available context.

Outcome:
A Microsoft Copilot Studio copilot is operational with conversation flows for the three core enterprise knowledge scenarios, connected to the Foundry agent, and validated through direct testing in the Copilot Studio canvas.

---

### 2. Automated Ingestion Workflow

Build the automation layer that keeps the knowledge index current when new documents arrive, without requiring any manual action.

- Create a Power Automate flow that triggers automatically when a new file is uploaded to the designated Azure Blob Storage container.
- The flow must initiate document extraction using Azure Document Intelligence and queue or trigger an update to the Azure AI Search index with the newly processed content.
- Design for resilience: the flow must include error handling so that processing failures are captured and surfaced rather than silently dropped.
- Validate the automation by uploading a document that was not part of your original corpus. Confirm the document becomes queryable through the copilot within a defined time window. Choose a time window that reflects what would be acceptable in a real enterprise scenario.
- Review the flow run history to confirm successful execution. This run history screenshot is a required submission artifact.

Consider what an operations team would need to monitor and troubleshoot this flow if it ran in production. Build accordingly.

Outcome:
A Power Automate flow automates end-to-end ingestion from Blob Storage upload to searchable knowledge index entry, with error handling and a confirmed successful run history.

---

### 3. Web Channel Publishing & End-to-End Validation

Publish the copilot as a live web channel and validate the complete system through three structured real-world scenarios. This is the final proof that everything works together.

**Web Channel Deployment:**

- Publish the copilot to the Copilot Studio web channel (Demo Website / custom page channel).
- Obtain the live web channel URL. This URL must be functional and accessible without requiring organizational sign-in credentials.
- Open the web channel in a browser and confirm the copilot loads and responds before beginning validation.

**End-to-End Validation Scenarios:**

Run all three scenarios through the live web channel URL - not through the Copilot Studio canvas or the Foundry playground. The URL is the product.

- **Scenario 1 - Policy Lookup with Citation:** Ask the copilot to explain the organization's position on a specific topic that is covered in your indexed corpus. For example: data classification levels, travel expense limits, or vendor onboarding requirements. The response must cite the source document, section, or page. Verify the citation points to a real document in your corpus.

- **Scenario 2 - Cross-Document Comparison:** Ask the copilot to compare two policies or document sections from the same category. The response must be structured, distinguish the two documents clearly, and reference both source documents. Verify the comparison is accurate against the actual documents.

- **Scenario 3 - Recommendation Under a Scenario:** Describe a realistic business situation to the copilot and ask which policy, template, or procedure applies. The response must name the specific document, explain the rationale, and ground the recommendation in indexed content. Verify the recommendation is correct.

For validation to be considered successful, all three scenarios must produce responses that are accurate, cited, and free from hallucinated content. If any scenario fails, diagnose and fix the gap before submitting.

Outcome:
The copilot is live on the web channel, accessible via a shareable URL, and delivers accurate grounded cited responses across all three enterprise knowledge scenarios when tested through the live channel.

---

## Expected Outcomes

By the end of Challenge 2:

- A Microsoft Copilot Studio copilot is connected to the Foundry agent with conversation flows covering document lookup, policy comparison, and recommendation scenarios.
- A Power Automate flow automates ingestion from Blob Storage through Document Intelligence to the Azure AI Search index when new documents are uploaded.
- The copilot is published and live on the Copilot Studio web channel with a shareable URL.
- All three end-to-end validation scenarios pass through the live web channel URL with accurate, grounded, cited responses.
- The complete system - corpus, extraction, indexing, agent, copilot interface, automation, and web channel - is operational and validated.

---

## Completion Criteria (Mandatory Submission)

Please use the instructions provided below and follow the submission steps carefully:

Once you complete this challenge, you must:

1. Keep the below artifacts ready to be uploaded:

   - A screenshot of the copilot web channel in a browser showing a cited response to an enterprise policy lookup query (Scenario 1 validation). The URL bar must be visible to confirm this is the web channel and not the Copilot Studio canvas.
   - A screenshot of the copilot web channel showing a structured cross-document policy comparison response with source references (Scenario 2 validation).
   - A screenshot of the Power Automate flow run history confirming at least one successful automated ingestion run triggered by a new Blob Storage upload.

1. Name the screenshots using the below naming convention:

   - `<Your_Name>_<Challenge02>_<file01>_<Time_Stamp(HH:MM)>`
   - `<Your_Name>_<Challenge02>_<file02>_<Time_Stamp(HH:MM)>`
   - `<Your_Name>_<Challenge02>_<file03>_<Time_Stamp(HH:MM)>`

1. Navigate back to **Hackathon Portal** where you registered for the hackathon.

1. In the hackathon portal, select **Learning Resources** page.

   ![](./media/hackportalv2.png)

1. Scroll down to bottom, under **Upload Your Certificate**, click **upload Certificate** and upload the artifacts that you have prepared earlier.

   ![](./media/hack2.png)

This submission is mandatory.

Failure to submit these artifacts will result in the challenge being marked as incomplete.

## Congratulations! You have successfully completed Challenge 2 and the full Enterprise Knowledge & Document Intelligence Copilot Hackathon
