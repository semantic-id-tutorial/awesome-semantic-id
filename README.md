# Awesome Semantic IDs for Recommender Systems

[![Paper](https://img.shields.io/badge/CIKM'26-10.1145%2F3799682.3839274-red)](https://doi.org/10.1145/3799682.3839274)
[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated reading list on **Semantic IDs for Recommender Systems** — item identity encoded as discrete, content-aware token sequences (typically via RQ-VAE / RQ-KMeans style vector quantization) rather than arbitrary integer IDs. This list accompanies the CIKM '26 tutorial *["IDs That Mean Something: A Hands-On Tutorial on Semantic IDs for Recommender Systems"](https://doi.org/10.1145/3799682.3839274)*.

We trace the field from raw IDs to semantic IDs, and organize papers published **since [TIGER](https://proceedings.neurips.cc/paper_files/paper/2023/hash/20dcab0f14046a5c6b02b61da9f13229-Abstract-Conference.html) (NeurIPS '23)** — the paper that established generating semantic IDs as a recommendation paradigm — across construction, generative and discriminative usage, multimodal/collaborative fusion, cold-start, cross-domain transfer, and cross-task unification. Where a paper has both an official venue version and an arXiv preprint, we link the official version.

Reading paths follow the camera-ready tutorial (Sections 2.3–2.7); papers are listed once under their main contribution, with cross-references for overlapping topics. Bibliographic refresh: 2026-10-19.

We continuously maintain this list to foster future endeavors. Contributions welcome — see [How to Contribute](#how-to-contribute).

## Citation

If you find this list useful, please cite the tutorial it accompanies:

```bibtex
@inproceedings{li2026ids,
  title     = {IDs That Mean Something: A Hands-On Tutorial on Semantic IDs for Recommender Systems},
  author    = {Li, Roger Zhe and Salah, Aghiles and Sertkan, Mete and Jin, Changhong and Niu, Yingjie and Dong, Ruihai and Smyth, Barry},
  booktitle = {Proceedings of the 35th ACM International Conference on Information and Knowledge Management (CIKM '26)},
  year      = {2026},
  publisher = {ACM},
  address   = {New York, NY, USA},
  doi       = {10.1145/3799682.3839274}
}
```

## Table of Contents
- [Background: From Raw IDs to Semantic IDs](#background-from-raw-ids-to-semantic-ids)
- [Semantic ID Construction \& Tokenization](#semantic-id-construction--tokenization)
- [Generative Recommendation with Semantic IDs](#generative-recommendation-with-semantic-ids)
- [Semantic IDs in Discriminative Ranking \& Retrieval](#semantic-ids-in-discriminative-ranking--retrieval)
- [Multimodality in Semantic ID Construction](#multimodality-in-semantic-id-construction)
- [Collaborative Signals in Semantic ID Construction](#collaborative-signals-in-semantic-id-construction)
- [Cold-Start Recommendation with Semantic IDs](#cold-start-recommendation-with-semantic-ids)
- [Cross-Domain Transfer with Semantic IDs](#cross-domain-transfer-with-semantic-ids)
- [Cross-Task Unification \& Semantic Planning](#cross-task-unification--semantic-planning)
- [Related Surveys \& Tutorials](#related-surveys--tutorials)
- [Related Awesome Lists](#related-awesome-lists)
- [How to Contribute](#how-to-contribute)

## Background: From Raw IDs to Semantic IDs

For two decades, item identity in industrial recommenders was anchored in arbitrary integer IDs — enabling exact lookup and memorization, but no identity-level generalization to new or semantically-similar items. Auxiliary/multimodal content was later folded in as a *side input* to mitigate cold-start, without changing item identity itself. Semantic IDs shift this boundary: item identity itself becomes a structured, content-aware object.

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *Wide & Deep* | [Wide & Deep Learning for Recommender Systems](https://doi.org/10.1145/2988450.2988454) | DLRS@RecSys'16 | / |
| *Multimedia RS Survey* | [Recommender Systems Leveraging Multimedia Content](https://doi.org/10.1145/3407190) | ACM CSUR'21 | / |
| *Multi-Modal RS Hands-On* | [Multi-Modal Recommender Systems: Hands-On Exploration](https://doi.org/10.1145/3460231.3473324) | RecSys'21 | [GitHub](https://github.com/PreferredAI/cornac) |

## Semantic ID Construction & Tokenization

How to *build* semantic IDs — quantization/tokenization architectures that turn item content into discrete token sequences.

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *VQ-Rec* | [Learning Vector-Quantized Item Representation for Transferable Sequential Recommenders](https://doi.org/10.1145/3543507.3583434) | WWW'23 | [GitHub](https://github.com/RUCAIBox/VQ-Rec) |
| *GenRet* | [Learning to Tokenize for Generative Retrieval](https://proceedings.neurips.cc/paper_files/paper/2023/hash/91228b942a4528cdae031c1b68b127e8-Abstract-Conference.html) | NeurIPS'23 | [GitHub](https://github.com/sunnweiwei/GenRet) |
| *SEATER* | [Generative Retrieval with Semantic Tree-Structured Item Identifiers via Contrastive Learning](https://arxiv.org/abs/2309.13375) | arXiv'23 | [GitHub](https://github.com/Ethan00Si/SEATER_Generative_Retrieval) |
| *LMIndexer* | [Language Models as Semantic Indexers](https://openreview.net/forum?id=hJEMTDOwKx) | ICML'24 | [GitHub](https://github.com/PeterGriffinJin/LMIndexer) |
| *ActionPiece* | [ActionPiece: Contextually Tokenizing Action Sequences for Generative Recommendation](https://openreview.net/forum?id=h2oNQOzbc5) | ICML'25 | [GitHub](https://github.com/google-deepmind/action_piece) |
| *TokenRec* | [TokenRec: Learning to Tokenize ID for LLM-based Generative Recommendation](https://ieeexplore.ieee.org/document/11129873) | TKDE'25 | [GitHub](https://github.com/Quhaoh233/TokenRec) |
| *UTGRec* | [Universal Item Tokenization for Transferable Generative Recommendation](https://arxiv.org/abs/2504.04405) | arXiv'25 | [GitHub](https://github.com/RUCAIBox/UTGRec) |
| *HiD-VAE* | [HiD-VAE: Interpretable Generative Recommendation via Hierarchical and Disentangled Semantic IDs](https://arxiv.org/abs/2508.04618) | arXiv'25 | / |
| *PCR-CA* | [PCR-CA: Parallel Codebook Representations with Contrastive Alignment for Multiple-Category App Recommendation](https://arxiv.org/abs/2508.18166) | arXiv'25 | / |
| *COSETTE* | [Closing the Performance Gap in Generative Recommenders with Collaborative Tokenization and Efficient Modeling](https://arxiv.org/abs/2508.14910) | arXiv'25 | / |
| *PSRQ* | [Progressive Semantic Residual Quantization for Multimodal-Joint Interest Modeling in Music Recommendation](https://doi.org/10.1145/3746252.3761579) | CIKM'25 | / |
| *FORGE* | [FORGE: Forming Semantic Identifiers for Generative Retrieval in Industrial Datasets](https://arxiv.org/abs/2509.20904) | arXiv'25 | [GitHub](https://github.com/selous123/al_sid) |
| *Purely Semantic Indexing* | [Purely Semantic Indexing for LLM-based Generative Recommendation and Retrieval](https://arxiv.org/abs/2509.16446) | arXiv'25 | / |
| *Semantics Meet Signals* | [Semantics Meet Signals: Dual Codebook Representation Learning for Generative Recommendation](https://arxiv.org/abs/2511.20673) | arXiv'25 | / |
| *H2W* | [The Best of the Two Worlds: Harmonizing Semantic and Hash IDs for Sequential Recommendation](https://arxiv.org/abs/2512.10388) | arXiv'25 | / |
| *MERGE* | [MERGE: Next-Generation Item Indexing Paradigm for Large-Scale Streaming Recommendation](https://arxiv.org/abs/2601.20199) | arXiv'26 | / |
| *SemanticConvergence* | [Semantic Convergence: Harmonizing Recommender Systems via Two-Stage Alignment and Behavioral Semantic Tokenization](https://ojs.aaai.org/index.php/AAAI/article/view/33311) | AAAI'25 | / |
| *R3-VAE* | [R3-VAE: Reference Vector-Guided Rating Residual Quantization VAE for Generative Recommendation](https://arxiv.org/abs/2604.11440) | arXiv'26 | / |
| *PrefixMem* | [LLMs Need Encoders for Semantic IDs Too](https://arxiv.org/abs/2606.00324) | arXiv'26 | / |
| *Rethinking Tokenizer* | [Rethinking Generative Recommender Tokenizer: RecSys-Native Encoding and Semantic Quantization Beyond LLMs](https://arxiv.org/abs/2602.02338) | arXiv'26 | / |
| *UniSID* | [End-to-End Semantic ID Generation for Generative Advertisement Recommendation](https://arxiv.org/abs/2602.10445) | arXiv'26 | / |
| *TAAC-SID* | [Tencent Advertising Algorithm Challenge 2025: All-Modality Generative Recommendation](https://arxiv.org/abs/2604.04976) | arXiv'26 | [GitHub](https://github.com/TencentAdvertisingAlgorithmCompetition/baseline_2025) |
| *DIGER* | [Differentiable Semantic ID for Generative Recommendation](https://doi.org/10.1145/3805712.3809641) | SIGIR'26 | [GitHub](https://github.com/junchen-fu/DIGER) |
| *Variable-Length SIDs* | [Variable-Length Semantic IDs for Recommender Systems](https://arxiv.org/abs/2602.16375) | arXiv'26 | / |
| *CCE / ZCR* | [Faithful Evaluation of Semantic-ID Tokenizers for Generative Recommendation](https://arxiv.org/abs/2605.25330) | CIKM'26 (accepted) | [GitHub](https://github.com/Nishikata97/CollisionGenRec) |

## Generative Recommendation with Semantic IDs

Semantic IDs as the backbone of **generative retrieval/recommendation**, starting from TIGER. This section includes autoregressive generation and alternative decoding approaches.

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *TIGER* | [Recommender Systems with Generative Retrieval](https://proceedings.neurips.cc/paper_files/paper/2023/hash/20dcab0f14046a5c6b02b61da9f13229-Abstract-Conference.html) | NeurIPS'23 (seminal) | [GitHub](https://github.com/EdoardoBotta/RQ-VAE-Recommender) |
| *LC-Rec* | [Adapting Large Language Models by Integrating Collaborative Semantics for Recommendation](https://doi.org/10.1109/ICDE60146.2024.00118) | ICDE'24 | [GitHub](https://github.com/RUCAIBox/LC-Rec) |
| *ColaRec* | [Content-Based Collaborative Generation for Recommender Systems](https://doi.org/10.1145/3627673.3679692) | CIKM'24 | [GitHub](https://github.com/Junewang0614/ColaRec) |
| *MBGen* | [Multi-Behavior Generative Recommendation](https://doi.org/10.1145/3627673.3679730) | CIKM'24 | [GitHub](https://github.com/anananan116/MBGen) |
| *EAGER* | [EAGER: Two-Stream Generative Recommender with Behavior-Semantic Collaboration](https://doi.org/10.1145/3637528.3671775) | KDD'24 | [GitHub](https://github.com/yewzz/EAGER) |
| *MMGRec* | [MMGRec: Multimodal Generative Recommendation with Transformer Model](https://arxiv.org/abs/2404.16555) | arXiv'24 | [GitHub](https://github.com/hanliu95/MMGRec) |
| *MVIGER* | [MVIGER: Multi-View Variational Integration of Complementary Knowledge for Generative Recommender](https://arxiv.org/abs/2408.08686) | arXiv'24 | / |
| *EAGER-LLM* | [EAGER-LLM: Enhancing Large Language Models as Recommenders through Exogenous Behavior-Semantic Integration](https://doi.org/10.1145/3696410.3714933) | WWW'25 | / |
| *SETRec* | [SETRec: Order-Agnostic Identifier for Large Language Model-based Generative Recommendation](https://doi.org/10.1145/3726302.3730053) | SIGIR'25 | [GitHub](https://github.com/Linxyhaha/SETRec) |
| *RPG* | [Generating Long Semantic IDs in Parallel for Recommendation](https://doi.org/10.1145/3711896.3736979) | KDD'25 | [GitHub](https://github.com/facebookresearch/RPG_KDD2025) |
| *GNPR-SID* | [Generative Next POI Recommendation with Semantic ID](https://doi.org/10.1145/3711896.3736981) | KDD'25 | [GitHub](https://github.com/wds1996/GNPR-SID) |
| *EARN* | [EARN: Efficient Inference Acceleration for LLM-based Generative Recommendation by Register Tokens](https://doi.org/10.1145/3711896.3736919) | KDD'25 | [GitHub](https://github.com/transcend-0/EARN) |
| *AtSpeed* | [Efficient Inference for Large Language Model-based Generative Recommendation](https://openreview.net/forum?id=ACSNlt77hq) | ICLR'25 | [GitHub](https://github.com/Linxyhaha/AtSpeed) |
| *SpecGR* | [Inductive Generative Recommendation via Retrieval-based Speculation](https://ojs.aaai.org/index.php/AAAI/article/view/38486) | AAAI'26 | [GitHub](https://github.com/Jamesding000/SpecGR) |
| *LLaDA-Rec* | [LLaDA-Rec: Discrete Diffusion for Parallel Semantic ID Generation in Generative Recommendation](https://arxiv.org/abs/2511.06254) | arXiv'25 | [GitHub](https://github.com/TengShi-RUC/LLaDA-Rec) |
| *ContRec* | [Diffusion Generative Recommendation with Continuous Tokens](https://arxiv.org/abs/2504.12007) | arXiv'25 | [GitHub](https://github.com/Quhaoh233/ContRec) |
| *GRAM* | [GRAM: Generative Recommendation via Semantic-aware Multi-granular Late Fusion](https://aclanthology.org/2025.acl-long.1596/) | ACL'25 | [GitHub](https://github.com/skleee/GRAM) |
| *GRAM (retrieval)* | [Generative Retrieval and Alignment Model: A New Paradigm for E-commerce Retrieval](https://doi.org/10.1145/3701716.3715228) | WWW'25 (Companion) | / |
| *OneRec* | [OneRec: Unifying Retrieve and Rank with Generative Recommender and Iterative Preference Alignment](https://arxiv.org/abs/2502.18965) | arXiv'25 | [GitHub](https://github.com/Kuaishou-OneRec/OpenOneRec) |
| *OneRec (Tech Report)* | [OneRec Technical Report](https://arxiv.org/abs/2506.13695) | arXiv'25 | [GitHub](https://github.com/Kuaishou-OneRec/OpenOneRec) |
| *OneRec-V2* | [OneRec-V2 Technical Report](https://arxiv.org/abs/2508.20900) | arXiv'25 | [GitHub](https://github.com/Kuaishou-OneRec/OpenOneRec) |
| *COBRA* | [Sparse Meets Dense: Unified Generative Recommendations with Cascaded Sparse-Dense Representations](https://openreview.net/forum?id=zugMif2nm6) | NeurIPS'25 | / |
| *MTGR* | [MTGR: Industrial-Scale Generative Recommendation Framework in Meituan](https://doi.org/10.1145/3746252.3761565) | CIKM'25 | / |
| *GR4AD* | [Generative Recommendation for Large-Scale Advertising](https://arxiv.org/abs/2602.22732) | arXiv'26 | / |
| *TSGR* | [TSGR: Taobao Search Generative Retrieval](https://arxiv.org/abs/2607.18796) | arXiv'26 | / |
| *HiGR* | [HiGR: Industrial-Scale Hierarchical Generative Slate Recommendation Framework in Tencent](https://arxiv.org/abs/2512.24787) | arXiv'25 | / |
| *GLIDE* | [Deploying Semantic ID-based Generative Retrieval for Large-Scale Podcast Discovery at Spotify](https://arxiv.org/abs/2603.17540) | arXiv'26 | / |
| *Model-Scaling for SIDs* | [Understanding Generative Recommendation with Semantic IDs from a Model-scaling View](https://arxiv.org/abs/2509.25522) | arXiv'25 | / |
| *NEZHA* | [NEZHA: A Zero-sacrifice and Hyperspeed Decoding Architecture for Generative Recommendations](https://arxiv.org/abs/2511.18793) | arXiv'25 | / |
| *Align3GR* | [Align3GR: Unified Multi-Level Alignment for LLM-based Generative Recommendation](https://ojs.aaai.org/index.php/AAAI/article/view/38651) | AAAI'26 | / |
| *PROMISE* | [PROMISE: Process Reward Models Unlock Test-Time Scaling Laws in Generative Recommendations](https://arxiv.org/abs/2601.04674) | arXiv'26 | / |
| *Latte* | [Expressiveness Limits of Autoregressive Semantic ID Generation in Generative Recommendation](https://arxiv.org/abs/2605.06331) | arXiv'26 | [GitHub](https://github.com/hyp1231/Latte) |
| *DualGR* | [DualGR: Generative Retrieval with Long and Short-Term Interests Modeling](https://arxiv.org/abs/2511.12518) | WWW'26 (Best Short Paper) | / |
| *Text2Tracks* | [Text2Tracks: Prompt-based Music Recommendation via Generative Retrieval](https://arxiv.org/abs/2503.24193) | arXiv'25 | [GitHub](https://github.com/mayurbhangale/text2tracks) |
| *RedGR* | [RedGR: Unified Generative Retrieval for Recommendation in REDnote](https://doi.org/10.1145/3805712.3808417) | SIGIR'26 | / |

## Semantic IDs in Discriminative Ranking & Retrieval

Semantic IDs used as **structured input features** in traditional discriminative ranking, CTR prediction, and embedding-based retrieval pipelines (not autoregressive generation).

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *UIST* | [Discrete Semantic Tokenization for Deep CTR Prediction](https://doi.org/10.1145/3589335.3651558) | WWW'24 (Companion) | [GitHub](https://github.com/Jyonn/SemanticTokenizer) |
| *SIDE* | [SIDE: Semantic ID Embedding for Effective Learning from Sequences](https://doi.org/10.1007/978-3-032-16358-5_5) | AdKDD'25 | / |
| *USIRL* | [Unified Semantic and ID Representation Learning for Deep Recommenders](https://arxiv.org/abs/2502.16474) | arXiv'25 | / |
| *IDProxy* | [IDProxy: Cold-Start CTR Prediction for Ads and Recommendation at Xiaohongshu with Multimodal LLMs](https://arxiv.org/abs/2603.01590) | arXiv'26 | / |
| *RQ-GMM* | [RQ-GMM: Residual Quantized Gaussian Mixture Model for Multimodal Semantic Discretization in CTR Prediction](https://doi.org/10.1145/3805712.3809968) | SIGIR'26 | / |
| *PaletteID* | [PaletteID: Prototype-Composed Semantic Identifiers for Multimodal CTR Prediction](https://arxiv.org/abs/2607.29000) | arXiv'26 | / |
| *Dual-Purpose SIDs* | [Tokens are All You Need: Dual-purpose Semantic IDs for Achieving LLM-Level I/O Efficiency in Recommendation Systems](https://arxiv.org/abs/2607.24865) | arXiv'26 | / |
| *FedMM* | [FedMM: Federated Collaborative Signal Quantization for Multi-Market CTR Prediction](https://doi.org/10.1145/3805712.3809654) | SIGIR'26 | / |
| *SIREN* | [SIREN: Unified Multi-Granularity Semantic Interaction for Multi-Modal Lifelong User Interest Modeling](https://arxiv.org/abs/2605.25726) | arXiv'26 | / |
| *Snapchat SIDs* | [Semantic IDs for Recommender Systems at Snapchat: Use Cases, Technical Challenges, and Design Choices](https://doi.org/10.1145/3805712.3808405) | SIGIR'26 | / |
| *STORE* | [STORE: Semantic Tokenization, Orthogonal Rotation and Efficient Attention for Scaling Up Ranking Models](https://arxiv.org/abs/2511.18805) | arXiv'25 | / |
| *YouTube Semantic IDs* | [Better Generalization with Semantic IDs: A Case Study in Ranking for Recommendations](https://doi.org/10.1145/3640457.3688190) | RecSys'24 | / |
| *DAS* | [DAS: Dual-Aligned Semantic IDs Empowered Industrial Recommender System](https://doi.org/10.1145/3746252.3761529) | CIKM'25 | / |
| *Meta SID Stability* | [Enhancing Embedding Representation Stability in Recommendation Systems with Semantic ID](https://doi.org/10.1145/3705328.3748123) | RecSys'25 | / |
| *TRM* | [Farewell to Item IDs: Unlocking the Scaling Potential of Large Ranking Models via Semantic Tokens](https://arxiv.org/abs/2601.22694) | arXiv'26 | / |


## Multimodality in Semantic ID Construction

Papers centered on fusing multiple content modalities (text/image/audio/video) into semantic ID construction. Read along two axes: early fusion before quantization versus late fusion of modality-specific codes, and redundancy versus complementary cross-modal information. FusID and Multimodal Semantics are starting points; MME-SID and QARM appear under [Collaborative Signals](#collaborative-signals-in-semantic-id-construction).

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *MMQ* | [MMQ: Multimodal Mixture-of-Quantization Tokenization for Semantic ID Generation and User Behavioral Adaptation](https://doi.org/10.1145/3773966.3777923) | WSDM'26 | / |
| *Q-BERT4Rec* | [Q-BERT4Rec: Quantized Semantic-ID Representation Learning for Multimodal Recommendation](https://arxiv.org/abs/2512.02474) | arXiv'25 | / |
| *QARM V2* | [QARM V2: Quantitative Alignment Multi-Modal Recommendation for Reasoning User Sequence Modeling](https://arxiv.org/abs/2602.08559) | arXiv'26 | / |
| *DMESR* | [DMESR: Dual-view MLLM-based Enhancing Framework for Multimodal Sequential Recommendation](https://arxiv.org/abs/2602.13715) | arXiv'26 | / |
| *AdaSID* | [Beyond Static Collision Handling: Adaptive Semantic ID Learning for Multimodal Recommendation at Industrial Scale](https://arxiv.org/abs/2604.23522) | arXiv'26 | / |
| *Multimodal Semantics* | [Beyond Unimodal Perspectives: Generative Retrieval with Multimodal Semantics](https://doi.org/10.1145/3805712.3809844) | SIGIR'26 | / |
| *FusID* | [FusID: Modality-Fused Semantic IDs for Generative Music Recommendation](https://arxiv.org/abs/2601.08764) | arXiv'26 | / |


## Collaborative Signals in Semantic ID Construction

Papers specifically about injecting/aligning collaborative-filtering or behavioral signals into semantic ID construction — the tension between IDs that are semantically meaningful (from content) vs. recommendation-aware (from interactions). Includes joint/end-to-end tokenizer-recommender training, contrastive alignment to CF embeddings, semantic-collaborative disentanglement, and collision/staleness handling driven by interaction skew.

Reading paths following Section 2.5 of the tutorial:

- **Quantize collaborative embeddings:** TokenRec and MME-SID.
- **Fine-tune content representations before tokenization:** QARM and TRM (listed under Discriminative Ranking).
- **Train on collaborative pairs:** PLUM; LETTER and CoST provide related alignment objectives.
- **Optimize tokenizer and recommender jointly:** ETEGRec, DIGER (under Construction), and Bi-Level Tokenization.

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *LETTER* | [Learnable Item Tokenization for Generative Recommendation](https://doi.org/10.1145/3627673.3679569) | CIKM'24 | [GitHub](https://github.com/HonghuiBao2000/LETTER) |
| *CoST* | [CoST: Contrastive Quantization based Semantic Tokenization for Generative Recommendation](https://doi.org/10.1145/3640457.3688178) | RecSys'24 | / |
| *ETEGRec* | [Generative Recommender with End-to-End Learnable Item Tokenization](https://doi.org/10.1145/3726302.3729989) | SIGIR'25 | [GitHub](https://github.com/RUCAIBox/ETEGRec) |
| *CCFRec* | [Bridging Textual-Collaborative Gap through Semantic Codes for Sequential Recommendation](https://doi.org/10.1145/3711896.3736869) | KDD'25 | [GitHub](https://github.com/RUCAIBox/CCFRec) |
| *DiscRec* | [DiscRec: Disentangled Semantic-Collaborative Modeling for Generative Recommendation](https://arxiv.org/abs/2506.15576) | arXiv'25 | [GitHub](https://github.com/Ten-Mao/DiscRec) |
| *BBQRec* | [BBQRec: Behavior-Bind Quantization for Multi-Modal Sequential Recommendation](https://arxiv.org/abs/2504.06636) | arXiv'25 | / |
| *DQ-VAE* | [Representation Quantization for Collaborative Filtering Augmentation](https://arxiv.org/abs/2508.11194) | arXiv'25 | / |
| *ADC-SID* | [Taming the Long Tail: Denoising Collaborative Information for Robust Semantic ID Generation](https://arxiv.org/abs/2510.25622) | arXiv'25 | / |
| *CEMG* | [CEMG: Collaborative-Enhanced Multimodal Generative Recommendation](https://link.springer.com/chapter/10.1007/978-981-95-6950-2_36) | MMM'26 | / |
| *DECOR* | [Learning Decomposed Contextual Token Representations from Pretrained and Collaborative Signals for Generative Recommendation](https://doi.org/10.1145/3805712.3809578) | SIGIR'26 | [GitHub](https://github.com/yliuaa/DECOR) |
| *GateSID* | [GateSID: Adaptive Gating for Balancing Semantic and Collaborative Signals in Recommendation](https://arxiv.org/abs/2603.22916) | arXiv'26 | / |
| *SID Staleness* | [Mitigating Collaborative Semantic ID Staleness in Generative Retrieval](https://doi.org/10.1145/3805712.3809877) | SIGIR'26 | / |
| *UNGER* | [UNGER: Generative Recommendation with A Unified Code via Semantic and Collaborative Integration](https://arxiv.org/abs/2502.06269) | arXiv'25 | / |
| *SaviorRec* | [SaviorRec: Semantic-Behavior Alignment for Cold-Start Recommendation](https://arxiv.org/abs/2508.01375) | arXiv'25 | / |
| *Bi-Level Tokenization* | [Bi-Level Optimization for Generative Recommendation: Bridging Tokenization and Generation](https://doi.org/10.1145/3805712.3809632) | SIGIR'26 | / |
| *PRISM* | [PRISM: Purified Representation and Integrated Semantic Modeling for Generative Sequential Recommendation](https://arxiv.org/abs/2601.16556) | arXiv'26 | / |
| *QuaSID* | [Stop Treating Collisions Equally: Qualification-Aware Semantic ID Learning for Recommendation at Industrial Scale](https://arxiv.org/abs/2603.00632) | arXiv'26 | / |
| *Rethinking Sem-Collab* | [Rethinking Semantic Collaborative Integration: Why Alignment Is Not Enough](https://doi.org/10.1145/3805712.3808539) | SIGIR'26 | / |
| *QARM* | [QARM: Quantitative Alignment Multi-Modal Recommendation at Kuaishou](https://doi.org/10.1145/3746252.3761502) | CIKM'25 | / |
| *MME-SID* | [Empowering Large Language Model for Sequential Recommendation via Multimodal Embeddings and Semantic IDs](https://doi.org/10.1145/3746252.3761169) | CIKM'25 | [GitHub](https://github.com/Applied-Machine-Learning-Lab/MME-SID) |
| *PLUM* | [PLUM: Adapting Pre-trained Language Models for Industrial-scale Generative Recommendations](https://doi.org/10.1145/3774904.3792802) | WWW'26 | / |
| *SCRec* | [Addressing Cross-Stage Decoupling of Semantic and Collaborative Signals in Generative Recommendation](https://doi.org/10.1145/3773078.3831736) | RecSys'26 | / |


## Cold-Start Recommendation with Semantic IDs

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *MoToRec* | [MoToRec: Sparse-Regularized Multimodal Tokenization for Cold-Start Recommendation](https://doi.org/10.1609/aaai.v40i18.38558) | AAAI'26 | / |
| *ColdGenRec* | [Cold-Starts in Generative Recommendation: A Reproducibility Study](https://arxiv.org/abs/2603.29845) | SIGIR'26 | [GitHub](https://github.com/zhangzhen-research/ColdGenrec) |
| *GR Cold-Item Reachability* | [Can Generative Recommendation Reach Cold Items? A Temporal Perspective on Semantic-ID Generation](https://arxiv.org/abs/2607.21101) | arXiv'26 | [GitHub](https://github.com/Lucas-PJ/GRColdItemReachability) |
| *GTI* | [Grounded Token Initialization for New Vocabulary in LMs for Generative Recommendation](https://arxiv.org/abs/2604.02324) | arXiv'26 | / |

## Cross-Domain Transfer with Semantic IDs

Using the shared semantic structure of semantic IDs to transfer knowledge across recommendation domains/platforms without explicit source-target alignment.

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *Quantizing Intent* | [Quantizing Intent: Cross-Domain Semantic IDs from Organic Activity for Industrial Ranking](https://arxiv.org/abs/2606.01396) | arXiv'26 (LinkedIn) | / |
| *GenCDSR* | [Empowering Cross-Domain Sequential Recommendation with Hybrid Tokenization and Serial-Parallel Decoding](https://doi.org/10.1145/3773078.3831777) | RecSys'26 | [GitHub](https://github.com/Applied-Machine-Learning-Lab/RecSys2026_GenCDSR) |
| *MetaRec* | [Transferable Sequential Recommendation via Vector Quantized Meta Learning](https://ieeexplore.ieee.org/document/10825425/) | IEEE BigData'24 | / |
| *RecGPT* | [RecGPT: A Foundation Model for Sequential Recommendation](https://aclanthology.org/2025.emnlp-main.513/) | EMNLP'25 | [GitHub](https://github.com/HKUDS/RecGPT) |
| *RecBase* | [RecBase: Generative Foundation Model Pretraining for Zero-Shot Recommendation](https://aclanthology.org/2025.emnlp-main.786/) | EMNLP'25 | / |
| *GMC* | [Generative Multi-Target Cross-Domain Recommendation](https://arxiv.org/abs/2507.12871) | arXiv'25 | / |
| *GenCDR* | [From IDs to Semantics: A Generative Framework for Cross-Domain Recommendation with Adaptive Semantic Tokenization](https://ojs.aaai.org/index.php/AAAI/article/view/38508) | AAAI'26 | [GitHub](https://github.com/hupeiyu21/GenCDR) |


## Cross-Task Unification & Semantic Planning

Semantic IDs as a shared representation unifying recommendation with search/retrieval and other tasks, and early work on using semantic IDs for planning/reasoning about what the next exposure should accomplish.

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *SIDReasoner* | [Reasoning over Semantic IDs Enhances Generative Recommendation](https://doi.org/10.1145/3770855.3818122) | KDD'26 | [GitHub](https://github.com/HappyPointer/SIDReasoner) |
| *SIGMA* | [SIGMA: A Semantic-Grounded Instruction-Driven Generative Multi-Task Recommender at AliExpress](https://doi.org/10.1145/3805712.3808421) | SIGIR'26 (Industry) | / |
| *UniSearch* | [UniSearch: Rethinking Search System with a Unified Generative Architecture](https://arxiv.org/abs/2509.06887) | arXiv'25 | / |
| *Joint Search & Recommendation* | [Semantic IDs for Joint Generative Search and Recommendation](https://doi.org/10.1145/3705328.3759300) | RecSys'25 | / |
| *GenSAR* | [GenSAR: Unifying Balanced Search and Recommendation with Generative Retrieval](https://doi.org/10.1145/3705328.3748071) | RecSys'25 | / |


## Related Surveys & Tutorials

### Surveys

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *Item-ID Survey* | [A Survey of Item Identifiers in Generative Recommendation: Construction, Alignment, and Generation](https://doi.org/10.36227/techrxiv.176945895.52184668/v1) | TechRxiv'26 | [GitHub](https://github.com/HKBU-LAGAS/Awesome-Item-ID-Gen-RecSys) |
| *Practitioner's Handbook* | [Generative Recommendation with Semantic IDs: A Practitioner's Handbook](https://doi.org/10.1145/3746252.3761612) | CIKM'25 | / |
| *VQ4Rec Survey* | [Vector Quantization for Recommender Systems: A Review and Outlook](https://arxiv.org/abs/2405.03110) | arXiv'24 | [GitHub](https://github.com/Jyonn/VQ4Rec) |
| *Gen-Rec Data/Model/Tasks* | [A Survey on Generative Recommendation: Data, Model, and Tasks](https://arxiv.org/abs/2510.27157) | arXiv'25 | / |
| *Gen-RecSys* | [A Review of Modern Recommender Systems Using Generative Models (Gen-RecSys)](https://doi.org/10.1145/3637528.3671474) | KDD'24 | / |
| *Gen Search & Rec Survey* | [A Survey of Generative Search and Recommendation in the Era of Large Language Models](https://arxiv.org/abs/2404.16924) | arXiv'24 | / |
| *LLM4Rec Survey* | [A Survey on Large Language Models for Recommendation](https://arxiv.org/abs/2305.19860) | arXiv'23 | [GitHub](https://github.com/WLiK/LLM4Rec-Awesome-Papers) |
| *LLM4Rec TOIS Survey* | [How Can Recommender Systems Benefit from Large Language Models: A Survey](https://doi.org/10.1145/3678004) | TOIS'25 | [GitHub](https://github.com/CHIANGEL/Awesome-LLM-for-RecSys) |

### Tutorials

| Method | Paper Title | Published At | Website |
|:---:|:---|:---:|:---:|
| *Tutorial* | [Tutorial on Large Language Models for Recommendation](https://doi.org/10.1145/3604915.3609494) | RecSys'23 | [Website](https://llmrecsys.github.io/) |
| *Tutorial* | [Large Language Models for Recommendation: Progresses and Future Directions](https://doi.org/10.1145/3589335.3641247) | WWW'24 (Companion) | [Website](https://generative-rec.github.io/tutorial/) |
| *Tutorial* | [Recommendation with Generative Models (Gen-RecSys)](https://doi.org/10.1145/3701551.3703485) | WSDM'25 | [Website](https://www.wsdm-conference.org/2025/tutorials/) |
| *Tutorial* | [Navigating Large Language Models for Recommendation: From Architecture to Learning Paradigms and Deployment](https://doi.org/10.1145/3726302.3731696) | SIGIR'25 | [Website](https://generative-rec.github.io/tutorial/) |
| *Tutorial* | [A Tutorial on Recent Advances in Generative Conversational Recommender Systems](https://doi.org/10.1145/3705328.3748010) | RecSys'25 | [Website](https://recsys-lab.at/gen-conv-recsys-tutorial/) |
| *Tutorial* | [Towards Large Generative Recommendation: A Tokenization Perspective](https://doi.org/10.1145/3746252.3761451) | CIKM'25 | [Website](https://large-genrec.github.io/cikm2025.html) |
| *Tutorial* | [Generative Recommendation Models: Progress and Directions](https://doi.org/10.1145/3701716.3715856) | WWW'25 (Companion) | [Website](https://large-genrec.github.io/www2025.html) |
| *Tutorial* | [Tutorial on Generative Recommendation: Foundations and Frontiers](https://doi.org/10.1145/3770855.3816450) | KDD'26 | [Website](https://applied-machine-learning-lab.github.io/KDD2026_GenRec_Tutorial/) |


## Related Awesome Lists

- [HKBU-LAGAS/Awesome-Item-ID-Gen-RecSys](https://github.com/HKBU-LAGAS/Awesome-Item-ID-Gen-RecSys) — curated list on item identification/tokenization in generative recommender systems
- [hyp1231/awesome-generative-recommendation](https://github.com/hyp1231/awesome-generative-recommendation) — awesome things about generative recommendation models
- [Kuaishou-RecModel/Tri-Decoupled-GenRec](https://github.com/Kuaishou-RecModel/Tri-Decoupled-GenRec) — survey repo on tokenization, architecture, and optimization for generative recommendation (this list's format template)
- [Jyonn/VQ4Rec](https://github.com/Jyonn/VQ4Rec) — papers using vector quantization for recommender systems
- [jihoo-kim/Awesome-Generative-RecSys](https://github.com/jihoo-kim/Awesome-Generative-RecSys) — curated list of generative recommender systems (paper & code)
- [WLiK/LLM4Rec-Awesome-Papers](https://github.com/WLiK/LLM4Rec-Awesome-Papers) — papers/resources on LLM-based recommender systems
- [CHIANGEL/Awesome-LLM-for-RecSys](https://github.com/CHIANGEL/Awesome-LLM-for-RecSys) — papers/resources on LLM-related recommender system topics
- [Chriskuei/awesome-generative-retrieval-models](https://github.com/Chriskuei/awesome-generative-retrieval-models) — awesome papers on generative retrieval models (broader IR)
- [HaFred/awesome-generative-recsys](https://github.com/HaFred/awesome-generative-recsys) — auto-refreshing daily paper list for generative RecSys

## How to Contribute

We welcome contributions from the community! If you spot a missing paper, an outdated link, or a miscategorized entry, please open an issue or pull request on [GitHub](https://github.com/semantic-id-tutorial/awesome-semantic-id). When submitting a paper, please include: method name, paper title (linked to the official venue version if published, else arXiv), venue'year, and a link to official code if available.

## License

The content of this repository is licensed under [CC0 1.0](LICENSE) — feel free to reuse.
