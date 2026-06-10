# Challenge 2 - Ship the Product

## Overview

Take the grounded AI agent you built in Challenge 1 and give it a face that employees can actually use. You will create a Copilot Studio agent, connect it to your AI Search knowledge index, design conversation topics that cover real enterprise use cases, and publish it so anyone can access it through a browser.

The challenge is complete when a live published copilot answers policy questions with citations through a shareable URL.

---

## Prerequisites

- Challenge 1 complete - your AI Search index is populated and the Foundry agent is tested.
- Access to Microsoft Copilot Studio (included with your M365 license).

---

## Objectives

### 1. Copilot Studio Agent

Create the conversational interface that employees will use to query the knowledge base.

- Create a new agent in Microsoft Copilot Studio.
- Connect Azure AI Search as a knowledge source.
- Configure the agent's instructions to enforce grounded, cited responses - consistent with how the Foundry agent was configured in Challenge 1.

---

### 2. Conversation Topics

Design topics that route different types of employee queries to the right behavior.

- Create at least three topics covering the following scenarios:
  - **Policy Lookup** - the employee asks about a specific policy or wants a summary of a document.
  - **Policy Comparison** - the employee wants to compare two policies or versions of the same policy.
  - **Recommendation** - the employee describes a situation and wants to know which policy applies and what to do.
- Configure a fallback topic that surfaces a clear "not found" message rather than fabricating an answer for out-of-scope questions.
- Test each topic in the Copilot Studio canvas before publishing. Every response for an in-scope query should include a citation to the source document.

---

### 3. Publish and Validate

Publish the copilot and confirm it works end-to-end through the live channel.

- Publish the copilot to a web channel.
- Open the web channel URL in a browser (not in the Copilot Studio canvas) and confirm the copilot loads.
- Run the following three validation scenarios through the live URL:
  - Ask about a specific policy detail - confirm the response cites a source document.
  - Ask the copilot to compare two policies - confirm a structured comparison with references to both documents.
  - Describe a business situation and ask which policy applies - confirm the recommendation names the correct document and section.
- All three responses must be accurate, grounded, and free from hallucinated content.

---

## Success Criteria

Before submitting, confirm the following:

- The Copilot Studio agent is connected to your AI Search index.
- At least three conversation topics are created and tested.
- The fallback topic returns a "not found" message for out-of-scope queries.
- The copilot is published and accessible via a live web channel URL.
- All three validation scenarios return cited, grounded responses through the live URL.

Click **Next** at the bottom of the page to proceed to the Bonus Challenge.
