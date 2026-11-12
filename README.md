<div align="center">

# 💊 Medication Recommender Systems

**From Prescription Imitation to Controllable Medication Recommendation:<br>A Survey and Taxonomy**

Linyu Li<sup>1</sup> · Zhi Jin<sup>1,✉</sup> · Yuanpeng He<sup>1</sup> · Haoran Duan<sup>2</sup> · Dongming Jin<sup>1</sup><br>Jiandong Li<sup>1</sup> · Jia Li<sup>2</sup> · Jin Zhang<sup>3</sup> · Gadeng Luosang<sup>4</sup> · Tashi Nyima<sup>4</sup> · Jiannong Cao<sup>5</sup>

<sup>1</sup>Peking University · <sup>2</sup>Wuhan University · <sup>3</sup>University of Electronic Science and Technology of China<br><sup>4</sup>Tibet University · <sup>5</sup>The Hong Kong Polytechnic University · <sup>✉</sup>Corresponding author

[![Papers](https://img.shields.io/badge/Papers-111-2563eb)](#paper-catalog)
[![Code](https://img.shields.io/badge/Author_repositories-30-0f766e)](#code)
[![Coverage](https://img.shields.io/badge/Coverage-2026--10--24-64748b)](#scope)

**[Papers](#paper-catalog) · [Code](#code) · [Figures](#overview) · [Datasets](#datasets) · [Benchmarks](#benchmarks)**

</div>

A companion collection of papers, code, datasets, and benchmarks for our survey on medication recommendation. The core catalog contains **111 methods and systems**; additional sections provide related reading and resources.

<a id="contents"></a>
## Contents

- **Overview:** [Research evolution](#evolution) · [Recommendation pipeline](#task) · [Taxonomy](#taxonomy)
- **Papers:** [By year](#paper-catalog) · [Where to start](#reading-paths) · [Code](#code) · [Language-model methods](#llm-roles)
- **Resources:** [Datasets](#datasets) · [Drug knowledge](#knowledge) · [Benchmarks](#benchmarks) · [Reported results](#reported-results)
- **More:** [Specialty tasks](#adjacent) · [Open challenges](#future) · [Related surveys](#related-surveys) · [Contributing](#contributing)

<a id="scope"></a>
<a id="overview"></a>
## Survey overview

Medication recommendation uses patient records and drug knowledge to suggest medications suited to an individual's clinical context. Our survey follows the field from learning recorded prescribing patterns toward recommendations that can respond to clinical constraints and preferences.

**Literature through:** 24 October 2026 · **Collection updated:** 12 November 2026

<a id="evolution"></a>
### Research evolution

[![Evolution of medication recommendation research](assets/readme/evolution.png)](assets/readme/evolution.png)

*Figure 1. Research evolution and representative methods. The medical-model inset provides context and is outside the 111-entry catalog. Click any figure to enlarge.*

<a id="task"></a>
### Recommendation pipeline

Patient records and drug knowledge support medication prediction, with different approaches to representing patient history, incorporating knowledge, and producing recommendations.

[![Medication recommendation pipeline](assets/readme/pipeline.png)](assets/readme/pipeline.png)

*Figure 2. A typical medication recommendation pipeline, from EHR preprocessing and drug knowledge to model outputs.*

<a id="taxonomy"></a>
### Taxonomy

We organize methods by **patient representation**, **drug representation**, and **output mechanism**. Safety objectives, inference-time safety controls, and confidence estimation are considered alongside these dimensions.

[![Taxonomy of medication recommendation methods](assets/readme/taxonomy.png)](assets/readme/taxonomy.png)

*Figure 3. The survey taxonomy, with representative methods for each category.*

<a id="reading-paths"></a>
## Where to start

For structured models, start with [LEAP](#model-leap) → [GAMENet](#model-gamenet) → [SafeDrug](#model-safedrug) → [COGNet](#model-cognet) → [MoleRec](#model-molerec). For LLM-based approaches, see [LAMO](#model-lamo), [FLAME](#model-flame), and [GiantMed](#model-giantmed). For constraints and confidence, see [RxGuard](#model-rxguard) and [ARC](#model-arc).

<details>
<summary><strong>Browse by research topic</strong></summary>

| Topic | Start here | Further reading |
|---|---|---|
| Set construction | [LEAP](#model-leap), [COGNet](#model-cognet) | [CompNet](#model-compnet), [DPG](#model-dpg), [SSPNet](#model-sspnet) |
| Patient history | [GAMENet](#model-gamenet), [VITA](#model-vita) | [DAPSNet](#model-dapsnet), [LAMRec](#model-lamrec), [HypeMed](#model-hypemed) |
| Molecular representations | [SafeDrug](#model-safedrug), [MoleRec](#model-molerec) | [CRec](#model-crec), [SubRec](#model-subrec), [MGRec](#model-mgrec) |
| Knowledge graphs and ontologies | [G-BERT](#model-g-bert), [DGCL](#model-dgcl) | [SMR](#model-smr), [OntoMedRec](#model-ontomedrec), [KEHGCN](#model-kehgcn) |
| Rare conditions and short histories | [RAREMed](#model-raremed), [SHAPE](#model-shape) | [DrugDoctor](#model-drugdoctor), [RPNet](#model-rpnet), [MetaDrug](#model-metadrug) |
| Missing data and noisy labels | [MedGCN](#model-medgcn), [IMDR](#model-imdr) | [KDGN](#model-kdgn), [KRAM](#model-kram), [SCALE](#model-scale) |
| Medication changes | [MICRON](#model-micron), [ARCI](#model-arci) | [R-GEAN](#model-r-gean) |
| LLMs | [LAMO](#model-lamo), [FLAME](#model-flame) | [GiantMed](#model-giantmed), [RASPER](#model-rasper), [DCSENet](#model-dcsenet) |
| Retrieval | [TreatRAG](#model-treatrag), [HI-DR](#model-hi-dr) | [ARMED](#model-armed), [PACE-RAG](#model-pace-rag), [RES-MR](#model-res-mr) |
| Constraints and referral | [DRMP](#model-drmp), [DrugRec](#model-drugrec) | [ARC](#model-arc), [RxGuard](#model-rxguard), [SafeRx-Agent](#model-saferx-agent) |
| Fairness, privacy, and transfer | [IFMR](#model-ifmr), [TEMPT](#model-tempt) | [RaceMED](#model-racemed), [DrugGuard](#model-drugguard), [FedMed](#model-fedmed) |

</details>

<a id="paper-catalog"></a>
## Paper list · 111 methods and systems

[2026 · 33](#papers-2026) · [2025 · 26](#papers-2025) · [2024 · 18](#papers-2024) · [2023 · 10](#papers-2023) · [2022 · 9](#papers-2022) · [1975–2021 · 15](#papers-early)

Paper titles link to the cited publications or preprints. Years follow the versions used in the survey; online-publication and proceedings dates may differ. **Code** links to confirmed author repositories; **—** means no confirmed implementation is linked.

<a id="papers-2026"></a>
### 2026 · 33 entries

| Method and paper | Venue | Code |
|---|---|---|
| <a id="model-armed"></a>**ARMED**<br>[ARMED: Adaptive Retrieval-Augmented Medication Recommendation](https://arxiv.org/abs/2610.16440v1) | arXiv | — |
| <a id="model-bh3-medrec"></a>**BH3-MedRec**<br>[BH³-MedRec: Bilateral Hierarchical Heterogeneous Hypergraph Convolution Network for Medication Recommendation](https://doi.org/10.1145/3779446) | TIST | — |
| <a id="model-dcsenet"></a>**DCSENet**<br>[Dual-Channel Semantic-Enhanced Combinatorial Medication Recommendation via Knowledge Distillation](https://doi.org/10.24963/ijcai.2026/772) | IJCAI | — |
| <a id="model-drugguard"></a>**DrugGuard**<br>[Towards privacy-preserving drug recommendation via attribute unlearning](https://doi.org/10.1016/j.patcog.2026.114321) | Pattern Recognit. | — |
| <a id="model-fedmed"></a>**FedMed**<br>[FedMed: Federated Learning-Based Personalized and Safe Medication Recommendation](https://doi.org/10.1145/3770855.3818934) | KDD | — |
| <a id="model-finemed"></a>**FineMed**<br>[Medication mapping and diagnosis enhancement for fine-grained medication recommendation](https://doi.org/10.1016/j.ins.2026.123930) | Inf. Sci. | — |
| <a id="model-genrxr"></a>**GenRxR**<br>[Improving Rare Medication Recommendation with Counterfactual Data Augmentation and Large Language Models](https://doi.org/10.1145/3773078.3831753) | RecSys | — |
| <a id="model-giantmed"></a>**GiantMed**<br>[Awaken the Giant: Activating LLMs via Deep Model Guidance for Boundary-aware Medication Recommendation](https://doi.org/10.1145/3770854.3780297) | KDD | [Code](https://github.com/lvhangkenn/GiantMed) |
| <a id="model-grain"></a>**GRAIN**<br>[GRAIN: Molecules Are Not the Right Granularity -- Active-Ingredient Modeling for Safe Medication Recommendation](https://arxiv.org/abs/2608.00098v1) | arXiv | — |
| <a id="model-hadrec"></a>**HADRec**<br>[HADRec: A Hierarchy-Aware Drug Recommendation Framework by Fusing Molecular Knowledge and Electronic Health Record](https://arxiv.org/abs/2610.00984) | arXiv | — |
| <a id="model-hem-med"></a>**HEM-Med**<br>[HEM-Med: A Hierarchical Agentic Memory Framework for Safe Multi-Center Medication Recommendation](https://arxiv.org/abs/2610.20191v1) | arXiv | — |
| <a id="model-hhgcn-drugrec"></a>**HHGCN-DrugRec**<br>[HHGCN-DrugRec: Hierarchical HyperGraph Convolution Network for Drug Combination Recommendation](https://link.springer.com/chapter/10.1007/978-981-95-4155-3_14) | DASFAA | — |
| <a id="model-hier"></a>**HIER**<br>[Self-supervised Hierarchical Representation for Medication Recommendation](https://doi.org/10.1007/978-981-95-4155-3_9) | DASFAA | — |
| <a id="model-hypemed"></a>**HypeMed**<br>[HypeMed: Enhancing Medication Recommendations with Hypergraph-Based Patient Relationships](https://doi.org/10.1145/3803851) | TOIS | [Code](https://github.com/xansar/HypeMed) |
| <a id="model-katmed"></a>**KATMed**<br>[KATMed: a knowledge-augmented transformer model for contraindication-aware medication recommendation in comorbidities](https://doi.org/10.1016/j.jbi.2026.104991) | JBI | — |
| <a id="model-kehgcn"></a>**KEHGCN**<br>[Knowledge-Enhanced Explainable Hypergraph Convolution Network for Medication Recommendation](https://doi.org/10.1609/aaai.v40i19.38681) | AAAI | — |
| <a id="model-kram"></a>**KRAM**<br>[KRAM: Knowledge-driven robust training against label noise for medication recommendation](https://doi.org/10.1016/j.eswa.2026.131330) | ESWA | — |
| <a id="model-medicare"></a>**MediCARE**<br>[MediCARE: Medical Collaborative Agents REasoning over Interpretable Heterogeneous Graphs](https://doi.org/10.1016/j.artmed.2026.103444) | AIIM | — |
| <a id="model-medirec"></a>**MediRec**<br>[MediRec: Enhancing Chinese Medication Recommendation with Explainable Clinical Reasoning](https://arxiv.org/abs/2510.21084v3) | arXiv | — |
| <a id="model-metadrug"></a>**MetaDrug**<br>[User-Adaptive Meta-Learning for Cold-Start Medication Recommendation with Uncertainty Filtering](https://doi.org/10.1109/icde65706.2026.00298) | ICDE | — |
| <a id="model-mgrec"></a>**MGRec**<br>[MGRec: Structure-Grounded Medication Recommendation via Condition-Aware Molecular Representation Learning](https://doi.org/10.24963/ijcai.2026/289) | IJCAI | — |
| <a id="model-msam"></a>**MSAM**<br>[Learning Collective Medication Effects via Multi-level Abstraction for Medication Recommendation](https://doi.org/10.48550/arXiv.2601.19259) | arXiv | — |
| <a id="model-pace-rag"></a>**PACE-RAG**<br>[PACE-RAG: Patient-Aware Contextual and Evidence-Constrained RAG for Clinical Drug Recommendation](https://arxiv.org/abs/2603.17356v3) | arXiv | [Code](https://github.com/cheo0y/PACE-RAG) |
| <a id="model-r-gean"></a>**R-GEAN**<br>[R-GEAN: Regimen-Guided Edit Action Network for Within-Admission Medication Change Prediction](https://doi.org/10.48550/arXiv.2609.22959) | arXiv | — |
| <a id="model-racemed"></a>**RaceMED**<br>[RaceMED: A Race-Aware Approach to Accurate and Fair Medication Recommendation](https://doi.org/10.1145/3770855.3818065) | KDD | — |
| <a id="model-rasper"></a>**RASPER**<br>[RASPER: Reward-Aligned Summarization of Clinical Notes for EHR Outcome Prediction](https://arxiv.org/abs/2610.02979v1) | arXiv | — |
| <a id="model-res-mr"></a>**RES-MR**<br>[RES-MR: Risk-Aware Reasoning for Explainable and Safe Medication Recommendation](https://doi.org/10.1145/3805712.3809604) | SIGIR | [Code](https://github.com/wangcong2001/RES-MR) |
| <a id="model-rpnet"></a>**RPNet**<br>[Relation-aware pre-trained network with hierarchical aggregation mechanism for cold-start drug recommendation](https://doi.org/10.1016/j.neunet.2026.108618) | Neural Netw. | — |
| <a id="model-rxguard"></a>**RxGuard**<br>[RxGuard: Knowledge-Guided Safety Guardrails for Medication Recommendation](https://doi.org/10.1145/3770855.3818849) | KDD | — |
| <a id="model-saferx-agent"></a>**SafeRx-Agent**<br>[SafeRx-Agent: A Knowledge-Grounded Multi-Agent Framework for Safe and Explainable Medication Recommendation](https://doi.org/10.48550/arXiv.2605.29146) | arXiv | — |
| <a id="model-scale"></a>**SCALE**<br>[SCALE: Sharpness-Aware Correction for Addressing Long-Tail Effects in Combinatorial Medication Recommendation](https://doi.org/10.1145/3770855.3818852) | KDD | — |
| <a id="model-scamed"></a>**SCAMed**<br>[Structural complementarity-aware molecular representation learning for medication recommendation](https://www.sciencedirect.com/science/article/pii/S095219762601122X) | Eng. Appl. AI | — |
| <a id="model-sdrec"></a>**SDRec**<br>[SDRec: Synergistic Drug Recommendation Network Based on Medical Domain Knowledge](https://www.sciopen.com/article/10.26599/TST.2025.9010078) | Tsinghua ST | — |

[↑ Paper index](#paper-catalog) · [↑ Contents](#contents)


<a id="papers-2025"></a>
### 2025 · 26 entries

| Method and paper | Venue | Code |
|---|---|---|
| <a id="model-arc"></a>**ARC**<br>[Advancing Confidence Calibration and Quantification in Medication Recommendation](https://doi.org/10.1145/3690624.3709232) | KDD | — |
| <a id="model-armr"></a>**ARMR**<br>[ARMR: Adaptively Responsive Network for Medication Recommendation](https://doi.org/10.24963/ijcai.2025/871) | IJCAI | — |
| <a id="model-bimorec"></a>**BiMoRec**<br>[Medication recommendation via dual molecular modalities and multi-step enhancement](https://www.sciencedirect.com/science/article/pii/S0957417425007857) | ESWA | [Code](https://github.com/guangyunms/BiMoRec) |
| <a id="model-cafemed"></a>**CafeMed**<br>[CafeMed: Causal Attention Fusion Enhanced Medication Recommendation](https://doi.org/10.1109/BIBM66473.2025.11356494) | BIBM | [Code](https://github.com/rkl71/CafeMed) |
| <a id="model-cidgmed"></a>**CIDGMed**<br>[CIDGMed: Causal inference-driven medication recommendation with enhanced dual-granularity learning](https://doi.org/10.1016/j.knosys.2024.112685) | KBS | [Code](https://github.com/lixiang-222/CIDGMed) |
| <a id="model-crec"></a>**CRec**<br>[Revisiting drug recommendation from a causal perspective](https://doi.org/10.1109/JBHI.2024.3471637) | JBHI | — |
| <a id="model-dpid"></a>**DPID**<br>[Towards robust drug recommendation based on dual perspective encoder and iterative denoising mechanism](https://www.sciencedirect.com/science/article/pii/S095741742501406X) | ESWA | — |
| <a id="model-excerf"></a>**EXCERF**<br>[Beyond EHRs: External Clinical knowledge and cohort Features for medication recommendation](https://doi.org/10.1016/j.knosys.2025.113763) | KBS | — |
| <a id="model-flame"></a>**FLAME**<br>[Fine-grained List-wise Alignment for Generative Medication Recommendation](https://proceedings.neurips.cc/paper_files/paper/2025/file/44a1f7e0a1fe7867f586b10739a0c26a-Paper-Conference.pdf) | NeurIPS | [Code](https://github.com/cxfann/Flame) |
| <a id="model-gap"></a>**GAP**<br>[GAP: Graph-Assisted Prompts for Dialogue-based Medication Recommendation](https://doi.org/10.48550/arXiv.2505.12888) | arXiv | — |
| <a id="model-gpsrec"></a>**GPSRec**<br>[Improving the Safety of Medication Recommendation via Graph Augmented Patient Similarity Network](https://doi.org/10.1145/3746252.3761071) | CIKM | — |
| <a id="model-hi-dr"></a>**HI-DR**<br>[HI-DR: Exploiting Health Status-Aware Attention and an EHR Graph+ for Effective Medication Recommendation](https://doi.org/10.1609/aaai.v39i11.33301) | AAAI | — |
| <a id="model-imdr"></a>**IMDR**<br>[Incomplete Multi-View Drug Recommendation via Multi-Level Representation Learning and Curriculum Learning](https://doi.org/10.1145/3711896.3737236) | KDD | — |
| <a id="model-lamo"></a>**LAMO**<br>[Fine-grained Alignment of Large Language Models for General Medication Recommendation without Overprescription](https://arxiv.org/abs/2503.03687v2) | arXiv | [Code](https://github.com/zzhUSTC2016/LAMO) |
| <a id="model-mambaguard"></a>**MambaGuard**<br>[MambaGuard-MOO: Multi-Objective Safe Drug Recommendation with Contrastive Learning](https://doi.org/10.1109/BIGDATA66926.2025.11402123) | IEEE BigData | — |
| <a id="model-medalign"></a>**MedAlign**<br>[MedAlign: Enhancing Combinatorial Medication Recommendation with Multi-modality Alignment](https://doi.org/10.1145/3746027.3755265) | ACM MM | [Code](https://github.com/lvhangkenn/MedAlign) |
| <a id="model-medcoact"></a>**MedCoAct**<br>[MedCoAct: Confidence-Aware Multi-Agent Collaboration for Complete Clinical Decision](https://doi.org/10.1109/BIBM66473.2025.11356820) | BIBM | — |
| <a id="model-mkmed"></a>**MKMed**<br>[Combating the Bucket Effect: Multi-Knowledge Alignment for Medication Recommendation](https://arxiv.org/abs/2504.18096v1) | arXiv | — |
| <a id="model-mr-dtr"></a>**MR-DTR**<br>[Time-aware Medication Recommendation via Intervention of Dynamic Treatment Regimes](https://doi.org/10.1145/3696410.3714533) | WWW | [Code](https://github.com/liyifo/MR-DTR) |
| <a id="model-sdrbt"></a>**SDRBT**<br>[Patient deep spatio-temporal encoding and medication substructure mapping for safe medication recommendation](https://doi.org/10.1016/j.jbi.2025.104785) | JBI | [Code](https://github.com/yhqfighting/SDRBT) |
| <a id="model-secgi"></a>**SECGI**<br>[SECGI: A Medication Recommendation Model Combining LLM-Based Semantic Enrichment and Causal Graph Inference](https://doi.org/10.1109/BIBM66473.2025.11356251) | BIBM | — |
| <a id="model-sspnet"></a>**SSPNet**<br>[SSPNet: Leveraging Robust Medication Recommendation with History and Knowledge](https://doi.org/10.24963/ijcai.2025/1052) | IJCAI | [Code](https://github.com/ResearchGroupHdZhang/SSPNet) |
| <a id="model-subrec"></a>**SubRec**<br>[Integrating Drug Substructures and Longitudinal Electronic Health Records for Personalized Drug Recommendation](http://papers.nips.cc/paper_files/paper/2025/hash/5b0c0b2c2efdd736a53688ebfdc3bcdb-Abstract-Conference.html) | NeurIPS | — |
| <a id="model-tempt"></a>**TEMPT**<br>[A Contrastive Pretrain Model with Prompt Tuning for Multi-center Medication Recommendation](https://doi.org/10.1145/3706631) | TOIS | — |
| <a id="model-tracedr"></a>**TraceDR**<br>[Traceable Drug Recommendation over Medical Knowledge Graphs](https://doi.org/10.48550/arXiv.2510.27274) | arXiv | — |
| <a id="model-treatrag"></a>**TreatRAG**<br>[TreatRAG: A Framework for Personalized Treatment Recommendation](https://doi.org/10.1145/3705328.3748022) | RecSys | — |

[↑ Paper index](#paper-catalog) · [↑ Contents](#contents)


<a id="papers-2024"></a>
### 2024 · 18 entries

| Method and paper | Venue | Code |
|---|---|---|
| <a id="model-acdnet"></a>**ACDNet**<br>[ACDNet: Attention-guided Collaborative Decision Network for effective medication recommendation](https://doi.org/10.1016/j.jbi.2023.104570) | JBI | — |
| <a id="model-arci"></a>**ARCI**<br>[Contrastive Learning on Medical Intents for Sequential Prescription Recommendation](https://doi.org/10.1145/3627673.3679836) | CIKM | — |
| <a id="model-causalmed"></a>**CausalMed**<br>[CausalMed: Causality-Based Personalized Medication Recommendation Centered on Patient Health State](https://doi.org/10.1145/3627673.3679542) | CIKM | — |
| <a id="model-chimedrec"></a>**ChiMedRec**<br>[Chiral Molecular Graph Encoder for Medication Recommendation](https://doi.org/10.1109/BIBM62325.2024.10822474) | BIBM | — |
| <a id="model-dkinet"></a>**DKINet**<br>[DKINet: Medication recommendation via domain knowledge informed deep learning](https://doi.org/10.1109/BIBM62325.2024.10821909) | BIBM | [Code](https://github.com/sherry6247/DKINet) |
| <a id="model-dmrnet"></a>**DMRNet**<br>[DMRNet: Effective Network for Accurate Discharge Medication Recommendation](https://doi.org/10.1109/ICDE60146.2024.00262) | ICDE | — |
| <a id="model-drechgr"></a>**DRecHGR**<br>[Enhancing Drug Recommendations via Heterogeneous Graph Representation Learning in EHR Networks](https://doi.org/10.1109/TKDE.2023.3329025) | TKDE | — |
| <a id="model-drugdoctor"></a>**DrugDoctor**<br>[DrugDoctor: enhancing drug recommendation in cold-start scenario via visit-level representation learning and training](https://doi.org/10.1093/bib/bbae464) | Brief. Bioinf. | [Code](https://github.com/kybinn/DrugDoctor) |
| <a id="model-lamrec"></a>**LAMRec**<br>[LAMRec: Label-aware Multi-view Drug Recommendation](https://doi.org/10.1145/3627673.3679656) | CIKM | — |
| <a id="model-leader"></a>**LEADER**<br>[Large Language Model Distilling Medication Recommendation Model](https://doi.org/10.48550/arXiv.2402.02803) | arXiv | — |
| <a id="model-mgrn"></a>**MGRN**<br>[MGRN: toward robust drug recommendation via multi-view gating retrieval network](https://doi.org/10.1093/bioinformatics/btae572) | Bioinformatics | — |
| <a id="model-mk-gnn"></a>**MK-GNN**<br>[Medical-Knowledge-Based Graph Neural Network for Medication Combination Prediction](https://doi.org/10.1109/TNNLS.2023.3266490) | TNNLS | — |
| <a id="model-nla-mmr"></a>**NLA-MMR**<br>[Natural Language-Assisted Multi-modal Medication Recommendation](https://doi.org/10.1145/3627673.3679529) | CIKM | — |
| <a id="model-ontomedrec"></a>**OntoMedRec**<br>[OntoMedRec: Logically-pretrained model-agnostic ontology encoders for medication recommendation](https://doi.org/10.1007/s11280-024-01268-1) | World Wide Web | — |
| <a id="model-promise"></a>**PROMISE**<br>[PROMISE: A pre-trained knowledge-infused multimodal representation learning framework for medication recommendation](https://doi.org/10.1016/j.ipm.2024.103758) | IPM | — |
| <a id="model-raremed"></a>**RAREMed**<br>[Leave no patient behind: Enhancing medication recommendation for rare disease patients](https://doi.org/10.1145/3626772.3657785) | SIGIR | [Code](https://github.com/zzhUSTC2016/RAREMed) |
| <a id="model-stratmed"></a>**StratMed**<br>[StratMed: Relevance stratification between biomedical entities for sparsity on medication recommendation](https://doi.org/10.1016/j.knosys.2023.111239) | KBS | [Code](https://github.com/lixiang-222/StratMed) |
| <a id="model-vita"></a>**VITA**<br>[VITA: Carefully Chosen and Weighted Less Is Better in Medication Recommendation](https://doi.org/10.1609/aaai.v38i8.28704) | AAAI | [Code](https://github.com/jhheo0123/VITA) |

[↑ Paper index](#paper-catalog) · [↑ Contents](#contents)


<a id="papers-2023"></a>
### 2023 · 10 entries

| Method and paper | Venue | Code |
|---|---|---|
| <a id="model-carmen"></a>**Carmen**<br>[Context-Aware Safe Medication Recommendations with Molecular Graph and DDI Graph Embedding](https://doi.org/10.1609/aaai.v37i6.25861) | AAAI | — |
| <a id="model-cehmr"></a>**CEHMR**<br>[CEHMR: Curriculum learning enhanced hierarchical multi-label classification for medication recommendation](https://doi.org/10.1016/j.artmed.2023.102613) | AIIM | [Code](https://github.com/siomkos2020/CEHMR) |
| <a id="model-dapsnet"></a>**DAPSNet**<br>[Dual Attention and Patient Similarity Network for drug recommendation](https://doi.org/10.1093/bioinformatics/btad003) | Bioinformatics | — |
| <a id="model-dgcl"></a>**DGCL**<br>[DGCL: distance-wise and graph contrastive learning for medication recommendation](https://doi.org/10.1016/j.jbi.2023.104301) | JBI | [Code](https://github.com/Benjamin-cell/DGCL) |
| <a id="model-dpg"></a>**DPG**<br>[Interaction-aware Drug Package Recommendation via Policy Gradient](https://doi.org/10.1145/3511020) | TOIS | — |
| <a id="model-medrec"></a>**MedRec**<br>[Knowledge-enhanced attributed multi-task learning for medicine recommendation](https://doi.org/10.1145/3527662) | TOIS | — |
| <a id="model-molerec"></a>**MoleRec**<br>[MoleRec: Combinatorial Drug Recommendation with Substructure-Aware Molecular Representation Learning](https://doi.org/10.1145/3543507.3583872) | WWW | [Code](https://github.com/yangnianzu0515/MoleRec) |
| <a id="model-ontopath"></a>**OntoPath**<br>[Ontology-aware Prescription Recommendation in Treatment Pathways Using Multi-evidence Healthcare Data](https://doi.org/10.1145/3579994) | TOIS | — |
| <a id="model-refine"></a>**REFINE**<br>[REFINE: A Fine-Grained Medication Recommendation System Using Deep Learning and Personalized Drug Interaction Modeling](https://proceedings.neurips.cc/paper_files/paper/2023/file/4b7439a4ab0b8e4bcb4e2412c6a10a58-Paper-Conference.pdf) | NeurIPS | — |
| <a id="model-shape"></a>**SHAPE**<br>[SHAPE: A sample-adaptive hierarchical prediction network for medication recommendation](https://doi.org/10.1109/JBHI.2023.3320139) | JBHI | [Code](https://github.com/sherry6247/SHAPE) |

[↑ Paper index](#paper-catalog) · [↑ Contents](#contents)


<a id="papers-2022"></a>
### 2022 · 9 entries

| Method and paper | Venue | Code |
|---|---|---|
| <a id="model-4sdrug"></a>**4SDrug**<br>[4SDrug: Symptom-based Set-to-set Small and Safe Drug Recommendation](https://doi.org/10.1145/3534678.3539089) | KDD | [Code](https://github.com/Melinda315/4SDrug) |
| <a id="model-cognet"></a>**COGNet**<br>[Conditional Generation Net for Medication Recommendation](https://doi.org/10.1145/3485447.3511936) | WWW | [Code](https://github.com/BarryRun/COGNet) |
| <a id="model-drmp"></a>**DRMP**<br>[A drug recommendation model based on message propagation and DDI gating mechanism](https://doi.org/10.1109/JBHI.2022.3153342) | JBHI | — |
| <a id="model-drugrec"></a>**DrugRec**<br>[Debiased, Longitudinal and Coordinated Drug Recommendation through Multi-Visit Clinic Records](https://proceedings.neurips.cc/paper_files/paper/2022/file/b295b3a940706f431076c86b78907757-Paper-Conference.pdf) | NeurIPS | [Code](https://github.com/ssshddd/DrugRec) |
| <a id="model-ifmr"></a>**IFMR**<br>[Perceived individual fairness with a molecular representation for medicine recommendations](https://doi.org/10.1016/j.knosys.2022.108755) | KBS | — |
| <a id="model-kdgn"></a>**KDGN**<br>[Knowledge-enhanced dual graph neural network for robust medicine recommendation](https://doi.org/10.1109/BIBM55620.2022.9995543) | BIBM | — |
| <a id="model-medgcn"></a>**MedGCN**<br>[MedGCN: Medication recommendation and lab test imputation via graph convolutional networks](https://doi.org/10.1016/j.jbi.2022.104000) | JBI | — |
| <a id="model-pccnet"></a>**PCCNet**<br>[Patient condition change network for safe medication recommendation](https://doi.org/10.1109/BIBM55620.2022.9995523) | BIBM | — |
| <a id="model-tahdnet"></a>**TAHDNet**<br>[TAHDNet: Time-aware hierarchical dependency network for medication recommendation](https://doi.org/10.1016/j.jbi.2022.104069) | JBI | — |

[↑ Paper index](#paper-catalog) · [↑ Contents](#contents)


<a id="papers-early"></a>
### 1975–2021 · 15 entries

| Method and paper | Venue | Code |
|---|---|---|
| <a id="model-merits"></a>**MERITS**<br>[MERITS: Medication recommendation for chronic disease with irregular time-series](https://doi.org/10.1109/ICDM51629.2021.00192) | 2021 · ICDM | — |
| <a id="model-mesin"></a>**MeSIN**<br>[MeSIN: Multilevel selective and interactive network for medication recommendation](https://doi.org/10.1016/j.knosys.2021.107534) | 2021 · KBS | — |
| <a id="model-micron"></a>**MICRON**<br>[Change Matters: Medication Change Prediction with Recurrent Residual Networks](https://doi.org/10.24963/ijcai.2021/513) | 2021 · IJCAI | [Code](https://github.com/ycq091044/MICRON) |
| <a id="model-premier"></a>**PREMIER**<br>[Personalizing medication recommendation with a graph-based approach](https://doi.org/10.1145/3488668) | 2021 · TOIS | — |
| <a id="model-safedrug"></a>**SafeDrug**<br>[SafeDrug: Dual Molecular Graph Encoders for Recommending Effective and Safe Drug Combinations](https://doi.org/10.24963/ijcai.2021/514) | 2021 · IJCAI | [Code](https://github.com/ycq091044/SafeDrug) |
| <a id="model-sarmr"></a>**SARMR**<br>[Self-Supervised Adversarial Distribution Regularization for Medication Recommendation](https://doi.org/10.24963/ijcai.2021/431) | 2021 · IJCAI | — |
| <a id="model-smr"></a>**SMR**<br>[SMR: Medical Knowledge Graph Embedding for Safe Medicine Recommendation](https://doi.org/10.1016/j.bdr.2020.100174) | 2021 · Big Data Res. | — |
| <a id="model-gate"></a>**GATE**<br>[GATE: Graph-attention augmented temporal neural network for medication recommendation](https://doi.org/10.1109/ACCESS.2020.3007835) | 2020 · IEEE Access | — |
| <a id="model-compnet"></a>**CompNet**<br>[Order-free Medicine Combination Prediction with Graph Convolutional Reinforcement Learning](https://doi.org/10.1145/3357384.3357965) | 2019 · CIKM | — |
| <a id="model-g-bert"></a>**G-BERT**<br>[Pre-training of Graph Augmented Transformers for Medication Recommendation](https://doi.org/10.24963/ijcai.2019/825) | 2019 · IJCAI | [Code](https://github.com/jshang123/G-Bert) |
| <a id="model-gamenet"></a>**GAMENet**<br>[GAMENet: Graph Augmented Memory Networks for Recommending Medication Combination](https://ojs.aaai.org/index.php/AAAI/article/view/3905) | 2019 · AAAI | [Code](https://github.com/sjy1203/GAMENet) |
| <a id="model-dmnc"></a>**DMNC**<br>[Dual memory neural computer for asynchronous two-view sequential learning](https://doi.org/10.1145/3219819.3219981) | 2018 · KDD | [Code](https://github.com/thaihungle/DMNC) |
| <a id="model-srl-rnn"></a>**SRL-RNN**<br>[Supervised Reinforcement Learning with Recurrent Neural Network for Dynamic Treatment Recommendation](https://doi.org/10.1145/3219819.3219961) | 2018 · KDD | — |
| <a id="model-leap"></a>**LEAP**<br>[LEAP: Learning to Prescribe Effective and Safe Treatment Combinations for Multimorbidity](https://doi.org/10.1145/3097983.3098109) | 2017 · KDD | — |
| <a id="model-mycin"></a>**MYCIN**<br>[A model of inexact reasoning in medicine](https://doi.org/10.1016/0025-5564(75)90047-4) | 1975 · Math. Biosci. | — |

[↑ Paper index](#paper-catalog) · [↑ Contents](#contents)

<a id="code"></a>
## Code

The catalog links **30 author repositories**. Common starting points include [GAMENet](https://github.com/sjy1203/GAMENet), [SafeDrug](https://github.com/ycq091044/SafeDrug), [MoleRec](https://github.com/yangnianzu0515/MoleRec), [LAMO](https://github.com/zzhUSTC2016/LAMO), [FLAME](https://github.com/cxfann/Flame), and [GiantMed](https://github.com/lvhangkenn/GiantMed).

- **SafeDrug:** use the author's `archived` branch when reproducing the paper's results.
- **DrugDoctor:** consult the author's [Figure 4 correction](https://github.com/kybinn/DrugDoctor) for its cold-start analysis.

Links have been checked, but the implementations have not been rerun for this collection.

<a id="llm-roles"></a>
## Language models in medication recommendation

Language models contribute representations, recommendations, training signals, and explanations. Text-representation methods include [NLA-MMR](#model-nla-mmr), [RASPER](#model-rasper), and [SECGI](#model-secgi); the table below highlights other roles. Contextual systems such as DrugGPT and AMIE are outside the core catalog.

| Role | Examples |
|---|---|
| Candidate decision | [LAMO](#model-lamo) |
| Candidate refinement | [GiantMed](#model-giantmed) |
| List construction and revision | [FLAME](#model-flame) |
| Discharge-medication generation | [MediRec](#model-medirec) |
| Distillation into a smaller model | [LEADER](#model-leader), [DCSENet](#model-dcsenet) |
| Training-data construction | [TraceDR](#model-tracedr), [GenRxR](#model-genrxr) |
| Offline knowledge / supervision | [KATMed](#model-katmed), [IMDR](#model-imdr) |
| Similar-case retrieval | [TreatRAG](#model-treatrag), [PACE-RAG](#model-pace-rag), [ARMED](#model-armed) |
| Graph-guided evidence | [GAP](#model-gap), [RES-MR](#model-res-mr) |
| Medication knowledge assistant | [DrugGPT](https://doi.org/10.1038/s41551-025-01471-z), outside the catalog |
| Explanation | [MediCARE](#model-medicare) |
| Agent coordination and verification | [SafeRx-Agent](#model-saferx-agent) |
| Longitudinal management | [AMIE management](https://www.nature.com/articles/s41586-026-10764-5) |

<a id="datasets"></a>
## Datasets

| Dataset | Overview |
|---|---|
| [MIMIC-III v1.4](https://physionet.org/content/mimiciii/1.4/) | Hospital records widely used for medication-set recommendation. |
| [MIMIC-IV v2.2](https://physionet.org/content/mimiciv/2.2/) | Hospital and intensive-care records used in more recent studies. |
| [eICU v2.0](https://physionet.org/content/eicu-crd/2.0/) | Multicenter intensive-care records. |
| [CHIP 2025 cohort used by MediRec](https://arxiv.org/abs/2510.21084v3) | Chinese clinical records for discharge-medication recommendation. |
| [Synthea](https://synthetichealth.github.io/synthea/) | Synthetic patient histories for development and pipeline testing. |

Dataset versions follow the survey. MIMIC and eICU require the relevant credentialing and data-use agreement; study-specific preprocessing produces different cohorts and medication vocabularies.

<a id="knowledge"></a>
## Drug knowledge and terminology

| Resource | What it provides |
|---|---|
| [TWOSIDES](https://tatonettilab.org/resources/tatonetti-stm.html) | Drug-pair associations derived from adverse-event reports |
| [DrugBank](https://go.drugbank.com/) | Curated drug properties, interaction information, and chemical structures |
| [RxNorm](https://www.nlm.nih.gov/research/umls/rxnorm/overview.html) | Normalized drug concepts at ingredient, strength, dose-form, and clinical-drug granularities |
| [ATC/DDD Index](https://atcddd.fhi.no/atc_ddd_index/) | Anatomical, therapeutic, pharmacological, and chemical classification |
| [UMLS](https://www.nlm.nih.gov/research/umls/index.html) | Biomedical concepts and relations across terminologies |
| [PrimeKG](https://zitniklab.hms.harvard.edu/projects/PrimeKG/) | Biomedical relations connecting diseases, drugs, and other biological entities |
| [OMOP Common Data Model](https://www.ohdsi.org/data-standardization/) | Shared structure and standardized vocabularies for observational data |
| [HL7 FHIR](https://www.hl7.org/fhir/overview.html) | Resources and interfaces for health-information exchange |

<a id="benchmarks"></a>
## Medication-focused benchmarks

These resources cover medication knowledge, prescription quality, and clinical risk. Links point to the versions discussed in the survey, including preprints.

| Benchmark and paper | Focus |
|---|---|
| [Chinese medication benchmark](https://aclanthology.org/2025.acl-short.91/) | Medication knowledge and reasoning in Chinese. |
| [RxEval](https://arxiv.org/abs/2605.14543) | Patient-specific medication, dose, and route choices. |
| [RxSafeBench](https://arxiv.org/abs/2511.04328) | Contraindications and drug interactions. [Data](https://github.com/CAS-SIAT-XinHai/RxSafeBench) |
| [Rx-LLM](https://www.medrxiv.org/content/10.64898/2025.12.01.25341004v2) | Medication-order fields and prescribing errors. |
| [PsiBench](https://www.medrxiv.org/content/10.64898/2026.06.05.26354271v1) | Medication-safety scenarios and alerts. |
| [MedMatch](https://www.medrxiv.org/content/10.64898/2026.01.13.26343949v1) | Complete medication-order expression. |
| [RxQA, introduced with AMIE](https://www.nature.com/articles/s41586-026-10764-5) | Medication reasoning based on formulary information. |
| [NOHARM](https://arxiv.org/abs/2512.01241v4) | Harmful actions and important omissions in clinical management. |

<a id="adjacent"></a>
## Specialty and adjacent tasks

Additional reading beyond the 111-entry core catalog.

| Year | Paper | Venue | Connection to medication recommendation |
|---|---|---|---|
| 2026 | [Large Language Model–Based Clinical Decision Support for Antibiotic Selection and Dose Recommendation in Hospitalized Patients With Pneumonia: Multicenter Retrospective Study](https://doi.org/10.2196/98207) | JMIR Med. Inform. | Pneumonia: antibiotic selection and dose recommendation |
| 2024 | [An antimicrobial drug recommender system using MALDI-TOF MS and dual-branch neural networks](https://doi.org/10.7554/eLife.93242) | eLife | Antimicrobial recommendation from MALDI-TOF mass spectrometry |
| 2024 | [PresRecST: a novel herbal prescription recommendation algorithm for real-world patients with integration of syndrome differentiation and treatment planning](https://doi.org/10.1093/jamia/ocae066) | JAMIA | PresRecST: syndrome differentiation and herbal treatment planning |
| 2023 | [Advancing Precision Medicine: Treatment Regimen Recommendations via Siamese Neural Networks](https://doi.org/10.1109/BIBM58861.2023.10385518) | BIBM | Treatment regimen retrieval using Siamese networks |
| 2022 | [Drug recommendation system for diabetes using a collaborative filtering and clustering approach: development and performance evaluation](https://doi.org/10.2196/37233) | J. Med. Internet Res. | Diabetes medication recommendation |
| 2022 | [Transformer-and generative adversarial network–based inpatient traditional Chinese medicine prescription recommendation: Development study](https://doi.org/10.2196/35239) | JMIR Med. Inform. | TCM-Trans: inpatient herbal prescription recommendation |
| 2019 | [Learning and recommending treatments using electronic medical records](https://doi.org/10.1016/j.knosys.2019.05.031) | KBS | Treatment regimen learning and recommendation from EHRs |
| 2015 | [Reducing inappropriate polypharmacy: the process of deprescribing](https://doi.org/10.1001/jamainternmed.2015.0324) | JAMA Intern. Med. | Deprescribing and revision of existing therapy |

### Clinical evaluation and management

| Study and paper | Focus |
|---|---|
| [Pneumonia antibiotic support](https://doi.org/10.2196/98207) | Retrospective evaluation of antibiotic selection and dosing. |
| [Physician–RAG prescribing workflow](https://doi.org/10.1016/j.ijmedinf.2026.106598) | Collaboration between physicians and retrieval-augmented systems. |
| [AMIE management](https://www.nature.com/articles/s41586-026-10764-5) | Management planning across simulated clinical encounters. |
| [NHS primary-care medication review](https://arxiv.org/abs/2512.21127) | Medication-related issues and proposed interventions. |

<a id="evaluation"></a>
<a id="reported-results"></a>
## Reported results

The figure summarizes selected results from [COGNet](#model-cognet) and [FLAME](#model-flame). Compare methods within each study's protocol: the two studies use different inputs, medication vocabularies, and evaluation settings, so these results are not a unified leaderboard.

[![Reported results from the COGNet and FLAME studies](assets/readme/reported-results.png)](assets/readme/reported-results.png)

*Figure 4. Published results reproduced in the survey.*

Agreement with recorded prescriptions alone does not establish clinical safety or benefit. Evaluation should also consider interactions, omissions, prescription completeness, and generalization.

Reporting references: [MINIMAR](https://doi.org/10.1093/jamia/ocaa088) · [TRIPOD+AI](https://www.bmj.com/content/385/bmj-2023-078378) · [TRIPOD-LLM](https://www.nature.com/articles/s41591-024-03425-5) · [SPIRIT-AI](https://www.nature.com/articles/s41591-020-1037-7) · [DECIDE-AI](https://www.nature.com/articles/s41591-022-01772-9).

<a id="future"></a>
## Open challenges

- **Controllable recommendations:** respond to clinical constraints and preferences, with referral when evidence is insufficient.
- **Complete regimens:** move beyond drug names to dosing, administration, and medication changes.
- **Learning from outcomes:** connect recommendations to patient outcomes while addressing confounding.
- **Generalization and reliability:** improve transfer across institutions and populations, update knowledge, and evaluate clinical workflows.

<a id="general-recommendation"></a>
<details>
<summary><strong>Related ideas from general recommendation</strong></summary>

These papers provide methodological context beyond the core catalog.

| Study and paper | Connection |
|---|---|
| **MODT4R** · TKDE 2025<br>[Beyond Accuracy: Decision Transformers for Reward-Driven Multi-Objective Recommendations](https://doi.org/10.1109/TKDE.2025.3582506) | Multi-objective recommendation |
| **CoLLM** · TKDE 2025<br>[CoLLM: Integrating Collaborative Embeddings Into Large Language Models for Recommendation](https://doi.org/10.1109/TKDE.2025.3540912) | LLMs and collaborative representations |
| **HCR** · TKDE 2024<br>[Mitigating Hidden Confounding Effects for Causal Recommendation](https://doi.org/10.1109/TKDE.2024.3378482) | Causal recommendation |
| **LCKD-SR** · TKDE 2026<br>[Passing on Wisdom: LLM-Driven Cascaded Knowledge Distillation for Sequential Recommendation](https://doi.org/10.1109/TKDE.2026.3675423) | Knowledge distillation for sequential recommendation |
| **FENCR** · TOIS 2025<br>[Feature-Enhanced Neural Collaborative Reasoning for Explainable Recommendation](https://doi.org/10.1145/3690381) | Explainable recommendation |

</details>

<a id="related-surveys"></a>
## Related surveys

| Year | Survey | Venue | Focus |
|---|---|---|---|
| 2026 | [A systematic survey of digital medication recommendation systems](https://doi.org/10.1016/j.bspc.2026.110882) | Biomed. Signal Process. Control | Digital medication recommendation systems |
| 2026 | [A Survey on Medical Large Language Models: Technology, Application, Trustworthiness, and Future Directions](https://doi.org/10.1109/TKDE.2026.3709941) | TKDE | Medical LLM technology, applications, and trustworthiness |
| 2025 | [A scoping review on generative AI and large language models in mitigating medication related harm](https://doi.org/10.1038/s41746-025-01565-7) | npj Digit. Med. | Generative AI and LLMs for medication-related harm |
| 2024 | [Recommender Systems in the Era of Large Language Models (LLMs)](https://doi.org/10.1109/TKDE.2024.3392335) | TKDE | LLM-based recommender systems in general domains |
| 2023 | [Deep Learning for Medication Recommendation: A Systematic Survey](https://doi.org/10.1162/dint_a_00197) | Data Intell. | Deep learning for medication recommendation |
| 2021 | [Recommender systems in the healthcare domain: state-of-the-art and research issues](https://link.springer.com/article/10.1007/s10844-020-00633-6) | J. Intell. Inf. Syst. | Recommender systems across healthcare tasks |

<a id="contributing"></a>
## Contributing

Papers, author-code links, and corrections are welcome through [issues](https://github.com/2391134843/Medication-Recommendation-Survey/issues) and [pull requests](https://github.com/2391134843/Medication-Recommendation-Survey/pulls). Please include the paper link and a brief description of the proposed addition or correction.

## Acknowledgments

Inspired by [LLMSurvey](https://github.com/RUCAIBox/LLMSurvey) and [Awesome Knowledge Graph Reasoning](https://github.com/LIANGKE23/Awesome-Knowledge-Graph-Reasoning). Thanks to the authors and maintainers who share their papers, code, and data.

[↑ Contents](#contents)
