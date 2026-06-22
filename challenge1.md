# Challenge 1 - Build the Brain

## Overview

Set up the AI infrastructure that powers the enterprise knowledge platform. You will prepare document storage, deploy the AI models, build a vector search index from your document corpus, and wire it all together into a grounded AI agent that can answer policy questions with citations.

The challenge is complete when your Microsoft Foundry agent returns accurate, cited responses to enterprise knowledge queries in the playground.

---

## Prerequisites

Deploy all resources in the **<inject key="Region"></inject>** region before you start.

| Resource | Recommended SKU | Notes |
|---|---|---|
| Azure Storage Account | Standard LRS | You will create a blob container for the document corpus |
| Foundry Project | Standard | Create a Microsoft Foundry Project |
| Azure AI Search | Basic | Sufficient for this lab; enables semantic and vector search |

---

## Objectives

### 1. Document Storage

Set up the storage layer that holds your enterprise policy corpus.

- Create an Azure Storage Account and a blob container named `knowledge-docs`.
- Download the knowledge base dataset provided for this lab - 10 policy documents across HR, IT, and Finance categories.
- Upload all 10 documents to the `knowledge-docs` container.

<validation step="6a8d1575-856e-49b9-af67-fb2668d0fd75" />
 
> **Congratulations** on completing the Challenge! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding Challenge. If you receive a success message, you can proceed to the next Challenge. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help.

---

### 2. AI Models

Prepare the models your agent and index will rely on.

- In your Microsoft Foundry project, deploy the following two models:
  - A chat completion model - use `gpt-4.1` or `gpt-4.1-mini` (whichever is available in your region).
  - An embedding model - use `text-embedding-ada-002`.
- Note the deployment names - you will need them when configuring the index and agent.

<validation step="e80882e6-7459-4042-889a-8761a4763182" />
 
> **Congratulations** on completing the Challenge! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding Challenge. If you receive a success message, you can proceed to the next Challenge. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help.

---

### 3. Knowledge Index

Build a vector search index from the documents in Blob Storage.

- Create an Azure AI Search instance (Basic SKU is sufficient to control cost).
- Use the **Import data** option in AI Search to connect to your Blob Storage container.
- Set the vectorizer kind to **Microsoft Foundry**, and select your `text-embedding-ada-002` deployment. Run the indexer.

<validation step="082b146f-d781-43f0-8878-89c5680b0af9" />
 
> **Congratulations** on completing the Challenge! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding Challenge. If you receive a success message, you can proceed to the next Challenge. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help.

---

### 4. Grounded Agent

Build the AI agent in Microsoft Foundry and connect it to your knowledge index.

- In your Microsoft Foundry project, create a new agent using the chat model you deployed.
- Add Azure AI Search as a knowledge source on the agent, pointing to your index.
- Write a system prompt that instructs the agent to:
  - Always ground answers in retrieved documents - no general knowledge for policy questions.
  - Include a source citation in every response.
  - Return a clear fallback message when the answer is not found in the index.
  - Format policy comparisons as a structured table.
- Test the agent in the Microsoft Foundry chat playground. Run at least five queries covering different scenarios - a direct lookup, a summary, a cross-document comparison, a recommendation, and an out-of-scope question. Confirm every in-scope answer includes a citation.

<validation step="a589c4e0-175a-4b8a-b724-b4cf1db56c4c" />
 
> **Congratulations** on completing the Challenge! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding Challenge. If you receive a success message, you can proceed to the next Challenge. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help.

---

## Success Criteria

Before moving to Challenge 2, confirm the following:

- All 10 documents are uploaded to the `knowledge-docs` blob container.
- Both models (chat and embedding) are deployed in your Microsoft Foundry project.
- The AI Search index exists and document count is greater than 0.
- A test query in Search Explorer returns relevant results.
- The Microsoft Foundry agent returns cited, grounded responses in the playground for at least 5 test queries.
- The agent returns a clear fallback message (not a hallucinated answer) for an out-of-scope question.

---

Click **Next** at the bottom of the page to proceed to Challenge 2.
