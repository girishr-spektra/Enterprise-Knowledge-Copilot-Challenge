# Solution Guide - Enterprise Knowledge & Document Intelligence Copilot

**Purpose:** Facilitator / proctor fast-path reference. Walk-through of both challenges end-to-end.  
**Audience:** Lab author / proctor running feasibility validation.  
**Time estimate:** Challenge 1 ~75 min, Challenge 2 ~45 min.

---

## What Are We Building?

An enterprise knowledge platform where employees ask natural language questions about company policies and get accurate, cited answers from a grounded AI agent, delivered through a published Copilot Studio interface.

### Architecture

```
                        CHALLENGE 1 - Build the Brain
  ┌──────────────┐    ┌──────────────────────────────┐    ┌─────────────────────┐
  │ Blob Storage │───▶│  AI Search                   │───▶│  AI Foundry Agent   │
  │ knowledge-   │    │  Import + Vectorize           │    │  gpt-4.1 / mini     │
  │ docs (10 doc)│    │  vector index                │    │  grounded in index  │
  └──────────────┘    └──────────────────────────────┘    └─────────────────────┘

                        CHALLENGE 2 - Ship the Product
  ┌─────────────────────────────────────────────────────────────────────┐
  │  Copilot Studio agent                                                │
  │  AI Search connected as knowledge source                             │
  │  3 topics: Lookup, Comparison, Recommendation                        │
  │  Published to web channel - live URL                                 │
  └─────────────────────────────────────────────────────────────────────┘
```

### Service roles

| Service | Role |
|---|---|
| **Blob Storage** | Document repository. All 10 PDFs uploaded here. AI Search pulls from here during import. |
| **AI Search** | Vectorizes and indexes document content in one pass via "Import and vectorize data". Supports hybrid search for the agent. |
| **AI Foundry** | Hosts the chat and embedding model deployments and the grounded agent. |
| **Copilot Studio** | Conversational interface. Connects to AI Search directly as a knowledge source. Publishes to web channel. |

---

## Resources to Deploy First (~10 min)

Deploy everything in the **same region** (recommended: Sweden Central or West US 2).

| Resource | SKU | Notes |
|---|---|---|
| Storage Account | Standard LRS | Create container `knowledge-docs` |
| AI Foundry Hub + Project | Standard | Create hub then project inside it |
| Azure OpenAI (via Foundry) | - | Deploy `gpt-4.1` or `gpt-4.1-mini` + `text-embedding-ada-002` |
| Azure AI Search | Basic | Enable semantic search |

---

# CHALLENGE 1 - Build the Brain

## Step 1 - Upload Documents

1. Go to Storage Account > **Containers** > `knowledge-docs`.
2. Upload all 10 PDFs flat into the container root (no subfolders).

Files: HR-001, HR-002, HR-002v2, HR-003, IT-001, IT-002, IT-003, FIN-001, FIN-002, FIN-003.

---

## Step 2 - Deploy Models in AI Foundry

1. Go to https://ai.azure.com > open your project.
2. Go to **Models + endpoints** > **+ Deploy model**.
3. Deploy: `gpt-4.1` or `gpt-4.1-mini` (whichever is available in your region).
4. Deploy: `text-embedding-ada-002`.
5. Note both deployment names - you will need them in Steps 3 and 4.

---

## Step 3 - Build the Vector Index in AI Search

1. In the Azure Portal, open your AI Search resource.
2. Click **Import and vectorize data** (top toolbar).
3. **Data source:** Select **Azure Blob Storage** > pick your storage account and `knowledge-docs` container.
4. **Vectorize text:** Select your `text-embedding-ada-002` deployment as the embedding source.
5. **Index name:** `enterprise-knowledge-index`.
6. Submit - the indexer runs automatically.
7. Go to **Indexers** and wait for status **Success**.

**Verify:** Go to **Indexes** > `enterprise-knowledge-index` > **Search explorer**. Run `*` - confirm document count > 0 and content is visible. Run `data classification levels` - should return IT-001 content.

---

## Step 4 - Create the Foundry Agent

1. In AI Foundry, go to **Agents** > **+ New agent**.
2. Select your `gpt-4.1` deployment.
3. **System prompt:**

```
You are an enterprise knowledge assistant for Contoso Corporation. You answer questions from employees about company policies, procedures, and guidelines.

STRICT RULES:
1. Ground every response in documents retrieved from the knowledge base. Do not use general knowledge for policy-specific answers.
2. Every response MUST include a citation: [Source: <document_title>, Section: <section_name>]
3. If retrieved content does not contain enough information, respond: "I could not find a definitive answer in the Contoso policy documents. Please contact HR, IT, or Finance directly."
4. Never guess or infer policy details not present in the retrieved content.
5. When comparing two documents, produce a table with columns: Area | Old Policy | New Policy.
6. When making a recommendation, name the specific policy document, the section that applies, and explain why.
```

4. Under **Knowledge**, click **+ Add** > **Azure AI Search**.
5. Enter your Search endpoint, `enterprise-knowledge-index`, and admin key.
6. Query type: **Hybrid**, Top K: **5**.
7. Save.

**Test queries:**

| # | Query | Expected |
|---|---|---|
| 1 | What is the hotel rate limit for international travel to London? | Cites HR-003, $350/night |
| 2 | Summarize the data classification levels at Contoso. | Cites IT-001, 4 levels |
| 3 | Compare the remote work policy before and after the 2024 update. | Cites HR-002 + HR-002v2, comparison table |
| 4 | I need to hire a contractor for 12 months at $900/day. What approvals do I need? | Cites FIN-003, correct approval tier |
| 5 | What happens if an employee stores company files on personal Dropbox? | Cites IT-002, Level 3 violation |

All 5 should cite a source. If ungrounded, verify the index is populated and the AI Search connection is saved on the agent.

**C1 submission screenshots:** (1) AI Search index showing document count, (2) Foundry playground showing a cited response.

---

# CHALLENGE 2 - Ship the Product

## Step 5 - Create the Copilot Studio Agent

1. Go to https://copilotstudio.microsoft.com > **Create** > **New agent**.
2. Name: `Contoso Knowledge Copilot`.
3. Under **Knowledge**, click **+ Add knowledge** > **Azure AI Search**.
4. Enter your Search endpoint, index name `enterprise-knowledge-index`, and key.
5. Set agent instructions to enforce grounded, cited responses (same grounding rules as the Foundry agent).

---

## Step 6 - Create Topics

Create three custom topics:

**Topic 1 - Policy Lookup**
- Trigger phrases: "what is the policy on", "summarize the document", "explain the policy for", "what does Contoso say about"
- Add a generative answer node connected to the knowledge source.
- Fallback: "I couldn't find a definitive answer in the policy documents. Please contact HR, IT, or Finance directly."

**Topic 2 - Policy Comparison**
- Trigger phrases: "compare", "what changed between", "difference between", "old vs new policy"
- Ask for the two documents to compare, then pass to generative answer with instruction to produce a structured table.

**Topic 3 - Policy Recommendation**
- Trigger phrases: "which policy applies", "what should I do if", "am I allowed to", "what are the rules for"
- Ask the employee to describe their situation, then pass to generative answer with instruction to name the applicable policy and section.

Also configure the **System Fallback** topic to return: "I can only answer questions based on Contoso policy documents. Please rephrase or contact HR, IT, or Finance directly."

Test each topic in the Copilot Studio canvas before publishing.

---

## Step 7 - Publish and Validate

1. Click **Publish** (top right) and confirm.
2. Go to **Channels** > **Demo website**. Copy the URL.
3. Open the URL in a private browser window - confirm the copilot loads.

Run these 3 validation scenarios through the **live URL** (not the canvas):

**Scenario 1 - Policy Lookup**
Query: `What are the data classification levels at Contoso and what does each one mean?`
Expected: Cites IT-001, returns all 4 levels with definitions.

**Scenario 2 - Cross-Document Comparison**
Query: `Compare the old remote work policy with the 2024 update. What changed for Hybrid employees?`
Expected: Cites HR-002 and HR-002v2, structured comparison showing home office allowance and internet subsidy added.

**Scenario 3 - Recommendation**
Query: `I want to engage a senior technical contractor for 14 months at $950/day. What approvals do I need?`
Expected: Cites FIN-003, correct approval tier, flags that 14-month duration requires extension approval.

All 3 must be grounded and cited. If citations are missing, verify the agent instructions enforce `[Source: ...]` format.

**C2 submission screenshots:** (1) Web channel - Scenario 1 cited response (URL bar visible), (2) Web channel - Scenario 2 comparison with both document references, (3) Web channel - Scenario 3 recommendation.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| Agent returns ungrounded answers | Verify AI Search connection is saved on the agent. Check index document count > 0. |
| Index document count is 0 | Check the indexer status log. Confirm blob container name is exact match. Re-run the indexer. |
| Embeddings not working | Confirm `text-embedding-ada-002` deployment name matches what was entered in the Import wizard. |
| Copilot Studio not citing sources | Check agent instructions include `[Source: ...]` citation rule. |
| Web channel requires login | Go to Copilot Studio > **Security** > set authentication to **No authentication** before publishing. |
| Topics not triggering correctly | Add more trigger phrases. Check for conflicts with System topics. |
