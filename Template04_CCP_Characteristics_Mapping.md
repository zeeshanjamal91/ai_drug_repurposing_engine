# Complex Computing Problem Characteristics Mapping Sheet

**Riphah International University Lahore, Pakistan**  
**Riphah School of Computing & Innovation**

---

**Project Title:** AI-Based Autonomous Literature Discovery Engine for Drug Repurposing  

**Project ID:** *[Issued by FYP Manager — TO BE FILLED]*  

**Program / Semester:** BSDS — Fall 2026  

**Team:** Zeeshan Jamal (60761), Arfa Khalid (61265)  

**Supervisor:** Dr. Jamal ud Din, HOD (BSDS, BSAI)

---

## Overall mapping statement

This FYP is mapped primarily as a **Complex Computing Problem** and a **Complex Computing Activity** under Seoul Accord Section D (Graduate Attributes) definitions of range of problem solving and range of computing activities.

The core task is not a routine CRUD application or a single textbook algorithm exercise. It requires formulating abstract models for heterogeneous biomedical knowledge-graph link prediction, grounding large-language-model explanations in retrieved literature (RAG), and coupling ranked hypotheses with sandboxed molecular docking—while managing conflicting goals of novelty, evidence faithfulness, computational cost, and safety framing. No single standard procedure fully specifies this end-to-end research pipeline; solutions must be designed, justified, and experimentally evaluated.

**Important constraint (aligned with the proposal):** the system produces **pre-clinical computational hypotheses**, not clinical diagnoses or proven therapies. Consequence mappings below therefore emphasize research-use and misuse-risk management, not claimed patient-level clinical outcomes.

For each characteristic below, the project is mapped to **exactly one** level: **Complex**, **Broadly-defined**, or **Well-defined**.

---

# D.4 Common Range and Contextual Definitions Associated with the Graduate Attributes

## D.4.1 Range of Problem Solving

**Instruction (from template):** Describe in a few sentences how your FYP maps to a well-defined, broadly-defined, or complex computing problem. For each characteristic, map to a **single** type only.

### Summary paragraph (D.4.1)

Our FYP maps overall to a **complex computing problem**. Predicting missing drug–disease associations on PrimeKG, explaining them with PubMed-grounded RAG, and screening top candidates with AutoDock Vina has **no single obvious solution**. It demands conceptual modelling (heterogeneous graphs, link-prediction objectives, retrieval constraints), deep computing and biomedical-domain knowledge, and resolution of conflicting requirements (coverage vs noise, fluency vs hallucination, docking completeness vs runtime, usefulness vs dual-use/safety). The integrated closed loop sits largely outside routine professional software practice, comprises many interdependent sub-problems, and begins with requirements that are only partially known at the outset (what counts as a defensible hypothesis, which disease focus, enrichment thresholds, docking fallbacks). Stakeholder diversity and societal consequences are assessed carefully and mapped below without over-claiming clinical impact.

---

### Mapping table — D.4.1 Range of Problem Solving


| # | Characteristic | Mapped level | Definition chosen (from Seoul Accord / template) | Mapping to this FYP project |
| - | -------------- | ------------ | ------------------------------------------------ | --------------------------- |
| 1 | Range of conflicting requirements | **Complex** | Involves wide-ranging or conflicting technical, computing, and other issues | The pipeline must simultaneously optimize **ranking quality**, **explanation faithfulness** (anti-hallucination), **docking feasibility**, **API/compute cost**, **graph freshness vs enrichment noise**, and **safety / dual-use caution**. Improving one factor often worsens another (e.g., enriching the KG with more literature triples can add useful edges but also false relations; docking more candidates improves coverage but exceeds time/resource budgets; unconstrained LLM text is fluent but unsafe). These are wide-ranging, conflicting technical and domain issues—not a few minor trade-offs. |
| 2 | Depth of analysis required | **Complex** | Has no obvious solution, and requires conceptual thinking and innovative analysis to formulate suitable abstract models | There is no obvious off-the-shelf “correct” architecture. We must formulate abstract models for: (i) drug–disease **link prediction** on a heterogeneous KG; (ii) **entity linking** from user text to PrimeKG IDs; (iii) **RAG** as a grounded explanation layer; (iv) docking as a **computational triage** model (not clinical proof). Evaluation itself requires analytical design (leakage-controlled splits, AUROC/AUPRC/MRR/Hits@K, RAG ablations, docking success/failure analysis). |
| 3 | Depth of knowledge required | **Complex** | A solution requires the use of in-depth computing or domain knowledge and an analytical approach that is based on well-founded principles | Implementation and defense require in-depth knowledge of graph neural networks / relational learning, information retrieval and RAG, biomedical identifiers (DrugBank/MONDO/UniProt/PDB), molecular docking principles (AutoDock Vina scoring as in-silico approximation), and experimental methodology. Domain knowledge of drug repurposing and literature-based discovery is needed to interpret results and avoid overstated claims. |
| 4 | Familiarity of issues | **Complex** | Involves infrequently-encountered issues | While individual pieces (Streamlit UI, API calls, basic ML training) are familiar to practitioners, the **integrated** problem—autonomous LBD-style hypothesis generation combining KG-GNN prediction, live PubMed RAG, sandboxed docking, and safety-flagged dossiers—is infrequently encountered as a single computing problem in routine industry/academic practice, especially under FYP resource constraints and explicit anti-hallucination / dual-use constraints. |
| 5 | Level of problem | **Complex** | Is outside problems encompassed by standards and standard practice for professional computing | There is no complete ISO/IEEE “standard procedure” that specifies how to build and validate an end-to-end literature-assisted drug-repurposing hypothesis engine. Components may use known tools (PyTorch Geometric, NCBI E-utilities, Docker, Vina), but selecting architectures, leakage-safe evaluation, enrichment policy, and claim boundaries requires work **outside** cookbook professional practice. |
| 6 | Extent of stakeholder involvement and level of conflicting requirements | **Broadly-defined** | Involves several groups of stakeholders with differing and occasionally conflicting needs | Stakeholders include: the student team, computing supervisor/panel, optional biology/pharmacy co-advisor, and intended research users (computational / biomedical analysts). Needs differ (academic rigor vs demo polish vs biological plausibility vs usability) and occasionally conflict, but the set is not as wide-ranging as a multi-industry clinical deployment with patients, regulators, and payers. Mapping is therefore **broadly-defined**, not overstated as maximally diverse. |
| 7 | Consequences | **Broadly-defined** | Has consequences that are important locally, but may extend to a broader context | Locally, the work affects FYP assessment, research-training practice, and how users prioritize follow-up reading. More broadly, if shared, dossiers could influence academic research directions. We **do not** claim patient-level clinical consequences; outputs are labelled as hypotheses. Still, incorrect biological claims or unsafe dual-use framing would matter beyond a toy demo—hence broadly-defined (important locally, may extend), with safety/ADME/dual-use flags as mitigation. |
| 8 | Interdependence | **Complex** | Is a high-level problem possibly including many component parts or sub-problems | The project is a high-level closed loop composed of interdependent sub-problems: KG preprocessing & splits, GNN training, candidate filtering/path extraction, PubMed retrieval, LLM explanation, structure resolution, docking, safety review, and report/UI generation. Errors in entity linking or enrichment cascade into prediction, explanation, and docking quality. |
| 9 | Requirement identification | **Complex** | Identification of a requirement or the cause of a problem is ill defined or unknown | At proposal time, several requirements are ill-defined rather than selectable from a fixed menu: what disease focus yields a defensible demo; what enrichment confidence threshold is acceptable; how to treat missing PDB structures; how to measure “explanation faithfulness”; how aggressive safety filtering should be without hiding useful hypotheses. Clarifying these is part of the research/engineering work. |


**D.4.1 result:** **7 / 9** characteristics mapped to **Complex**; **2 / 9** (stakeholders; consequences) mapped to **Broadly-defined**; **0** to Well-defined. Overall classification: **Complex Computing Problem**.

---

## D.4.2 Range of Computing Activities

**Instruction (from template):** Describe in a few sentences how your FYP maps to a well-defined, broadly-defined, or complex computing activity. Map each characteristic to your project (single level only).

### Summary paragraph (D.4.2)

Our FYP is a **complex computing activity**. It uses diverse resources (people, GPUs/compute, curated KGs, literature APIs, structural biology databases, containers, and LLMs), requires resolving significant interactions among technical and contextual issues (graph snapshot vs live evidence; model score vs citation grounding; docking failures; safety vs utility), and applies computing/domain principles creatively in a novel integrated pipeline. Familiarity extends beyond routine prior coursework: success depends on principles-based design and evaluation, not only following a fixed operating procedure.

---

### Mapping table — D.4.2 Range of Computing Activities


| # | Characteristic | Mapped level | Definition chosen (from Seoul Accord / template) | Mapping to this FYP project |
| - | -------------- | ------------ | ------------------------------------------------ | --------------------------- |
| 1 | Range of resources (people, money, equipment, materials, information, and technologies) | **Complex** | Involves the use of diverse resources | Resources span: team members with divided module ownership; supervisor (and recommended domain co-advisor); compute/GPU for GNN training; PrimeKG data; NCBI PubMed/PMC APIs; UniProt/PDB/PubChem structural data; Docker + AutoDock Vina; embedding/LLM services; Git-based collaboration and experimental logs. This is a diverse resource mix across people, information, and technologies. |
| 2 | Level of interactions | **Complex** | Requires resolution of significant problems arising from interactions among wide-ranging or conflicting technical, computing, contextual, or other issues | Significant interaction problems include: (a) static KG predictions vs need for fresh literature evidence; (b) GNN ranking vs RAG disagreement; (c) docking prep failures interacting with path extraction; (d) API rate limits interacting with retrieval depth; (e) safety/dual-use filters interacting with scientific usefulness; (f) enrichment noise interacting with model metrics. Resolving these interactions is central to the activity, not incidental. |
| 3 | Innovation | **Complex** | Involves creative use of knowledge of computing or domain principles in novel ways | Innovation is the **closed-loop composition**: GNN hypothesis generation + PMID-grounded RAG explanation + sandboxed docking triage + safety-flagged dossier—on a PrimeKG backbone with optional capped literature enrichment. This is not merely reusing one existing product; it creatively combines graph-learning, IR/NLP, and computational chemistry principles for literature-assisted repurposing hypothesis prioritization. |
| 4 | Consequences to society and the environment | **Broadly-defined** | Has consequences that are most important locally, but may extend more widely | Locally important for academic research tooling and SDG-aligned learning (Goal 3 health research support; Goal 9 innovation). Wider extension is possible if the methodology is reused by other student/research groups. Clinical-care consequences are intentionally out of scope; societal risk is managed via hypothesis labelling and safety/dual-use checks. |
| 5 | Familiarity | **Complex** | Can extend beyond previous experiences by applying principles-based approaches | Undergraduate coursework covers programming, databases, and introductory ML/web concepts, but not the full principles stack of heterogeneous GNN link prediction, biomedical RAG evaluation, and automated docking orchestration. The activity extends beyond prior experience and must be approached via principles-based design, experimentation, and failure analysis. |


**D.4.2 result:** **4 / 5** characteristics mapped to **Complex**; **1 / 5** (consequences to society/environment) mapped to **Broadly-defined**; **0** to Well-defined. Overall classification: **Complex Computing Activity**.

---

## Consolidated judgement (for panel)

| Dimension | Overall mapping | Rationale in one line |
| --------- | --------------- | --------------------- |
| D.4.1 Range of Problem Solving | **Complex Computing Problem** | Multi-objective, model-heavy, non-standard, highly interdependent research/engineering problem with ill-defined requirements at the start |
| D.4.2 Range of Computing Activities | **Complex Computing Activity** | Diverse resources, significant cross-layer interactions, innovative integration, principles beyond prior routine experience |

Where **Broadly-defined** is used (stakeholders; consequences), the choice is deliberate and consistent with the proposal’s claim boundary: this is a research-hypothesis system, not a clinical product with maximal multi-stakeholder regulatory scope.

---

## Reference

- Section D — Graduate Attributes, Seoul Accord Documents:  
  https://www.seoulaccord.org/document.php?id=79  
- Project source alignment: *Template03 Project Proposal & Plan* for this FYP (PrimeKG + GNN + RAG + AutoDock Vina closed-loop scope).

---

*End of Complex Computing Problem Characteristics Mapping Sheet (Template-04 aligned draft v1.0)*
