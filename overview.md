# One Hackathon - Enterprise Knowledge & Document Intelligence Copilot

Welcome to the Hack to Skill: Enterprise Knowledge & Document Intelligence Copilot challenge.

In this hackathon, you will design and build a unified enterprise knowledge copilot that can ingest organizational content from multiple sources, process and extract intelligence from unstructured documents, and surface accurate cited answers, policy comparisons, and actionable recommendations to employees through a conversational interface.

---

## Problem Statement

Organizations accumulate vast amounts of institutional knowledge across SharePoint sites, Teams channels, PDF policy documents, email archives, and legacy storage systems. Employees spend hours searching across disconnected systems to locate relevant contracts, compliance policies, standard operating procedures, or approved templates - only to find outdated or incomplete results.

The lack of a unified, intelligent retrieval system creates significant productivity loss. Without grounded, cited responses, employees cannot trust AI-generated answers for compliance-sensitive or decision-critical queries. Policy comparison across document versions requires manual effort that is both error-prone and time-consuming.

This challenge addresses the full lifecycle of enterprise knowledge management: from raw document ingestion and intelligent extraction, through semantic indexing and AI-grounded retrieval, to a production-ready conversational copilot that employees can trust to surface accurate, cited, and actionable knowledge from across the organization.

---

## About the Sandbox Environment

   | Resources | Value | Remarks |
   | --- | --- | --- |
   | Enabled Services | `Azure AI Search` <br> `Microsoft AI Foundry` <br> `Azure Document Intelligence` <br> `Azure Blob Storage` <br> `Microsoft Copilot Studio` <br> `Power Automate Premium` <br> `Microsoft 365 Business Standard` | You have full access over the Azure subscription. Use these services to build the end-to-end knowledge copilot platform. |
   | Azure Entra ID User | Pre-created Entra ID user account | You will get one Entra ID User Account with access to all required services. |
   | Azure Subscription Permissions | **Owner** privilege over Azure Subscription | You will get Owner access to the Azure subscription. |
   | Azure Credit | **$150 USD** | Consumption limit is set on Azure spend to 150 USD. |
   | Credit Alerts | Credit Alerts are set on consumption of 25%, 50%, 75%, 85%, 90%, 95% and 100% of total Azure credits. | Make sure to check your registered email's inbox for any alert-related mails. Alerts give you a head start to keep your Azure spending in control and to plan out the remaining credits in the best way possible. |
   | Sandbox Duration | 1 Day / 24 Hours or until Azure Consumption Credits are exhausted. | The sandbox environment will be deleted automatically after 24 Hours or once the Azure credits are exhausted, whichever comes first. |

---

## Why This is Enterprise-Ready - Not Just Another Chatbot

If you have worked with Copilot Studio before, you may have built an agent that connects to SharePoint and answers questions. What you are building here is architecturally different at every layer.

The table below shows what separates an enterprise-grade knowledge platform from a basic document Q&A bot:

| Capability | Basic Knowledge Bot | What You Build Here |
| --- | --- | --- |
| Document ingestion | Upload files to SharePoint, auto-indexed | Blob Storage with category structure, Document Intelligence extracts tables, key-value pairs, headings, and metadata into a controlled schema |
| Retrieval mechanism | Keyword and basic semantic search inside Copilot Studio | Custom Azure AI Search index with chunking strategy, vector embeddings, hybrid search, and citation metadata per chunk |
| AI intelligence layer | Copilot Studio's built-in generative answers | Microsoft AI Foundry agent with engineered prompts, grounding enforcement, hallucination prevention, and structured comparison logic |
| Answer quality | Generative answer from matched content | Cited response - every answer references the source document, section, and page |
| Policy comparison | Not supported | Structured cross-document comparison engine built into the agent |
| New document handling | Manual re-upload to SharePoint | Power Automate triggers extraction and re-indexing automatically on blob upload |
| Deployment | Teams channel | Web channel published as a standalone URL accessible from any browser or portal |
| Trust and auditability | Limited - no source traceability | Full citation chain from response back to source chunk, document, and storage location |

This platform is designed to be connected to real enterprise identity, plugged into a real intranet or employee portal, and trusted for compliance-sensitive queries. The architecture you build here is the same pattern used in production enterprise AI deployments.

---

## Best Practices:

+ **Resources usage:** Please stop or scale down Azure AI Search, Document Intelligence, and other resources when not in use to minimize Azure spend.
+ **Azure Cost Analysis:** Maintain a practice of regularly checking the Cost Analysis report for the assigned Azure subscription to ensure sustainability of the environment over the challenge duration.
+ **Alert notifications:** Make sure to check your registered email's inbox for any alert-related emails. Alerts give you a head start to keep your Azure spending in control.
+ **Document corpus scope:** Keep your test document corpus focused and representative. Processing large volumes of documents will consume credits quickly during the hackathon.

---

## Hack to Skill Format: Challenge-Based

This hackathon is structured into two progressive challenges that build the enterprise knowledge platform in two distinct phases. The first challenge focuses on the intelligence backend. The second challenge focuses on the user-facing product built on top of it.

- **Challenge 1 - Intelligence Pipeline: Extraction, Indexing & Grounded AI**  
  Set up the document corpus in Blob Storage, extract structured content using Document Intelligence, build a semantic and vector-enabled knowledge index in Azure AI Search, and develop a grounded citation-aware AI agent in Microsoft AI Foundry. This challenge delivers the intelligence layer that everything else depends on.

- **Challenge 2 - Copilot Experience: Interface, Automation & Web Deployment**  
  Wire the Foundry agent to a Copilot Studio copilot with defined conversation flows for real employee scenarios, automate document ingestion using Power Automate, and publish the copilot as a live web channel accessible via a public URL. This challenge delivers the finished product employees can use.

Challenge 1 must be completed before starting Challenge 2. The system is not complete until both challenges are finished and the copilot is live on the web channel with validated, cited responses.

---

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year via email and live chat to ensure seamless assistance throughout the hackathon.

**Learner Support Contacts**  
- Email: cloudlabs-support@spektrasystems.com  
- Live Chat: https://cloudlabs.ai/labs-support

Click **Next** to proceed to set up the prerequisites for this hackathon.
