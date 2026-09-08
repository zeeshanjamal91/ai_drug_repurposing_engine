\# (1) FYP proposal review



\## User



I want you to read the fyp proposal .md file and then answer a few questions. For each answer, you need to be skeptical and thorough in research and make me understand in a way that I don't know anything about the field yet. We need to explore things but right now I need to understand and make sure that we'll be able to complete this project within 2 semesters.



\## Assistant



I'll locate and read your FYP proposal first, then assess feasibility for two semesters in plain terms.



\### Tool Glob File Search



```

{"globPattern":"\*\*/\*proposal\*.md"}

```



\### Tool Glob File Search



```

{"globPattern":"\*\*/\*fyp\*.md"}

```



\### Tool Glob File Search



```

{"globPattern":"\*\*/\*.md"}

```



\### Tool Read File V2



```

{"path":"c:\\\\Users\\\\3 Stars Laptop\\\\Documents\\\\Zeeshan's Data\\\\FYP\_Zeeshan\\\\FYP\_Zeeshan\\\\FYP\_Proposal\_Drug\_Repurposing.md"}

```



\## Assistant



I've read the proposal. Next I'll check the repo for existing work and research comparable projects so we can judge two-semester feasibility realistically.



\### Tool Glob File Search



```

{"globPattern":"\*\*/\*"}

```



\### Tool Web Search



```

{"searchTerm":"drug repurposing knowledge graph GNN literature based discovery student project feasibility","toolCallId":"tool\_88a6036a-2983-4eca-afd6-22a9f59f2ad"}

```



\### Tool Web Search



```

{"searchTerm":"PrimeKG Hetionet drug repurposing link prediction GNN baseline implementation time","toolCallId":"tool\_66059545-0e37-4179-9927-8cdb01560ac"}

```



\### Tool Web Search



```

{"searchTerm":"biomedical relation extraction PubMed abstracts student project difficulty NER pipeline","toolCallId":"tool\_f7298e21-0987-4b63-b442-ba8f76efc60"}

```



\### Tool Web Search



```

{"searchTerm":"AutoDock Vina automated pipeline Docker drug protein docking student project","toolCallId":"tool\_af4ed571-e5a1-4e2d-a07b-9bbdc194501"}

```



\## Assistant



I've read your proposal. Below is a plain-language breakdown and a skeptical feasibility check for completing this in \*\*two semesters\*\* (FYP-I + FYP-II), assuming a team of 3 BSDS students starting Fall 2026.



\---



\## What this project actually is (zero background)



Imagine biomedical research as millions of puzzle pieces scattered across papers:



\- Paper 1: \*"Drug A affects Protein X"\*

\- Paper 2: \*"Protein X is involved in Disease Y"\*



A human might think: \*"Maybe Drug A could help Disease Y?"\* — but no one can read 30+ million PubMed abstracts manually.



Your project builds a \*\*software assistant\*\* that:



1\. Organizes facts into a \*\*network\*\* (knowledge graph)

2\. Uses \*\*AI on that network\*\* to guess missing drug–disease links

3\. \*\*Finds paper evidence\*\* for those guesses

4\. \*\*Runs a computer simulation\*\* to check if the drug could physically bind a protein

5\. \*\*Outputs a report\*\* a scientist could use as a starting hypothesis — not a proven cure



Important: the proposal correctly says this does \*\*not\*\* discover new drugs or prove clinical effectiveness. It produces \*\*research hypotheses\*\* worth lab testing.



\---



\## The 5 steps, explained simply



| Step | What it means | Real-world analogy |

|------|---------------|-------------------|

| \*\*1. Knowledge Graph (KG)\*\* | Store entities (drug, protein, disease) and relationships as a network | A map of "who connects to whom" |

| \*\*2. GNN link prediction\*\* | AI learns patterns in the map and predicts missing links | "If A connects to B and B connects to C, maybe A connects to C" |

| \*\*3. LLM + RAG\*\* | AI explains a prediction using \*\*retrieved paper text\*\*, not memory alone | A research assistant that must cite sources |

| \*\*4. Molecular docking\*\* | Simulate whether a drug molecule fits into a protein | A 3D puzzle-fit test on a computer |

| \*\*5. Dashboard + report\*\* | Show results in a web UI and export a PDF dossier | The final deliverable users interact with |



\---



\## Skeptical feasibility verdict



\*\*Short answer: Yes, this can be done in 2 semesters — but only if you narrow scope on the hardest parts.\*\* As written, the proposal describes \*\*5 separate mini-projects\*\* wired together. That is ambitious even for a strong 3-person team.



\### What is realistically achievable



| Component | Difficulty | Why |

|-----------|------------|-----|

| GNN link prediction on an \*\*existing\*\* KG (Hetionet, PrimeKG) | \*\*Medium\*\* | Open datasets and code exist (\[PrimeKG-RGCN](https://github.com/arnold117/PrimeKG-RGCN-LinkPrediction), \[TxGNN](https://github.com/mims-harvard/txgnn)). Training can take hours on a GPU, not months. |

| RAG + LLM explanations | \*\*Medium\*\* | Well-understood pattern (LangChain/LlamaIndex + embeddings). Main risk is bad biology in text — your project addresses that by requiring retrieved evidence. |

| Streamlit dashboard | \*\*Easy–Medium\*\* | Standard for data science FYPs. |

| PDF report generation | \*\*Easy\*\* | LaTeX or templated PDF is straightforward. |

| Docking \*\*top 5–10\*\* candidates in Docker | \*\*Medium–Hard\*\* | Doable with existing pipelines (\[NeuroDockAI-VinaFlow](https://github.com/DrFatimaKhatoon/NeuroDockAI-VinaFlow)), but protein/ligand prep is fiddly. |



\### What is the biggest risk (read this carefully)



\*\*Step 1 — building a knowledge graph by extracting relationships from PubMed abstracts — is the hardest part of the entire proposal.\*\*



Why:



\- You need \*\*Named Entity Recognition\*\* (find "Metformin", "BRCA1", "Diabetes" in text)

\- Then \*\*Relation Extraction\*\* (decide if the sentence means \*affects\*, \*causes\*, \*treats\*, etc.)

\- Errors in step 1 cascade into step 2

\- Running this at scale on millions of abstracts is \*\*PhD/research-lab level\*\*, not typical FYP scope



Existing tools (SciSpacy, PubTator) help, but building a \*\*reliable, continuously ingesting\*\* extraction pipeline is where many student projects stall for an entire semester.



\*\*Critical decision:\*\* Do you \*\*build\*\* the KG from literature, or \*\*start from\*\* Hetionet/PrimeKG and optionally \*\*add\*\* a small PubMed slice?



| Approach | 2-semester feasibility |

|----------|------------------------|

| Build full KG from PubMed at scale | \*\*Very risky\*\* — likely consumes both semesters |

| Use PrimeKG/Hetionet + limited PubMed enrichment (one disease domain, \~2k–5k abstracts) | \*\*Realistic\*\* |

| Use existing KG only, focus on prediction + RAG + docking | \*\*Most realistic\*\* |



Your proposal mentions PrimeKG/Hetionet as prior work but Step 1 reads like full literature extraction. For a panel defense, you should \*\*explicitly choose\*\* one of the above.



\---



\## Rough 2-semester timeline (recommended)



Assuming \~16 weeks per semester and 3 students:



\### Semester 1 — Foundation (must work end-to-end, even if crude)



| Weeks | Focus | Deliverable |

|-------|-------|-------------|

| 1–2 | Literature review, tool survey, pick base KG | Written survey + architecture diagram |

| 3–5 | Load PrimeKG or Hetionet; build graph in Neo4j/NetworkX | Working KG with basic queries |

| 6–9 | Train a \*\*simple\*\* GNN (GAT or RGCN) for drug–disease link prediction | Model with AUROC/MRR metrics |

| 10–12 | Baseline evaluation on held-out links | Results table + 2–3 case studies |

| 13–16 | Mid demo: input disease → top drug predictions | \*\*Working vertical slice\*\* |



\*\*Semester 1 exit criterion:\*\* Given a disease, the system returns ranked drug candidates from the KG. No RAG/docking yet — that is fine.



\### Semester 2 — Integration + polish



| Weeks | Focus | Deliverable |

|-------|-------|-------------|

| 1–4 | RAG module: retrieve PubMed passages for top predictions | Evidence-backed explanations |

| 5–8 | Docker + AutoDock Vina for \*\*top 5–10\*\* hypotheses only | Docking scores in pipeline |

| 9–11 | Streamlit dashboard + PDF dossier | User-facing system |

| 12–14 | Evaluation, ablation, comparison to baselines | Thesis chapter material |

| 15–16 | Final defense prep, documentation | Complete FYP |



\---



\## Team split (3 people)



| Student | Primary ownership |

|---------|-------------------|

| \*\*Person A\*\* | KG + GNN (PyTorch Geometric) |

| \*\*Person B\*\* | RAG + LLM integration + safety filter |

| \*\*Person C\*\* | Docking/Docker + Streamlit + report generation |



Everyone shares evaluation, documentation, and defense prep. Avoid silos: integrate early in Semester 1, even with dummy components.



\---



\## Hidden requirements (often overlooked)



1\. \*\*GPU access\*\* — GNN training on CPU is slow; check university lab or Colab Pro.

2\. \*\*Docker on Windows\*\* — Works, but bioinformatics containers are easier on Linux/WSL2. Budget time for environment setup.

3\. \*\*Protein structures for docking\*\* — Not every prediction has a clean Protein X with a PDB structure. You will need fallback rules (skip, use closest homolog, etc.).

4\. \*\*Drug identifiers\*\* — Must map drug names to SMILES/InChI for docking (PubChem, DrugBank).

5\. \*\*LLM cost\*\* — If using OpenAI/Claude APIs, cap usage; consider local models (Llama, Mistral) for RAG.

6\. \*\*Biology validation\*\* — Pick 1–2 known repurposing successes (e.g. metformin, thalidomide) as sanity checks.



\---



\## What makes this defensible to examiners



Strengths in your proposal:



\- Clear scope: \*\*hypotheses, not cures\*\*

\- Addresses real gap: passive search vs. closed-loop pipeline

\- Hybrid GNN + RAG is a coherent story

\- Docking adds a "physical plausibility" layer beyond pure AI



What examiners will probe skeptically:



\- \*"Did you build the KG or use an existing one?"\* — Have a clear answer.

\- \*"How do you know the GNN predictions are meaningful?"\* — Need metrics + case studies + known-drug validation.

\- \*"How do you prevent LLM hallucinations?"\* — RAG with citations; show examples where RAG catches unsupported claims.

\- \*"Is docking scientifically valid?"\* — Present as \*\*computational sanity check\*\*, not binding affinity proof.



\---



\## Bottom line



| Question | Answer |

|----------|--------|

| Is the \*\*idea\*\* valid for an FYP? | \*\*Yes\*\* — timely, research-oriented, good SDG alignment |

| Is it \*\*complete as written\*\* in 2 semesters? | \*\*Only with scope control\*\* |

| Biggest scope cut needed? | \*\*Do not build a full PubMed-to-KG pipeline from scratch\*\* |

| Minimum viable FYP? | Existing KG → GNN predictions → RAG evidence → dock top N → dashboard + report |

| Stretch goal? | Incremental PubMed ingestion for one disease area |



\---



\## Suggested scope statement for your supervisor/panel



> \*"We use PrimeKG (or Hetionet) as our primary knowledge graph. We implement GNN-based drug–disease link prediction, augment predictions with RAG-retrieved literature evidence, computationally validate top candidates via sandboxed AutoDock Vina docking, and deliver an interactive dashboard with downloadable research dossiers. Optional extension: enrich the KG with relation extraction from a focused PubMed corpus in one therapeutic area."\*



That version is \*\*honest, achievable, and still innovative\*\* — the innovation is the \*\*integrated closed loop\*\*, not rebuilding Hetionet.



\---



Share your specific questions next — for example:



\- "Can we really do GNNs with our coursework?"

\- "Do we need a supervisor from biology?"

\- "What if we have no GPU?"

\- "How is this different from just using ChatGPT on papers?"



I can go deep on each one with the same beginner-friendly, skeptical approach.



\## User



Now for the Knowledge graph, does PrimeKG/Hetionet contain the latest research material references and are timely updated?

Where would we get the research paper once we found the candidate papers for the specific relationships? Would we have to buy the subscription of those journal in order for our LLM to read that paper? 

Supervisor from biology, what are your suggesions?



\## Assistant



I'll look up how current PrimeKG and Hetionet are, how paper access works for RAG, and what kind of biology supervisor helps most.



\### Tool Web Search



```

{"searchTerm":"Hetionet knowledge graph last updated maintenance 2024","toolCallId":"tool\_6c6d0141-dfef-49c5-84bd-c35d0b14eab"}

```



\### Tool Web Search



```

{"searchTerm":"PrimeKG knowledge graph last updated version 2024 2025 data sources","toolCallId":"tool\_b85f4733-2dc8-456d-90f3-d2e343be369"}

```



\### Tool Web Search



```

{"searchTerm":"PubMed abstracts free access full text PMC open access RAG biomedical literature","toolCallId":"tool\_24075284-c849-4108-a365-e6caa70debb"}

```



\### Tool Web Search



```

{"searchTerm":"PrimeKG knowledge graph PMID citation edge provenance June 2021 cutoff","toolCallId":"tool\_a3704125-19b0-4db6-8e0c-07594853158"}

```



\### Tool Web Search



```

{"searchTerm":"NCBI E-utilities PubMed API free rate limit abstracts PMC open access subset","toolCallId":"tool\_88b694e6-1794-412a-a232-afe3f8515a9"}

```



\## Assistant



These three questions hit a real design choice in your project: \*\*where the facts come from\*\*, \*\*where the evidence comes from\*\*, and \*\*who helps you judge whether the biology makes sense\*\*. Here is a skeptical, beginner-friendly breakdown.



\---



\## 1. Do PrimeKG / Hetionet have the latest research and stay updated?



\*\*Short answer: No — not in the way you might expect.\*\* They are \*\*snapshots\*\*, not live feeds of new papers.



\### Think of them like this



| Analogy | What it means |

|---------|----------------|

| \*\*Google Maps offline download\*\* | Useful, structured, but frozen at download time |

| \*\*Not Google Search\*\* | They do not auto-update when a new paper is published tonight |



A knowledge graph (KG) is a \*\*pre-built map\*\* of relationships like \*Drug → targets → Protein → associated with → Disease\*. That map is assembled from \*\*curated databases\*\* (DrugBank, MONDO, DisGeNET, etc.), not by reading every new PubMed paper daily.



\---



\### Hetionet — mostly outdated for “latest research”



| Fact | Detail |

|------|--------|

| \*\*Last real data update\*\* | \*\*November 2018\*\* (version 1.0) |

| \*\*Maintenance\*\* | Essentially \*\*frozen\*\* — the GitHub repo is mainly a download location |

| \*\*What it contains\*\* | \~47k nodes, \~2.25M relationships from 2018-era sources |

| \*\*Good for FYP?\*\* | Yes for learning GNNs on a smaller, well-studied graph — \*\*not\*\* if you need 2024–2026 literature |



Hetionet is like using a \*\*2018 textbook\*\*: still useful for methods and demos, but missing \~7 years of biomedical progress.



\---



\### PrimeKG (original) — better, but still a snapshot



| Fact | Detail |

|------|--------|

| \*\*Published\*\* | Nature Scientific Data, 2023 |

| \*\*Data cutoff\*\* | \*\*June 1, 2021\*\* (intentionally fixed for validation) |

| \*\*Sources\*\* | 20+ curated databases merged into one graph |

| \*\*Updates?\*\* | Not automatic. The authors provide \*\*rebuild scripts\*\* so researchers can make a newer version themselves |

| \*\*Paper references on edges?\*\* | \*\*Most edges do not point to a specific PMID.\*\* They come from databases like DrugBank or MONDO, which may have their own provenance |



So PrimeKG is \*\*much richer than Hetionet\*\*, but the public release you download is still roughly \*\*5 years behind today\*\* (as of 2026).



\---



\### PrimeKG-Plus — fresher, but still not “live”



A newer extension called \*\*PrimeKG-Plus\*\* rebuilds PrimeKG using database releases through \*\*December 2025\*\*. That is a big improvement.



But be precise about what it is:



\- \*\*`primekg\_plus.csv`\*\*: updated \*\*database\*\* edges only — \*\*no PubMed-derived edges\*\*

\- \*\*`primekg\_plus\_rd.csv`\*\*: adds \*\*550 expert-validated literature edges\*\* for \*\*4 rare neurological diseases only\*\* (Canavan, Batten, NPC, Tay–Sachs)



So even the “literature-augmented” version is \*\*not\*\* a general, continuously updated PubMed graph. It is a \*\*carefully curated add-on for a tiny disease subset\*\*.



\---



\### The honest picture for your project



```mermaid

flowchart LR

&#x20;   A\[New paper published today] --> B\[PubMed]

&#x20;   C\[PrimeKG / Hetionet] --> D\[Snapshot from curated DBs]

&#x20;   B -.->|NOT auto-synced| C

&#x20;   E\[Your RAG module] --> B

&#x20;   F\[GNN on KG] --> C

```



| Layer | How “timely” is it? |

|-------|---------------------|

| \*\*KG (PrimeKG/Hetionet)\*\* | Weeks to \*\*years\*\* behind; snapshot |

| \*\*RAG (PubMed search)\*\* | Can be \*\*near real-time\*\* for abstracts |

| \*\*Your innovation\*\* | KG finds candidates; RAG finds \*\*fresh evidence\*\* for those candidates |



\*\*This is actually a strong project story\*\*, if you say it clearly:



> \*“We use PrimeKG as a structured backbone for link prediction. Because the KG is a snapshot, we use RAG over live PubMed to retrieve current evidence for each predicted drug–disease link.”\*



That turns a weakness into a feature — \*\*do not hide it in your defense\*\*.



\---



\## 2. Where do you get papers for RAG? Do you need journal subscriptions?



\*\*Short answer: For an FYP, you almost certainly do NOT need paid journal subscriptions.\*\* You can build a solid RAG system using \*\*free, legal sources\*\*.



\### Step-by-step: what happens when your system finds a candidate link



Example: GNN predicts \*Metformin → Alzheimer’s disease\*.



Your RAG module would:



1\. \*\*Search PubMed\*\* for papers mentioning both entities

2\. \*\*Get paper IDs\*\* (called PMIDs)

3\. \*\*Fetch text\*\* the API allows you to read

4\. \*\*Feed that text to the LLM\*\* as context (not the LLM’s memory)

5\. \*\*Generate an explanation with citations\*\*



\---



\### What is free vs paid



| Content | Free? | Good enough for FYP? |

|---------|-------|----------------------|

| \*\*PubMed abstracts\*\* | \*\*Yes\*\* — via \[NCBI E-utilities API](https://www.ncbi.nlm.nih.gov/home/develop/api/) | \*\*Yes — this is the standard approach\*\* |

| \*\*PMC Open Access full text\*\* | \*\*Yes\*\* — for a large subset of papers | Nice bonus, not required |

| \*\*Paywalled full PDFs\*\* (Elsevier, Springer, etc.) | \*\*No\*\* — unless your university has access | \*\*Not needed\*\* for core system |



\### Important beginner distinction



\- \*\*PubMed\*\* = search engine + metadata + \*\*abstracts\*\* (usually free)

\- \*\*Publisher website\*\* = often paywalled \*\*full PDF\*\*

\- \*\*PMC (PubMed Central)\*\* = free full-text archive for \*\*open-access\*\* papers only



Roughly \*\*30–40%+ of biomedical papers\*\* have some form of free full text in PMC. The rest may only have a free \*\*abstract\*\* — and that is still usable.



\---



\### Practical RAG strategy (recommended for your FYP)



```

Tier 1 (always):  PubMed abstract via E-utilities  → FREE, fast, legal

Tier 2 (if available): PMC Open Access full text   → FREE when PMCID exists

Tier 3 (optional): University library access         → For manual validation only

Tier 4 (skip):     Scraping paywalled PDFs           → DON'T DO THIS

```



\*\*Why abstracts are enough for v1:\*\*



\- Most key claims (\*“Drug X inhibits Protein Y”\*) appear in the abstract

\- Many published RAG systems (PubMedQA-style) use \*\*abstract-only\*\* retrieval

\- Your goal is \*\*evidence-backed explanation\*\*, not reading every supplementary figure



\### Technical access (no subscription needed)



1\. Create a \*\*free NCBI account\*\*

2\. Get a \*\*free API key\*\* (raises limit from 3 to 10 requests/second)

3\. Use Python libraries: `Biopython`, `pymed`, or `LangChain` PubMed loaders

4\. For PMC full text: use `ELink` with `pubmed\_pmc` to check if open access exists



Example flow in plain English:



```

Prediction: Drug A – Disease B

&#x20;   ↓

Search PubMed: "Drug A" AND "Disease B"

&#x20;   ↓

Get top 10 PMIDs

&#x20;   ↓

Fetch abstracts (always works)

&#x20;   ↓

Try PMC full text (works for some papers)

&#x20;   ↓

Embed + retrieve relevant chunks

&#x20;   ↓

LLM writes: "Based on \[PMID:12345678], Drug A affects Protein X..."

```



\### What about the LLM “reading” the paper?



The LLM does not magically access journals. \*\*Your code fetches text first\*\*, then passes it to the LLM as input. No subscription is charged to the LLM — you are responsible for legally obtaining the text you feed it.



\*\*For your panel:\*\* Say clearly that you use \*\*NCBI’s official APIs\*\* and only ingest \*\*abstracts and PMC Open Access full text\*\*. That is standard, ethical, and defensible.



\---



\## 3. Do you need a biology supervisor? My suggestions



\*\*Short answer: Not strictly required, but a biology/pharmacy/bioinformatics co-advisor would significantly strengthen the project and your defense.\*\*



Your primary supervisor will likely be from \*\*Computing / Data Science\*\* — that is correct for the software and ML pipeline. But this project makes \*\*biological claims\*\*, even if framed as hypotheses. Someone who can sanity-check biology saves you from embarrassing mistakes.



\---



\### What each supervisor type brings



| Role | Covers | Example help |

|------|--------|--------------|

| \*\*Primary (CS/Data Science)\*\* | Architecture, GNN, RAG, Docker, Streamlit, evaluation metrics | “Is your train/test split valid?” |

| \*\*Co-supervisor (Biology/Pharmacy/Bioinformatics)\*\* | Biological plausibility, case studies, pathway interpretation, docking target choice | “This protein is not a realistic target for that drug class” |

| \*\*Industry advisor (optional)\*\* | Real-world workflow, regulatory framing | “How pharma teams evaluate repurposing hypotheses” |



\---



\### What a biology co-supervisor would specifically help with



1\. \*\*Pick 2–3 validation case studies\*\* with known repurposing stories (e.g., thalidomide, metformin, sildenafil) to prove your pipeline finds sensible results

2\. \*\*Review top predictions\*\* — flag obviously wrong links before your defense

3\. \*\*Choose protein targets for docking\*\* — not every drug–disease pair has a clean “Protein X” to dock against

4\. \*\*Interpret pathways\*\* — help you explain Drug → Protein → Pathway → Disease in panel-friendly language

5\. \*\*Frame claims safely\*\* — “computational hypothesis” vs “this drug cures X”

6\. \*\*Connect to Riphah\*\* — School of Pharmacy, medical campus, or bioinformatics faculty



\---



\### If you cannot get a biology co-supervisor



Still doable, with guardrails:



| Strategy | How |

|----------|-----|

| \*\*Use gold-standard benchmarks\*\* | Known drug–indication pairs from DrugBank / RepurposeDrugs |

| \*\*Limit disease scope\*\* | One therapeutic area (e.g., diabetes, Alzheimer’s) you can study deeply |

| \*\*External review sessions\*\* | One pharmacy faculty member reviews 10 predictions once per semester |

| \*\*Conservative language\*\* | Always say “hypothesis supported by literature + docking score,” never “proven treatment” |

| \*\*Citation requirement\*\* | RAG must cite PMIDs; no citation = flag as low confidence |



\---



\### Who to approach at a university like Riphah



Look for faculty who touch \*\*any\*\* of these:



\- Pharmacology / Clinical Pharmacy

\- Bioinformatics / Computational Biology

\- Biochemistry / Molecular Biology

\- Medical research (if cross-campus collaboration is allowed)



You do not need a full professor running the project — even a \*\*monthly 30-minute review\*\* from a pharmacy lecturer can be enough.



\*\*Pitch to them:\*\*



> \*“We are not claiming to discover drugs. We need help validating that our top 10 AI-generated hypotheses are biologically plausible and choosing appropriate protein targets for computational docking.”\*



That is a \*\*small, realistic ask\*\* — much easier to get a yes.



\---



\## How these three answers fit together (recommended design)



```

┌─────────────────────────────────────────────────────────┐

│  LAYER 1: Knowledge Graph (PrimeKG)                     │

│  Role: Structured map for GNN link prediction           │

│  Limitation: Snapshot (\~2021–2025 depending on version) │

└────────────────────────┬────────────────────────────────┘

&#x20;                        │ predicted drug–disease links

&#x20;                        ▼

┌─────────────────────────────────────────────────────────┐

│  LAYER 2: RAG over live PubMed                          │

│  Role: Fresh evidence + explanations with PMIDs         │

│  Access: FREE abstracts + PMC Open Access (no subs)     │

└────────────────────────┬────────────────────────────────┘

&#x20;                        │ top hypotheses with evidence

&#x20;                        ▼

┌─────────────────────────────────────────────────────────┐

│  LAYER 3: Biology sanity check                          │

│  Role: Co-supervisor / pharmacy advisor validates       │

│  Output: "Plausible" vs "Likely artifact" flags         │

└────────────────────────┬────────────────────────────────┘

&#x20;                        ▼

┌─────────────────────────────────────────────────────────┐

│  LAYER 4: Docking (AutoDock Vina)                       │

│  Role: Computational fit check on selected protein      │

└─────────────────────────────────────────────────────────┘

```



\---



\## Bottom-line answers



| Your question | Honest answer |

|---------------|---------------|

| Are PrimeKG/Hetionet up to date? | \*\*No — snapshots, not live literature feeds.\*\* Use PrimeKG-Plus if you want fresher DB data; use RAG for current papers. |

| Do we need journal subscriptions? | \*\*No for core FYP work.\*\* PubMed abstracts are free; PMC Open Access adds free full text for many papers. |

| Biology supervisor? | \*\*Strongly recommended as co-supervisor\*\*, not mandatory — but get someone to review biological plausibility of top predictions. |



\---



If you want, next we can go deeper on any of these:



\- \*\*PrimeKG vs Hetionet — which should you pick?\*\*

\- \*\*Exact RAG architecture\*\* (abstract-only vs abstract + PMC full text)

\- \*\*How to write the “data timeliness” section\*\* for your proposal/defense

\- \*\*Email template\*\* to ask a pharmacy faculty member to be co-supervisor



\## User



now tell me what will the input for our GNN for it needs to predict the links that will be fed to LLM to search and go through the relevant papers and then generate docking scripts and eventually the report? is there any other step included in this? how the workflow will start?



\## Assistant



\## The big picture first



Your system is a \*\*pipeline\*\* — like an assembly line. Each step takes the output of the previous step and adds something new.



\*\*Important:\*\* The GNN does \*\*not\*\* read research papers. It only reads the \*\*knowledge graph\*\* (a structured map of known relationships). Papers enter later, when the \*\*RAG/LLM\*\* step searches PubMed for evidence.



\---



\## How the workflow starts (user perspective)



A researcher opens your \*\*Streamlit dashboard\*\* and provides a starting point. That can be one of:



| Input mode | Example | What the system does |

|------------|---------|----------------------|

| \*\*Disease-first\*\* (most common) | \*"Find repurposing candidates for Type 2 Diabetes"\* | Predict which \*\*drugs\*\* might connect to that disease |

| \*\*Drug-first\*\* | \*"What new diseases might Metformin treat?"\* | Predict which \*\*diseases\*\* might connect to that drug |

| \*\*Batch / autonomous\*\* | No specific query — run on top-N missing links globally | System finds the most promising \*\*drug–disease pairs\*\* across the whole graph |



For an FYP demo, \*\*disease-first\*\* is the easiest story to tell.



\---



\## Complete workflow (every step)



```mermaid

flowchart TD

&#x20;   A\[START: User selects a disease] --> B\[Step 0: Load Knowledge Graph]

&#x20;   B --> C\[Step 1: GNN Link Prediction]

&#x20;   C --> D\[Step 2: Rank \& Filter Top Candidates]

&#x20;   D --> E\[Step 3: RAG - Search PubMed]

&#x20;   E --> F\[Step 4: LLM - Explain Pathway with Citations]

&#x20;   F --> G\[Step 5: Resolve Protein Target for Docking]

&#x20;   G --> H\[Step 6: Generate \& Run Docking Scripts in Docker]

&#x20;   H --> I\[Step 7: Safety / ADME Review by LLM]

&#x20;   I --> J\[Step 8: Generate PDF Report + Dashboard Display]

&#x20;   J --> K\[END: Downloadable Research Dossier]

```



There \*\*are\*\* a few steps beyond GNN → LLM → docking → report. Steps \*\*0, 2, 5, 7\*\* are easy to miss but important.



\---



\## Step 0 — Load and prepare the Knowledge Graph (before GNN)



\*\*This happens once at setup, not every user query.\*\*



| What | Detail |

|------|--------|

| \*\*Input\*\* | PrimeKG (or Hetionet) CSV files — millions of edges like `Metformin → targets → AMPK` |

| \*\*Processing\*\* | Convert to a graph format (PyTorch Geometric / NetworkX / Neo4j) |

| \*\*Node types\*\* | Drug, Disease, Protein/Gene, Pathway, etc. |

| \*\*Edge types\*\* | `treats`, `targets`, `associated\_with`, `interacts\_with`, etc. |



Think of this as loading the \*\*map\*\* before the AI can navigate it.



\---



\## Step 1 — GNN input and what it predicts



\### What the GNN actually receives as input



The GNN does \*\*not\*\* get PDFs or abstracts. It gets:



```

1\. Graph structure

&#x20;  - All nodes (drugs, diseases, proteins, ...)

&#x20;  - All known edges (relationships already in the KG)



2\. Node features (embeddings)

&#x20;  - Numbers describing each node

&#x20;  - Can be: learned from scratch, or pre-computed (drug fingerprints, disease text embeddings)



3\. A query (link to predict)

&#x20;  - Source node:  Drug X   (or Disease Y, depending on direction)

&#x20;  - Target node:  Disease Y  (or Drug X)

&#x20;  - Relation type: "indication" / "drug-disease association"

```



\### Concrete example



\*\*User asks:\*\* \*"Find drugs for Alzheimer's Disease"\*



```

GNN Input:

├── Full graph: 129,000 nodes, 7M edges (PrimeKG)

├── Query disease node: "Alzheimer's Disease" (MONDO ID: MONDO:0004975)

└── Task: For every drug node in the graph, score:

&#x20;        P(drug ──treats──► Alzheimer's) = ?

```



The GNN looks at \*\*neighbors and patterns\*\* in the graph:



```

Known:  Drug A → targets → Protein X

Known:  Protein X → associated\_with → Alzheimer's

Missing: Drug A → ??? → Alzheimer's   ← GNN predicts this link

```



\### GNN output



A \*\*ranked list\*\* of candidate drug–disease pairs with scores:



| Rank | Drug | Disease | Score | Already in KG? |

|------|------|---------|-------|----------------|

| 1 | Memantine | Alzheimer's | 0.94 | Yes (known — good sanity check) |

| 2 | Metformin | Alzheimer's | 0.87 | \*\*No — novel hypothesis\*\* |

| 3 | Aspirin | Alzheimer's | 0.81 | No |

| ... | ... | ... | ... | ... |



Only \*\*top K\*\* (e.g., top 5–10 \*\*novel\*\* predictions) move to the next step. Known pairs can be used for validation but are not interesting "discoveries."



\---



\## Step 2 — Rank, filter, and enrich (easy to forget)



Before sending to the LLM, your pipeline should:



| Action | Why |

|--------|-----|

| \*\*Remove known links\*\* | GNN might re-discover what's already in the KG |

| \*\*Keep top K\*\* | You cannot dock and RAG 500 candidates — too slow/expensive |

| \*\*Extract intermediate path\*\* | Drug → Protein → Disease chain from the graph |

| \*\*Resolve entity names \& IDs\*\* | `DB00945` → "Metformin", `MONDO:0004975` → "Alzheimer's" |



\*\*Output of Step 2\*\* — a structured record per candidate:



```json

{

&#x20; "drug": "Metformin",

&#x20; "drug\_id": "DB00945",

&#x20; "disease": "Alzheimer's Disease",

&#x20; "disease\_id": "MONDO:0004975",

&#x20; "gnn\_score": 0.87,

&#x20; "pathway": \["Metformin", "→ targets →", "AMPK", "→ involved\_in →", "Alzheimer's"],

&#x20; "intermediate\_proteins": \["AMPK", "TAU", "BACE1"],

&#x20; "status": "novel\_hypothesis"

}

```



This JSON is the \*\*handoff object\*\* from GNN world → LLM world.



\---



\## Step 3 — RAG: search PubMed for evidence



\*\*Input:\*\* The structured record from Step 2.



\*\*What happens:\*\*



```

For Metformin + Alzheimer's:

&#x20; 1. Build search queries:

&#x20;    - "Metformin AND Alzheimer"

&#x20;    - "Metformin AND AMPK AND neurodegeneration"

&#x20; 2. Query PubMed API (E-utilities) → get PMIDs

&#x20; 3. Fetch abstracts (free)

&#x20; 4. Try PMC Open Access for full text (when available)

&#x20; 5. Chunk text, embed, retrieve top relevant passages

```



\*\*Output:\*\* Retrieved evidence chunks with PMIDs:



```

\[PMID: 28473621] "...Metformin activates AMPK pathway which reduces 

&#x20;                  amyloid-beta accumulation in Alzheimer's models..."



\[PMID: 30123456] "...AMPK signaling is impaired in Alzheimer's disease 

&#x20;                  and represents a therapeutic target..."

```



\---



\## Step 4 — LLM: explain the biological pathway



\*\*Input:\*\* GNN path + retrieved PubMed chunks.



\*\*Task:\*\* The LLM writes a \*\*grounded explanation\*\* — it must use retrieved text, not guess from memory.



\*\*Example output:\*\*



> \*\*Hypothesis:\*\* Metformin may be relevant to Alzheimer's Disease.

>

> \*\*Proposed mechanism (multi-hop):\*\*

> Metformin → activates AMPK → reduces tau phosphorylation → may slow Alzheimer's progression

>

> \*\*Supporting evidence:\*\*

> - \[PMID:28473621]: Metformin reduced amyloid-beta in mouse models...

> - \[PMID:30123456]: AMPK dysfunction is linked to Alzheimer's pathology...

>

> \*\*Confidence:\*\* Moderate — preclinical evidence exists; no approved indication.



This is where your project adds value over "just ask ChatGPT" — every claim should trace to a \*\*retrieved PMID\*\*.



\---



\## Step 5 — Resolve protein target for docking (another hidden step)



Docking needs \*\*3D structures\*\*, not just names. This step bridges symbolic AI → physical simulation.



\*\*Input:\*\* Drug name + intermediate proteins from the graph path.



\*\*What happens:\*\*



```

Metformin → targets → AMPK

&#x20; ↓

Look up AMPK in UniProt → get protein ID (e.g., P54646)

&#x20; ↓

Find 3D structure in PDB (e.g., 4CFE)

&#x20; ↓

Get Metformin structure from PubChem → SMILES → convert to .pdbqt

&#x20; ↓

Define docking box around binding site

```



\*\*If no 3D structure exists:\*\* skip docking for that candidate, or use a homolog — document the fallback.



\*\*Output:\*\* File paths ready for the docking script:



```

receptor.pdbqt  (protein)

ligand.pdbqt    (drug)

config.txt      (docking box coordinates)

```



\---



\## Step 6 — Generate and run docking scripts (Docker sandbox)



\*\*Input:\*\* Protein + ligand files from Step 5.



\*\*What happens:\*\*



```bash

\# Auto-generated script (runs inside Docker container)

vina --receptor AMPK.pdbqt \\

&#x20;    --ligand Metformin.pdbqt \\

&#x20;    --config config.txt \\

&#x20;    --out Metformin\_AMPK\_out.pdbqt

```



\*\*Output:\*\* Binding affinity score (lower = stronger predicted binding):



```

Metformin ↔ AMPK:  -7.2 kcal/mol  (moderate binding — plausible)

Aspirin ↔ AMPK:    -4.1 kcal/mol  (weak — less plausible)

```



This is a \*\*computational sanity check\*\*, not proof the drug works in humans.



\---



\## Step 7 — Safety / ADME review (LLM reviewer agent)



From your proposal — often overlooked but included:



\*\*Input:\*\* All gathered info (drug properties, disease, evidence, docking score).



\*\*LLM checks for flags like:\*\*



| Check | Example flag |

|-------|--------------|

| Known toxicity | "This drug has hepatotoxicity warnings" |

| ADME issues | "Poor blood-brain barrier penetration — problematic for Alzheimer's" |

| Contraindications | "Already contraindicated in renal impairment" |

| Dual-use concerns | Basic screening only |



\*\*Output:\*\* Risk tags attached to the hypothesis:



```

⚠️ ADME Warning: Metformin BBB penetration is limited — may reduce CNS efficacy

✅ Safety: Well-established human safety profile (FDA approved since 1994)

```



\---



\## Step 8 — Report generation + dashboard



\*\*Input:\*\* Everything from Steps 1–7.



\*\*Output:\*\*



1\. \*\*Streamlit dashboard\*\* — interactive view of pathways, evidence, docking scores

2\. \*\*PDF dossier\*\* (LaTeX) — downloadable research report per hypothesis



Report sections typically:



```

1\. Executive Summary

2\. Predicted Drug–Disease Link (GNN score)

3\. Biological Pathway Explanation (with PMIDs)

4\. Literature Evidence Table

5\. Molecular Docking Results

6\. Safety / ADME Flags

7\. Conclusion: "Worth further pre-clinical investigation? Yes/No"

8\. References

```



\---



\## End-to-end example (one complete run)



\*\*User action:\*\* Opens dashboard → selects \*"Alzheimer's Disease"\* → clicks \*"Run Analysis"\*



```

START

&#x20; │

&#x20; ├─ \[0] Load PrimeKG graph (already in memory)

&#x20; │

&#x20; ├─ \[1] GNN scores all drugs → Metformin scores 0.87 (rank #2, novel)

&#x20; │

&#x20; ├─ \[2] Filter: keep top 5 novel candidates; extract path:

&#x20; │       Metformin → AMPK → Alzheimer's

&#x20; │

&#x20; ├─ \[3] RAG searches PubMed → finds 8 relevant abstracts

&#x20; │

&#x20; ├─ \[4] LLM writes pathway explanation citing PMIDs

&#x20; │

&#x20; ├─ \[5] Resolve AMPK → PDB structure 4CFE; Metformin → PubChem SMILES

&#x20; │

&#x20; ├─ \[6] Docker runs AutoDock Vina → score: -7.2 kcal/mol

&#x20; │

&#x20; ├─ \[7] LLM safety review → flags limited BBB penetration

&#x20; │

&#x20; └─ \[8] PDF dossier generated + shown on dashboard

&#x20; 

END → User downloads "Metformin-Alzheimers-Hypothesis-Dossier.pdf"

```



\---



\## What each component reads vs produces



| Step | Reads | Produces |

|------|-------|----------|

| \*\*0. KG Load\*\* | PrimeKG CSV | In-memory graph |

| \*\*1. GNN\*\* | Graph + disease query | Ranked drug–disease scores |

| \*\*2. Filter/Enrich\*\* | GNN output + graph paths | Structured hypothesis JSON |

| \*\*3. RAG\*\* | Hypothesis JSON → PubMed API | Evidence chunks + PMIDs |

| \*\*4. LLM Explain\*\* | Paths + evidence chunks | Pathway narrative with citations |

| \*\*5. Target Resolve\*\* | Protein names → UniProt/PDB/PubChem | `.pdbqt` files |

| \*\*6. Docking\*\* | `.pdbqt` files → AutoDock Vina | Binding affinity scores |

| \*\*7. Safety Review\*\* | Drug info + hypothesis | Risk flags |

| \*\*8. Report\*\* | All above | PDF + dashboard view |



\---



\## Semester 1 vs Semester 2 build order



Build a \*\*thin vertical slice\*\* early — one disease, one drug, end-to-end — even if crude:



| Semester | Build | Demo milestone |

|----------|-------|----------------|

| \*\*Sem 1\*\* | Steps 0 → 1 → 2 | \*"Given Alzheimer's, GNN returns top 10 drug candidates"\* |

| \*\*Sem 2\*\* | Steps 3 → 8 | \*"Full pipeline: prediction → evidence → docking → PDF"\* |



\---



\## Common beginner misconceptions (worth clearing up)



| Misconception | Reality |

|---------------|---------|

| "GNN reads papers" | \*\*No\*\* — GNN only reads the graph |

| "LLM discovers the link" | \*\*No\*\* — GNN discovers; LLM \*\*explains\*\* with evidence |

| "Docking proves the drug works" | \*\*No\*\* — it only checks if the molecule \*\*might fit\*\* a protein in silico |

| "We process all predictions" | \*\*No\*\* — only top 5–10 go through RAG + docking (cost/time) |

| "User uploads papers" | \*\*No\*\* — system fetches from PubMed automatically |



\---



\## Minimum viable workflow (if time is tight)



If two semesters feel tight, this is the \*\*smallest complete story\*\*:



```

User picks disease

&#x20;   → GNN predicts top 5 drugs

&#x20;   → RAG finds PubMed evidence + LLM explains

&#x20;   → Dock top 3 only

&#x20;   → PDF report for top 1

```



Steps 7 (safety review) can start as a simple rule-based checklist and upgrade to LLM later.



\---



Want me to next draw the \*\*exact data schema\*\* (JSON fields between each step), or a \*\*Semester 1 sprint plan\*\* for getting Step 0–2 working first?



\## User



So the user input converts into embeddings to be searched from KG on which GNN runs and predicts the missing link which gives the top candidates. and then RAG and next process starts. Give brief answer



\## Assistant



\*\*Almost — one small correction.\*\*



The user input (e.g. \*"Alzheimer's Disease"\*) is \*\*not\*\* turned into an embedding to search the KG like a vector database. It is \*\*mapped to a node\*\* in the graph (e.g. `MONDO:0004975`).



Then:



1\. \*\*GNN\*\* uses the full graph + that disease node → scores missing \*\*drug–disease\*\* links → returns \*\*top candidates\*\*

2\. \*\*RAG\*\* takes each candidate pair → searches \*\*PubMed\*\* for evidence

3\. \*\*LLM\*\* explains the pathway using those papers

4\. \*\*Docking\*\* tests drug–protein fit computationally

5\. \*\*Report\*\* compiles everything into a dossier



\*\*In one line:\*\* User picks a disease → GNN ranks drug candidates from the graph → RAG + LLM find and explain evidence → docking validates → report is generated.



\## User



Okay do we map the alzhimers to its id using NER or how? because user's input can be mistaken or mispelled or it can be sentence or we'll only provide a dropdown which I think is not the best option



\## Assistant



\*\*Not NER first — entity linking against your KG vocabulary.\*\*



NER is for \*finding\* entities inside free text. Your job is simpler: \*\*match what the user typed to a known disease node in PrimeKG\*\*.



\---



\## Recommended approach (best for FYP)



\*\*Hybrid: fuzzy search + disambiguation, not a plain dropdown.\*\*



```

User types: "alzheimers" / "Alzheimer Disease" / "memory loss disease"

&#x20;      ↓

Search KG disease names + synonyms (MONDO/UMLS labels from PrimeKG)

&#x20;      ↓

Fuzzy match (RapidFuzz / embedding similarity)

&#x20;      ↓

Show top 3 matches → user confirms one

&#x20;      ↓

Lock to node ID: MONDO:0004975

&#x20;      ↓

GNN runs on that node

```



\---



\## Three input modes (practical)



| Input type | How to handle |

|------------|---------------|

| \*\*Short name / typo\*\* `"alzheimers"` | Fuzzy string match against KG synonyms |

| \*\*Correct name\*\* `"Alzheimer's Disease"` | Direct lookup → node ID |

| \*\*Sentence\*\* `"find drugs for early onset dementia"` | SciSpacy NER → extract disease mention → then link to KG node |



Use NER \*\*only when input is a sentence\*\*. For normal queries, fuzzy lookup is enough.



\---



\## Why not dropdown-only?



\- Bad UX for 10,000+ diseases

\- Researchers know names, not IDs

\- Autocomplete + \*"Did you mean…?"\* is standard (like PubMed/Google)



\---



\## Minimal implementation



1\. Build a \*\*lookup table\*\* from PrimeKG: `{name, synonyms} → node\_id`

2\. \*\*Autocomplete\*\* as user types (Streamlit `st\_searchbox` or similar)

3\. \*\*Confirm screen\*\*: \*"You selected: Alzheimer's Disease (MONDO:0004975)"\*

4\. If confidence < threshold → ask user to pick from top 3



\*\*One line:\*\* Map user text → KG node via \*\*fuzzy synonym lookup\*\*, use \*\*NER only for sentence input\*\*, and always \*\*confirm before GNN runs\*\*.



\## User



Now as we have decided not to build the knowledge graph from scratch, but we are going to ingest the new articles in the existing graph like if we use PrimeKG as well right?



\## Assistant



\*\*Yes — that is a valid and smarter middle path.\*\* But be precise about what “ingesting new articles into PrimeKG” actually means, because there are two very different things:



\---



\## Two ways to handle “new literature”



| Approach | What it does | Updates KG? |

|----------|--------------|---------------|

| \*\*A. RAG at query time\*\* | When GNN finds a candidate, search PubMed for fresh evidence | \*\*No\*\* — papers used for explanation only |

| \*\*B. KG enrichment\*\* | Extract new triples from papers → \*\*add edges to PrimeKG\*\* | \*\*Yes\*\* — graph grows over time |



Your proposal can include \*\*both\*\*, but they serve different purposes:



```

PrimeKG (base graph, snapshot)

&#x20;       +

New article ingestion (optional enrichment)  →  GNN sees new edges

&#x20;       +

RAG at query time (always)                   →  LLM gets latest evidence

```



\---



\## What “ingesting into PrimeKG” actually looks like



You are \*\*not\*\* rebuilding PrimeKG. You are \*\*adding new edges\*\* to it:



```

Existing PrimeKG edge:

&#x20; Metformin → targets → AMPK



New paper says:

&#x20; "Drug X inhibits Protein Y in Alzheimer's models"



Your pipeline extracts:

&#x20; Drug X → targets → Protein Y

&#x20; Protein Y → associated\_with → Alzheimer's



You add these as NEW edges → GNN can now use them for link prediction

```



\*\*Steps for enrichment (limited scope):\*\*



1\. Fetch new abstracts from PubMed (e.g. last 2 years, one disease area)

2\. Run NER + relation extraction → get triples

3\. \*\*Normalize entities\*\* to PrimeKG IDs (Metformin → DrugBank ID, etc.)

4\. \*\*Validate\*\* — skip low-confidence or unmapped entities

5\. Append new edges to the graph

6\. Retrain / fine-tune GNN on the enriched graph



\---



\## Realistic FYP scope for ingestion



\*\*Do NOT try:\*\* continuous ingestion of all PubMed (millions of papers) — that alone is a PhD project.



\*\*DO try:\*\*



| Scope limit | Example |

|-------------|---------|

| \*\*One disease domain\*\* | Alzheimer's, Diabetes, or a rare disease |

| \*\*Time window\*\* | Last 1–2 years of papers |

| \*\*Volume cap\*\* | 500–2,000 abstracts max |

| \*\*Human/ rule validation\*\* | Only add edges where entity mapping confidence is high |



This matches what \*\*PrimeKG-Plus\*\* did for 4 rare diseases — curated, not automated at scale.



\---



\## Recommended architecture for your project



```

┌─────────────────────────────────────────┐

│  BASE: PrimeKG (download, don't build)  │

└──────────────────┬──────────────────────┘

&#x20;                  │

┌──────────────────▼──────────────────────┐

│  ENRICHMENT (Semester 2 stretch goal)   │

│  • PubMed fetch (focused corpus)        │

│  • NER + RE → new triples               │

│  • Entity linking to PrimeKG IDs        │

│  • Append validated edges               │

└──────────────────┬──────────────────────┘

&#x20;                  │

┌──────────────────▼──────────────────────┐

│  GNN on enriched graph → predictions      │

└──────────────────┬──────────────────────┘

&#x20;                  │

┌──────────────────▼──────────────────────┐

│  RAG (always) → live PubMed evidence      │

└───────────────────────────────────────────┘

```



\---



\## Semester split



| Semester | Focus |

|----------|-------|

| \*\*Sem 1\*\* | PrimeKG as-is → GNN → top candidates (no ingestion yet) |

| \*\*Sem 2\*\* | Add limited ingestion + RAG + docking + report |



If ingestion runs late, you still have a complete FYP because RAG covers timeliness at query time.



\---



\## One-line summary



\*\*Yes — use PrimeKG as the base and optionally enrich it with new article-derived edges in a narrow domain.\*\* Keep RAG for live evidence. Full-scale ingestion is out of scope; focused enrichment (one disease, \~1–2k papers) is a strong, defensible contribution.



\## User



In this way, if we enrich our graph, our LLM will have to check fewer new articles and the GNN will be able to find better and updated links. right? give brief answer



\## Assistant



\*\*Mostly yes — with one nuance.\*\*



\*\*GNN:\*\* Enriching the graph gives it \*\*newer, more complete edges\*\*, so link prediction improves and catches relationships that were missing from the old PrimeKG snapshot.



\*\*RAG/LLM:\*\* It may need to search \*\*fewer papers\*\* for background context, because some connections are already in the graph. But it should \*\*still search PubMed\*\* for the specific drug–disease candidate — to get \*\*fresh evidence and citations\*\* for the report.



\*\*In short:\*\* Enrichment makes the \*\*graph smarter\*\*; RAG still validates and \*\*explains\*\* each prediction with paper evidence.

