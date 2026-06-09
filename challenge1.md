# Challenge 1 - Phase 1: Build the Brain - Extraction, Indexing & Grounded AI

## Goal

Build the intelligence backend of the enterprise knowledge platform - the foundation that everything else depends on. You will establish a structured document corpus, run intelligent extraction to transform unstructured files into machine-readable content, design a semantic and vector-enabled knowledge index, and develop a grounded AI agent in Microsoft AI Foundry that delivers trusted, cited responses to real enterprise queries.

This challenge delivers the AI layer. No user-facing interface yet - just clean data, precise retrieval, and a grounded agent that you can test directly.

---

## Challenge Overview

The intelligence pipeline is the hardest part of building a production-grade knowledge platform. Getting it wrong means no amount of UI polish will fix the responses. Getting it right means the copilot experience you build on top in Challenge 2 will work correctly from day one.

In this challenge, you will build that foundation. You will move through three tightly connected layers: structured extraction, semantic indexing, and grounded AI reasoning. Each layer's output becomes the next layer's input.

In this challenge, you will:

- Organize and ingest a representative enterprise document corpus into Azure Blob Storage.
- Use Azure Document Intelligence to extract structured content from raw unstructured files.
- Design and populate an Azure AI Search index with semantic and vector capabilities.
- Build a Microsoft AI Foundry agent grounded in that index, capable of citations, policy comparison, and recommendations.

The challenge is complete when your Foundry agent returns accurate, grounded, cited responses for at least five representative enterprise queries - tested directly in the Foundry playground before any copilot interface is involved.

---

## Objectives

### 1. Document Repository & Intelligent Extraction Pipeline

Establish the document storage foundation and build the extraction layer that transforms raw enterprise files into structured, machine-readable content.

- Create a storage structure in Azure Blob Storage that organizes documents by category.
- Upload your prepared document corpus with at minimum three distinct content categories.
- Configure and use Azure Document Intelligence to process documents across your corpus.
- Extract key structural elements from your documents - this includes body text, tables, key-value pairs, section headings, and document metadata.
- Define a consistent output schema that captures extracted content in a format suitable for downstream indexing.
- Validate extraction accuracy across at least one document from each category. Assess whether the extracted structure faithfully represents the source document.

Your extraction pipeline must be repeatable. Running it against a new document should produce consistently structured output without manual intervention.

Outcome:
A structured, validated document corpus is extracted and ready for semantic indexing, with a repeatable pipeline that processes new documents to a consistent schema.

---

### 2. Semantic Knowledge Index Construction

Design and build an Azure AI Search index that enables accurate, contextually relevant retrieval across your document corpus.

- Define an index schema that captures extracted document content, metadata, source identifiers, category tags, and chunk-level references needed for citation.
- Decide on a chunking strategy for your documents. Consider how chunk size and overlap affect retrieval precision and response coherence.
- Configure semantic search capabilities on the index.
- Integrate vector embeddings to enable vector and hybrid search. Select an appropriate embedding model available through your Foundry workspace.
- Populate the index with your extracted document content.
- Evaluate retrieval quality by running representative queries across categories. Assess whether the top results are relevant, and tune index configuration where they are not.

Your index must be designed with citation traceability in mind. Every chunk in the index should carry enough metadata to allow a downstream AI agent to identify the source document, section, and page from which the content was drawn.

Outcome:
A production-quality Azure AI Search index is operational, supports semantic and vector retrieval, returns relevant results for representative enterprise queries, and carries sufficient metadata for citation.

---

### 3. Foundry AI Agent with Grounded Intelligence

Build the intelligence layer in Microsoft AI Foundry - an agent that uses your knowledge index as its grounding source and is capable of delivering trusted, cited responses for real enterprise query patterns.

- Create or configure a project in Microsoft AI Foundry connected to your Azure AI Search index.
- Design and implement an agent or prompt flow that retrieves relevant content from the index before generating responses.
- Engineer prompts that enforce the following behaviors:
  - Every response must cite the source document, section, or page from which the answer was drawn.
  - The agent must refuse to answer or clearly flag when the answer cannot be grounded in indexed content.
  - The agent must distinguish between a direct answer, a summary, and a comparison - and format output accordingly.
- Implement a **policy comparison capability**: given two documents or sections, the agent must produce a structured comparison that highlights similarities, differences, and implications.
- Implement a **recommendation capability**: based on a described scenario or question, the agent must recommend the applicable policy, template, or procedure and explain why.
- Test the agent against at least five representative enterprise queries spanning summarization, lookup, comparison, and recommendation patterns. Document which queries succeed and which reveal gaps.

Retrieval-augmented generation must be the foundation of all responses. The agent must not rely on parametric knowledge for domain-specific answers.

Outcome:
A Microsoft AI Foundry agent delivers grounded, cited, accurate responses for enterprise knowledge queries including document summarization, policy comparison, and actionable recommendations - verified through direct testing in the Foundry playground.

---

## Expected Outcomes

By the end of Challenge 1:

- An Azure Blob Storage structure organizes the enterprise document corpus by category.
- Azure Document Intelligence extracts structured content from all corpus documents using a repeatable pipeline.
- An Azure AI Search index with semantic and vector search is operational and returns relevant, citation-traceable results.
- A Microsoft AI Foundry agent is grounded in the knowledge index and delivers cited responses for summarization, comparison, and recommendation queries.
- Direct agent testing in the Foundry playground confirms grounding, citation accuracy, and correct handling of out-of-scope queries.

---

## Completion Criteria (Mandatory Submission)

Please use the instructions provided below and follow the submission steps carefully:

Once you complete this challenge, you must:

1. Keep the below artifacts ready to be uploaded:

   - A screenshot of the Azure AI Search index showing the populated index with document count and field schema visible.
   - A screenshot of the Microsoft AI Foundry agent playground showing a cited response to an enterprise query that includes the source document reference.

1. Name the screenshots using the below naming convention:

   - `<Your_Name>_<Challenge01>_<file01>_<Time_Stamp(HH:MM)>`
   - `<Your_Name>_<Challenge01>_<file02>_<Time_Stamp(HH:MM)>`

1. Navigate back to **Hackathon Portal** where you registered for the hackathon.

1. In the hackathon portal, select **Learning Resources** page.

   ![](./media/hackportalv2.png)

1. Scroll down to bottom, under **Upload Your Certificate**, click **upload Certificate** and upload the artifacts that you have prepared earlier.

   ![](./media/hack2.png)

This submission is mandatory.

Failure to submit these artifacts will result in the challenge being marked as incomplete.

## Congratulations! You have successfully completed Phase 1
