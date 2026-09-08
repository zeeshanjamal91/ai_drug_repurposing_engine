# RIPHAH INTERNATIONAL UNIVERSITY LAHORE, PAKISTAN

## Riphah School of Computing & Innovation

### FYP Registration / Supervisor Consent Form

---

**Semester:** Fall 2026  
**Program:** BSDS (BS Data Science)  
**Supervisor:** [Supervisor Name]  
**Designation:** [e.g., Assistant Professor]  
**Co-Supervisor:** [If applicable]  
**Designation:** [If applicable]  
**Industry Advisor:** [If applicable]  
**Designation:** [If applicable]

---

## Project Title

**AI-Based Autonomous Literature Discovery Engine for Drug Repurposing**

*Technical focus: Knowledge Graphs, Graph Neural Networks (GNNs), Large Language Models with Retrieval-Augmented Generation (RAG), and computational molecular docking for literature-based drug repurposing.*

---



## PROJECT TYPE


| #   | Types                                                     | Select | Description                                                                                                                                                                                          |
| --- | --------------------------------------------------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | Product Development Project                               | ☐      | Focused on designing, developing, testing, and deploying software or hardware solutions to solve a real-world problem.                                                                               |
| 2   | IoT & Embedded Systems Project                            | ☐      | Project involving the design and implementation of intelligent systems integrating sensors, embedded devices, communication technologies, cloud platforms, and software applications.                |
| 3   | **Research Project**                                      | **☑**  | A project involving scientific investigation of a computing problem through literature review, experimentation, data analysis, and validation to generate new knowledge or improve existing methods. |
| 4   | Consulting / Case Study                                   | ☐      | A systematic investigation of an existing organization, technology, information system, or computing problem to analyze current practices, identify issues, and recommend improvements.              |
| 5   | **Innovative & Entrepreneurial Project (AI Integration)** | **☑**  | Project that develops an innovative technology-based product or service with commercial potential and can extensively use AI.                                                                        |
| 6   | Continuation Project (Existing product based)             | ☐      | A project carried out in collaboration with an industry partner to solve an actual organizational problem using industrial standards, methodologies, and professional practices.                     |


---



## Sustainable Development Goals (SDGs)

- ☑ **Goal 3:** Good health and well-being *(Primary focus)*
- ☑ **Goal 9:** Industry, innovation and infrastructure *(Technical infrastructure & innovation focus)*

---



## PROJECT TEAM


| #   | Student ID     | Student Name                      | Program | Signature |
| --- | -------------- | --------------------------------- | ------- | --------- |
| 1   | [Student ID 1] | [Student Name 1] (Project Leader) | BSDS    |           |
| 2   | [Student ID 2] | [Student Name 2]                  | BSDS    |           |
| 3   | [Student ID 3] | [Student Name 3]                  | BSDS    |           |


**Supervisor Comments:** _____________________________________________________________

**Signature (Project Supervisor):** _____________ **Dated:** _____________

---



## STUDENT CONTACT DETAILS


| #   | Student ID     | Student Name     | Contact No. | Email     |
| --- | -------------- | ---------------- | ----------- | --------- |
| 1   | [Student ID 1] | [Student Name 1] | [Phone 1]   | [Email 1] |
| 2   | [Student ID 2] | [Student Name 2] | [Phone 2]   | [Email 2] |
| 3   | [Student ID 3] | [Student Name 3] | [Phone 3]   | [Email 3] |


---



## Undertaking

We all understand and undertake that we all have passed all the following courses as a pre-requisite to enroll in FYP:

- Object Oriented Programming
- Web Application Development
- Introduction to Database Systems
- Software Engineering

---



# PROJECT IDEA DETAILS



## Project Title

**AI-Based Autonomous Literature Discovery Engine for Drug Repurposing**

---



## Introduction

Every year, millions of biomedical research papers are published, each describing how drugs, proteins, and diseases are connected. However, these findings often remain scattered across separate studies, making it difficult for researchers to see the full picture. Drug repurposing — finding new uses for existing approved drugs — offers a faster and more affordable path than developing entirely new medicines, but manually reading and connecting information from this vast literature is not practical for humans.

Literature-Based Discovery (LBD) addresses this by linking facts published in different papers to suggest new scientific relationships. For example, if one paper states that *Drug A affects Protein X*, and another states that *Protein X is involved in Disease Y*, the system can suggest that *Drug A may be relevant to Disease Y*. Our project builds an automated software system that reads biomedical literature, organizes these relationships into a structured network (knowledge graph), uses artificial intelligence to find promising missing connections, retrieves supporting evidence from published papers, computationally tests whether a drug may bind to a relevant protein target, and finally generates a structured research report. The goal is not to discover a new drug or prove clinical effectiveness, but to identify **computationally evaluated research hypotheses** that scientists can investigate further in laboratory or pre-clinical settings.

---



## Problem Statement

Traditional drug discovery takes more than a decade and costs billions of dollars to bring a single new drug to market. Drug repurposing reduces this burden by exploring new therapeutic uses for drugs that are already approved and known to be safe. The challenge is that the evidence needed to support such ideas is buried across millions of research articles, and no human team can manually read and connect all of them.

Existing tools fall short in three important ways. First, many literature search systems act as passive search engines — they retrieve papers but do not automatically build structured networks or predict new drug–disease relationships. Second, tools that use Large Language Models (LLMs) can summarize text but may produce incorrect or unsupported biological claims because they lack structured evidence and physical validation steps. Third, current biomedical knowledge graphs (such as Hetionet or PrimeKG) are useful static databases but do not continuously ingest new literature, explain why a predicted link exists, or computationally evaluate whether a drug can physically interact with a protein target.

There is therefore a need for an integrated, autonomous data science system that can: (1) extract and organize biomedical relationships from literature, (2) predict promising drug–disease links using graph-based AI, (3) retrieve and explain supporting evidence from source papers, (4) run computational binding tests in a safe isolated environment, and (5) produce a clear, downloadable research dossier — all with minimal human intervention. This project addresses that gap within the realistic scope of a Final Year Project.

---



## Proposed Solution

We propose an **AI-Based Autonomous Literature Discovery Engine** — a closed-loop software pipeline that automatically moves from raw scientific text to ranked, computationally supported drug repurposing hypotheses.

**Step 1 — Literature Ingestion & Knowledge Graph Construction:** The system collects biomedical abstracts (e.g., from PubMed) and extracts structured relationships in the form of triples such as *Drug → affects → Protein* and *Protein → involved in → Disease*. These are stored in a heterogeneous knowledge graph — a network containing different types of entities (drugs, proteins, diseases) and their connections.

**Step 2 — Link Prediction using Graph Neural Networks (GNN):** A GNN learns patterns from the existing network and predicts drug–disease relationships that are not yet explicitly documented, ranking them by likelihood.

**Step 3 — Evidence Retrieval & Explanation using LLM + RAG:** For each predicted link, a Retrieval-Augmented Generation (RAG) module searches relevant published passages and uses an LLM to explain the biological pathway — following multi-hop connections such as Drug → Protein → Pathway → Disease — using retrieved source text rather than relying on the model's memory alone.

**Step 4 — Computational Binding Evaluation:** The system automatically generates and runs molecular docking scripts (using AutoDock Vina) inside a Docker sandbox — an isolated, controlled environment — to estimate how well a candidate drug molecule may bind to the relevant protein target. This provides a computational sanity check, not proof of clinical efficacy.

**Step 5 — Report Generation & Safety Review:** Findings are compiled into a structured Pre-clinical Repurposing Dossier (PDF via LaTeX). An automated LLM reviewer checks each hypothesis for basic safety concerns (e.g., toxicity flags, ADME limitations, and dual-use research concerns). Results are displayed on an interactive Streamlit web dashboard where users can explore predicted pathways, view evidence, and download reports.

**Example workflow:** If the literature contains *Drug A → affects Protein X* and *Protein X → involved in Disease Y*, the GNN asks *"Could Drug A be relevant to Disease Y?"*, the RAG module retrieves papers explaining the connection, docking checks whether Drug A computationally fits Protein X, and the system outputs: *"Drug A–Disease Y is a computationally supported hypothesis with these literature sources and this docking score."*

---



## Existing Solution / Prior Work



### 1. Don Swanson's Classic LBD (e.g., Arrowsmith)

**Description:** Early literature-based discovery tools that use keyword matching and co-occurrence analysis to find "ABC" relationships — if A is linked to B and B is linked to C, then A may be linked to C.

**Limitations:** No semantic understanding of biological context; requires manual search queries; cannot scale to multi-hop analysis across large literature corpora; provides no automated computational validation.

### 2. Biomedical Knowledge Graphs (e.g., PrimeKG, Hetionet)

**Description:** Pre-built biological networks that compile drug–protein, protein–protein, and gene–disease associations from curated databases.

**Limitations:** Static snapshots that do not continuously ingest new publications; no natural language reasoning to explain predicted links; no integrated computational binding evaluation layer.

### 3. AI Literature Search Tools (e.g., Elicit, Consensus)

**Description:** AI-powered tools that search PubMed using embeddings and use LLMs to summarize findings for researchers.

**Limitations:** Act as passive search and summarization interfaces; do not maintain structured knowledge graphs; cannot perform predictive link forecasting; prone to unsupported biological claims without structured evidence or physical simulation checks.

---



## Your Contribution / Value Addition


| #   | Contribution                                 | Description                                                                                                                                                                                                   |
| --- | -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | **Autonomous Closed-Loop Pipeline**          | Unlike passive search tools, our system automates the full cycle: hypothesis generation → evidence retrieval → computational evaluation → report generation → safety review, with minimal human intervention. |
| 2   | **GNN + LLM Hybrid Architecture**            | Combines graph-based link prediction (GNN) for structural pattern learning with RAG-enabled LLMs for evidence-backed pathway explanation, reducing unsupported AI hallucinations.                             |
| 3   | **Sandboxed Computational Binding Layer**    | Integrates AutoDock Vina molecular docking inside a Docker sandbox to computationally evaluate drug–protein interactions, bridging symbolic AI predictions with basic biochemical plausibility checks.        |
| 4   | **Automated Safety & Review Filter**         | An LLM-based reviewer agent screens generated hypotheses for toxicity concerns, ADME limitations, and dual-use research (DURC) flags before presenting results to users.                                      |
| 5   | **Interactive Dashboard & Research Dossier** | A Streamlit web interface visualizes predicted drug–disease pathways and evidence chains, with downloadable LaTeX-generated pre-clinical repurposing dossiers for further scientific review.                  |


**Scope clarification:** This system does **not** claim to discover new drugs or prove that a drug cures a disease in humans. It identifies promising drug–disease relationships from existing biomedical knowledge, prioritizes them using AI and computational methods, and presents them as **pre-clinical research hypotheses** worthy of further laboratory investigation. This realistic scope makes the project scientifically defensible and achievable within an FYP timeline.

---



## Key Terms Reference (for Panel Defense)


| Term                             | Simple Meaning                                                                                         |
| -------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Drug repurposing                 | Finding a new use for an existing approved drug                                                        |
| Literature-Based Discovery (LBD) | Discovering new scientific connections by analyzing published research                                 |
| Knowledge Graph                  | A network of entities and their relationships (e.g., Drug → affects → Protein → involved in → Disease) |
| GNN                              | AI that learns patterns from graph structures rather than isolated data points                         |
| Link Prediction                  | Predicting a relationship not yet explicitly present in the graph                                      |
| LLM + RAG                        | AI that answers using retrieved source documents, not memory alone                                     |
| Molecular Docking                | Computationally estimating how a drug molecule fits into a protein target                              |
| Docker Sandbox                   | Isolated environment for safely running computational experiments                                      |
| Pre-clinical candidate           | A computationally supported hypothesis worth further lab investigation                                 |


---

*End of Proposal*