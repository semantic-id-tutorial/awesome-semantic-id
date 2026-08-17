# Awesome Semantic IDs for Recommender Systems

[![Paper](https://img.shields.io/badge/CIKM'26-10.1145%2F3799682.3839274-red)](https://doi.org/10.1145/3799682.3839274)
[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
![Last commit](https://img.shields.io/github/last-commit/semantic-id-tutorial/awesome-semantic-id)
![GitHub stars](https://img.shields.io/github/stars/semantic-id-tutorial/awesome-semantic-id?style=social)

A curated reading list on **Semantic IDs for Recommender Systems** — item identity encoded as discrete, content-aware token sequences (typically via RQ-VAE / RQ-KMeans style vector quantization) rather than arbitrary integer IDs. This list accompanies the CIKM '26 tutorial *["IDs That Mean Something: A Hands-On Tutorial on Semantic IDs for Recommender Systems"](https://doi.org/10.1145/3799682.3839274)*.

We trace the field from raw IDs to semantic IDs, and organize papers published **since [TIGER](https://proceedings.neurips.cc/paper_files/paper/2023/hash/20dcab0f14046a5c6b02b61da9f13229-Abstract-Conference.html) (NeurIPS '23)** — the paper that established generating semantic IDs as a recommendation paradigm — across construction, generative and discriminative usage, multimodal/collaborative fusion, cold-start, cross-domain transfer, and cross-task unification. Where a paper has both an official venue version and an arXiv preprint, we link the official version and note the arXiv id.

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
| *Multimedia RS Survey* | [Recommender Systems Leveraging Multimedia Content](https://doi.org/10.1145/3453142) | ACM CSUR'21 | / |
| *Multi-Modal RS Hands-On* | [Multi-Modal Recommender Systems: Hands-On Exploration](https://doi.org/10.1145/3460231.3473324) | RecSys'21 | [![Github](https://img.shields.io/github/stars/PreferredAI/cornac.svg?style=social&label=Github)](https://github.com/PreferredAI/cornac) |

## Semantic ID Construction & Tokenization

How to *build* semantic IDs — quantization/tokenization architectures that turn item content into discrete token sequences.

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *VQ-Rec* | [Learning Vector-Quantized Item Representation for Transferable Sequential Recommenders](https://doi.org/10.1145/3543507.3583434) | WWW'23 | [![Github](https://img.shields.io/github/stars/RUCAIBox/VQ-Rec.svg?style=social&label=Github)](https://github.com/RUCAIBox/VQ-Rec) |
| *GenRet* | [Learning to Tokenize for Generative Retrieval](https://proceedings.neurips.cc/paper_files/paper/2023/hash/91228b942a4528cdae031c1b68b127e8-Abstract-Conference.html) | NeurIPS'23 | [![Github](https://img.shields.io/github/stars/sunnweiwei/GenRet.svg?style=social&label=Github)](https://github.com/sunnweiwei/GenRet) |
| *SEATER* | [Generative Retrieval with Semantic Tree-Structured Item Identifiers via Contrastive Learning](https://arxiv.org/abs/2309.13375) | arXiv'23 | [![Github](https://img.shields.io/github/stars/Ethan00Si/SEATER_Generative_Retrieval.svg?style=social&label=Github)](https://github.com/Ethan00Si/SEATER_Generative_Retrieval) |
| *LMIndexer* | [Language Models as Semantic Indexers](https://arxiv.org/abs/2310.07815) | ICML'24 | [![Github](https://img.shields.io/github/stars/PeterGriffinJin/LMIndexer.svg?style=social&label=Github)](https://github.com/PeterGriffinJin/LMIndexer) |
| *ActionPiece* | [ActionPiece: Contextually Tokenizing Action Sequences for Generative Recommendation](https://arxiv.org/abs/2502.13581) | ICML'25 | [![Github](https://img.shields.io/github/stars/google-deepmind/action_piece.svg?style=social&label=Github)](https://github.com/google-deepmind/action_piece) |
| *TokenRec* | [TokenRec: Learning to Tokenize ID for LLM-based Generative Recommendation](https://arxiv.org/abs/2406.10450) | TKDE'25 | [![Github](https://img.shields.io/github/stars/Quhaoh233/TokenRec.svg?style=social&label=Github)](https://github.com/Quhaoh233/TokenRec) |
| *UTGRec* | [Universal Item Tokenization for Transferable Generative Recommendation](https://arxiv.org/abs/2504.04405) | arXiv'25 | [![Github](https://img.shields.io/github/stars/RUCAIBox/UTGRec.svg?style=social&label=Github)](https://github.com/RUCAIBox/UTGRec) |
| *HiD-VAE* | [HiD-VAE: Interpretable Generative Recommendation via Hierarchical and Disentangled Semantic IDs](https://arxiv.org/abs/2508.04618) | arXiv'25 | / |
| *PCR-CA* | [PCR-CA: Parallel Codebook Representations with Contrastive Alignment for Multiple-Category App Recommendation](https://arxiv.org/abs/2508.18166) | arXiv'25 | / |
| *COSETTE* | [Closing the Performance Gap in Generative Recommenders with Collaborative Tokenization and Efficient Modeling](https://arxiv.org/abs/2508.14910) | arXiv'25 | / |
| *PSRQ* | [Progressive Semantic Residual Quantization for Multimodal-Joint Interest Modeling in Music Recommendation](https://arxiv.org/abs/2508.20359) | CIKM'25 | / |
| *FORGE* | [FORGE: Forming Semantic Identifiers for Generative Retrieval in Industrial Datasets](https://arxiv.org/abs/2509.20904) | arXiv'25 | [![Github](https://img.shields.io/github/stars/selous123/al_sid.svg?style=social&label=Github)](https://github.com/selous123/al_sid) |
| *Purely Semantic Indexing* | [Purely Semantic Indexing for LLM-based Generative Recommendation and Retrieval](https://arxiv.org/abs/2509.16446) | arXiv'25 | / |
| *Semantics Meet Signals* | [Semantics Meet Signals: Dual Codebook Representation Learning for Generative Recommendation](https://arxiv.org/abs/2511.20673) | arXiv'25 | / |
| *H2W* | [The Best of the Two Worlds: Harmonizing Semantic and Hash IDs for Sequential Recommendation](https://arxiv.org/abs/2512.10388) | arXiv'25 | / |
| *MERGE* | [MERGE: Next-Generation Item Indexing Paradigm for Large-Scale Streaming Recommendation](https://arxiv.org/abs/2601.20199) | arXiv'26 | / |
| *SemanticConvergence* | [Semantic Convergence: Harmonizing Recommender Systems via Two-Stage Alignment and Behavioral Semantic Tokenization](https://arxiv.org/abs/2412.13771) | AAAI'25 | / |
| *R3-VAE* | [R3-VAE: Reference Vector-Guided Rating Residual Quantization VAE for Generative Recommendation](https://arxiv.org/abs/2604.11440) | arXiv'26 | / |
| *PrefixMem* | [LLMs Need Encoders for Semantic IDs Too](https://arxiv.org/abs/2606.00324) | arXiv'26 | / |
| *Rethinking Tokenizer* | [Rethinking Generative Recommender Tokenizer: RecSys-Native Encoding and Semantic Quantization Beyond LLMs](https://arxiv.org/abs/2602.02338) | arXiv'26 | / |
| *UniSID* | [End-to-End Semantic ID Generation for Generative Advertisement Recommendation](https://arxiv.org/abs/2602.10445) | arXiv'26 | / |
| *TAAC-SID* | [Tencent Advertising Algorithm Challenge 2025: All-Modality Generative Recommendation](https://arxiv.org/abs/2604.04976) | arXiv'26 | [![Github](https://img.shields.io/github/stars/TencentAdvertisingAlgorithmCompetition/baseline_2025.svg?style=social&label=Github)](https://github.com/TencentAdvertisingAlgorithmCompetition/baseline_2025) |
| *DIGER* | [Differentiable Semantic ID for Generative Recommendation](https://doi.org/10.1145/3805712.3809641) | SIGIR'26 | [![Github](https://img.shields.io/github/stars/junchen-fu/DIGER.svg?style=social&label=Github)](https://github.com/junchen-fu/DIGER) |

## Generative Recommendation with Semantic IDs

Semantic IDs as the backbone of **generative retrieval/recommendation**: a model autoregressively generates the semantic ID of the next item, starting from TIGER.

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *TIGER* | [Recommender Systems with Generative Retrieval](https://proceedings.neurips.cc/paper_files/paper/2023/hash/20dcab0f14046a5c6b02b61da9f13229-Abstract-Conference.html) | NeurIPS'23 (seminal) | [![Github](https://img.shields.io/github/stars/EdoardoBotta/RQ-VAE-Recommender.svg?style=social&label=Github)](https://github.com/EdoardoBotta/RQ-VAE-Recommender) |
| *LC-Rec* | [Adapting Large Language Models by Integrating Collaborative Semantics for Recommendation](https://doi.org/10.1109/ICDE60146.2024.00268) | ICDE'24 | [![Github](https://img.shields.io/github/stars/RUCAIBox/LC-Rec.svg?style=social&label=Github)](https://github.com/RUCAIBox/LC-Rec) |
| *ColaRec* | [Content-Based Collaborative Generation for Recommender Systems](https://doi.org/10.1145/3627673.3679692) | CIKM'24 | [![Github](https://img.shields.io/github/stars/Junewang0614/ColaRec.svg?style=social&label=Github)](https://github.com/Junewang0614/ColaRec) |
| *MBGen* | [Multi-Behavior Generative Recommendation](https://doi.org/10.1145/3627673.3679730) | CIKM'24 | [![Github](https://img.shields.io/github/stars/anananan116/MBGen.svg?style=social&label=Github)](https://github.com/anananan116/MBGen) |
| *EAGER* | [EAGER: Two-Stream Generative Recommender with Behavior-Semantic Collaboration](https://doi.org/10.1145/3637528.3671775) | KDD'24 | [![Github](https://img.shields.io/github/stars/yewzz/EAGER.svg?style=social&label=Github)](https://github.com/yewzz/EAGER) |
| *MMGRec* | [MMGRec: Multimodal Generative Recommendation with Transformer Model](https://arxiv.org/abs/2404.16555) | arXiv'24 | [![Github](https://img.shields.io/github/stars/hanliu95/MMGRec.svg?style=social&label=Github)](https://github.com/hanliu95/MMGRec) |
| *MVIGER* | [MVIGER: Multi-View Variational Integration of Complementary Knowledge for Generative Recommender](https://arxiv.org/abs/2408.08686) | arXiv'24 | / |
| *EAGER-LLM* | [EAGER-LLM: Enhancing Large Language Models as Recommenders through Exogenous Behavior-Semantic Integration](https://doi.org/10.1145/3696410.3714933) | WWW'25 | / |
| *SETRec* | [SETRec: Order-Agnostic Identifier for Large Language Model-based Generative Recommendation](https://doi.org/10.1145/3726302.3730053) | SIGIR'25 | [![Github](https://img.shields.io/github/stars/Linxyhaha/SETRec.svg?style=social&label=Github)](https://github.com/Linxyhaha/SETRec) |
| *RPG* | [Generating Long Semantic IDs in Parallel for Recommendation](https://doi.org/10.1145/3711896.3736979) | KDD'25 | [![Github](https://img.shields.io/github/stars/facebookresearch/RPG_KDD2025.svg?style=social&label=Github)](https://github.com/facebookresearch/RPG_KDD2025) |
| *GNPR-SID* | [Generative Next POI Recommendation with Semantic ID](https://arxiv.org/abs/2506.01375) | KDD'25 | [![Github](https://img.shields.io/github/stars/wds1996/GNPR-SID.svg?style=social&label=Github)](https://github.com/wds1996/GNPR-SID) |
| *EARN* | [EARN: Efficient Inference Acceleration for LLM-based Generative Recommendation by Register Tokens](https://arxiv.org/abs/2507.00715) | KDD'25 | [![Github](https://img.shields.io/github/stars/transcend-0/EARN.svg?style=social&label=Github)](https://github.com/transcend-0/EARN) |
| *AtSpeed* | [Efficient Inference for Large Language Model-based Generative Recommendation](https://openreview.net/forum?id=ACSNlt77hq) | ICLR'25 | [![Github](https://img.shields.io/github/stars/Linxyhaha/AtSpeed.svg?style=social&label=Github)](https://github.com/Linxyhaha/AtSpeed) |
| *SpecGR* | [Inductive Generative Recommendation via Retrieval-based Speculation](https://arxiv.org/abs/2410.02939) | AAAI'26 | [![Github](https://img.shields.io/github/stars/Jamesding000/SpecGR.svg?style=social&label=Github)](https://github.com/Jamesding000/SpecGR) |
| *LLaDA-Rec* | [LLaDA-Rec: Discrete Diffusion for Parallel Semantic ID Generation in Generative Recommendation](https://arxiv.org/abs/2511.06254) | arXiv'25 | [![Github](https://img.shields.io/github/stars/TengShi-RUC/LLaDA-Rec.svg?style=social&label=Github)](https://github.com/TengShi-RUC/LLaDA-Rec) |
| *ContRec* | [Diffusion Generative Recommendation with Continuous Tokens](https://arxiv.org/abs/2504.12007) | arXiv'25 | [![Github](https://img.shields.io/github/stars/Quhaoh233/ContRec.svg?style=social&label=Github)](https://github.com/Quhaoh233/ContRec) |
| *GRAM* | [GRAM: Generative Recommendation via Semantic-aware Multi-granular Late Fusion](https://aclanthology.org/2025.acl-long.1596/) | ACL'25 | [![Github](https://img.shields.io/github/stars/skleee/GRAM.svg?style=social&label=Github)](https://github.com/skleee/GRAM) |
| *GRAM (retrieval)* | [Generative Retrieval and Alignment Model: A New Paradigm for E-commerce Retrieval](https://arxiv.org/abs/2504.01403) | WWW'25 (Companion) | / |
| *OneRec* | [OneRec: Unifying Retrieve and Rank with Generative Recommender and Iterative Preference Alignment](https://arxiv.org/abs/2502.18965) | arXiv'25 | [![Github](https://img.shields.io/github/stars/Kuaishou-OneRec/OpenOneRec.svg?style=social&label=Github)](https://github.com/Kuaishou-OneRec/OpenOneRec) |
| *OneRec (Tech Report)* | [OneRec Technical Report](https://arxiv.org/abs/2506.13695) | arXiv'25 | [![Github](https://img.shields.io/github/stars/Kuaishou-OneRec/OpenOneRec.svg?style=social&label=Github)](https://github.com/Kuaishou-OneRec/OpenOneRec) |
| *OneRec-V2* | [OneRec-V2 Technical Report](https://arxiv.org/abs/2508.20900) | arXiv'25 | [![Github](https://img.shields.io/github/stars/Kuaishou-OneRec/OpenOneRec.svg?style=social&label=Github)](https://github.com/Kuaishou-OneRec/OpenOneRec) |
| *COBRA* | [Sparse Meets Dense: Unified Generative Recommendations with Cascaded Sparse-Dense Representations](https://openreview.net/forum?id=zugMif2nm6) | NeurIPS'25 | / |
| *MTGR* | [MTGR: Industrial-Scale Generative Recommendation Framework in Meituan](https://doi.org/10.1145/3746252.3761565) | CIKM'25 | / |
| *GR4AD* | [Generative Recommendation for Large-Scale Advertising](https://arxiv.org/abs/2602.22732) | arXiv'26 | / |
| *TSGR* | [TSGR: Taobao Search Generative Retrieval](https://arxiv.org/abs/2607.18796) | arXiv'26 | / |
| *HiGR* | [HiGR: Industrial-Scale Hierarchical Generative Slate Recommendation Framework in Tencent](https://arxiv.org/abs/2512.24787) | arXiv'25 | / |
| *GLIDE* | [Deploying Semantic ID-based Generative Retrieval for Large-Scale Podcast Discovery at Spotify](https://arxiv.org/abs/2603.17540) | arXiv'26 | / |
| *Model-Scaling for SIDs* | [Understanding Generative Recommendation with Semantic IDs from a Model-scaling View](https://arxiv.org/abs/2509.25522) | arXiv'25 | / |
| *NEZHA* | [NEZHA: A Zero-sacrifice and Hyperspeed Decoding Architecture for Generative Recommendations](https://arxiv.org/abs/2511.18793) | arXiv'25 | / |
| *Align3GR* | [Align3GR: Unified Multi-Level Alignment for LLM-based Generative Recommendation](https://arxiv.org/abs/2511.11255) | AAAI'26 | / |
| *PROMISE* | [PROMISE: Process Reward Models Unlock Test-Time Scaling Laws in Generative Recommendations](https://arxiv.org/abs/2601.04674) | arXiv'26 | / |
| *Latte* | [Expressiveness Limits of Autoregressive Semantic ID Generation in Generative Recommendation](https://arxiv.org/abs/2605.06331) | arXiv'26 | [![Github](https://img.shields.io/github/stars/hyp1231/Latte.svg?style=social&label=Github)](https://github.com/hyp1231/Latte) |
| *DualGR* | [DualGR: Generative Retrieval with Long and Short-Term Interests Modeling](https://arxiv.org/abs/2511.12518) | WWW'26 (Best Short Paper) | / |
| *Text2Tracks* | [Text2Tracks: Prompt-based Music Recommendation via Generative Retrieval](https://arxiv.org/abs/2503.24193) | arXiv'25 | [![Github](https://img.shields.io/github/stars/mayurbhangale/text2tracks.svg?style=social&label=Github)](https://github.com/mayurbhangale/text2tracks) |
| *RedGR* | [RedGR: Unified Generative Retrieval for Recommendation in REDnote](https://doi.org/10.1145/3805712.3808417) | SIGIR'26 | / |

## Semantic IDs in Discriminative Ranking & Retrieval

Semantic IDs used as **structured input features** in traditional discriminative ranking, CTR prediction, and embedding-based retrieval pipelines (not autoregressive generation).

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *UIST* | [Discrete Semantic Tokenization for Deep CTR Prediction](https://doi.org/10.1145/3589335.3651558) | WWW'24 (Companion) | [![Github](https://img.shields.io/github/stars/Jyonn/SemanticTokenizer.svg?style=social&label=Github)](https://github.com/Jyonn/SemanticTokenizer) |
| *SIDE* | [SIDE: Semantic ID Embedding for Effective Learning from Sequences](https://arxiv.org/abs/2506.16698) | AdKDD'25 | / |
| *USIRL* | [Unified Semantic and ID Representation Learning for Deep Recommenders](https://arxiv.org/abs/2502.16474) | arXiv'25 | / |
| *IDProxy* | [IDProxy: Cold-Start CTR Prediction for Ads and Recommendation at Xiaohongshu with Multimodal LLMs](https://arxiv.org/abs/2603.01590) | arXiv'26 | / |
| *RQ-GMM* | [RQ-GMM: Residual Quantized Gaussian Mixture Model for Multimodal Semantic Discretization in CTR Prediction](https://arxiv.org/abs/2602.12593) | SIGIR'26 | / |
| *PaletteID* | [PaletteID: Prototype-Composed Semantic Identifiers for Multimodal CTR Prediction](https://arxiv.org/abs/2607.29000) | arXiv'26 | / |
| *Dual-Purpose SIDs* | [Tokens are All You Need: Dual-purpose Semantic IDs for Achieving LLM-Level I/O Efficiency in Recommendation Systems](https://arxiv.org/abs/2607.24865) | arXiv'26 | / |
| *FedMM* | [FedMM: Federated Collaborative Signal Quantization for Multi-Market CTR Prediction](https://arxiv.org/abs/2605.11433) | SIGIR'26 | / |
| *SIREN* | [SIREN: Unified Multi-Granularity Semantic Interaction for Multi-Modal Lifelong User Interest Modeling](https://arxiv.org/abs/2605.25726) | arXiv'26 | / |
| *Snapchat SIDs* | [Semantic IDs for Recommender Systems at Snapchat: Use Cases, Technical Challenges, and Design Choices](https://doi.org/10.1145/3805712.3808405) | SIGIR'26 | / |
| *STORE* | [STORE: Semantic Tokenization, Orthogonal Rotation and Efficient Attention for Scaling Up Ranking Models](https://arxiv.org/abs/2511.18805) | arXiv'25 | / |

## Multimodality in Semantic ID Construction

Papers centered on fusing multiple content modalities (text/image/audio/video) into semantic ID construction.

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *MMQ* | [MMQ: Multimodal Mixture-of-Quantization Tokenization for Semantic ID Generation and User Behavioral Adaptation](https://arxiv.org/abs/2508.15281) | WSDM'26 | / |
| *Q-BERT4Rec* | [Q-BERT4Rec: Quantized Semantic-ID Representation Learning for Multimodal Recommendation](https://arxiv.org/abs/2512.02474) | arXiv'25 | / |
| *QARM V2* | [QARM V2: Quantitative Alignment Multi-Modal Recommendation for Reasoning User Sequence Modeling](https://arxiv.org/abs/2602.08559) | arXiv'26 | / |
| *DMESR* | [DMESR: Dual-view MLLM-based Enhancing Framework for Multimodal Sequential Recommendation](https://arxiv.org/abs/2602.13715) | arXiv'26 | / |
| *AdaSID* | [Beyond Static Collision Handling: Adaptive Semantic ID Learning for Multimodal Recommendation at Industrial Scale](https://arxiv.org/abs/2604.23522) | arXiv'26 | / |

## Collaborative Signals in Semantic ID Construction

Papers specifically about injecting/aligning collaborative-filtering or behavioral signals into semantic ID construction — the tension between IDs that are semantically meaningful (from content) vs. recommendation-aware (from interactions). Includes joint/end-to-end tokenizer-recommender training, contrastive alignment to CF embeddings, semantic-collaborative disentanglement, and collision/staleness handling driven by interaction skew.

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *LETTER* | [Learnable Item Tokenization for Generative Recommendation](https://doi.org/10.1145/3627673.3679569) | CIKM'24 | [![Github](https://img.shields.io/github/stars/HonghuiBao2000/LETTER.svg?style=social&label=Github)](https://github.com/HonghuiBao2000/LETTER) |
| *CoST* | [CoST: Contrastive Quantization based Semantic Tokenization for Generative Recommendation](https://doi.org/10.1145/3640457.3688178) | RecSys'24 | / |
| *ETEGRec* | [Generative Recommender with End-to-End Learnable Item Tokenization](https://doi.org/10.1145/3726302.3729989) | SIGIR'25 | [![Github](https://img.shields.io/github/stars/RUCAIBox/ETEGRec.svg?style=social&label=Github)](https://github.com/RUCAIBox/ETEGRec) |
| *CCFRec* | [Bridging Textual-Collaborative Gap through Semantic Codes for Sequential Recommendation](https://doi.org/10.1145/3711896.3736869) | KDD'25 | [![Github](https://img.shields.io/github/stars/RUCAIBox/CCFRec.svg?style=social&label=Github)](https://github.com/RUCAIBox/CCFRec) |
| *DiscRec* | [DiscRec: Disentangled Semantic-Collaborative Modeling for Generative Recommendation](https://arxiv.org/abs/2506.15576) | arXiv'25 | [![Github](https://img.shields.io/github/stars/Ten-Mao/DiscRec.svg?style=social&label=Github)](https://github.com/Ten-Mao/DiscRec) |
| *BBQRec* | [BBQRec: Behavior-Bind Quantization for Multi-Modal Sequential Recommendation](https://arxiv.org/abs/2504.06636) | arXiv'25 | / |
| *DQ-VAE* | [Representation Quantization for Collaborative Filtering Augmentation](https://arxiv.org/abs/2508.11194) | arXiv'25 | / |
| *ADC-SID* | [Taming the Long Tail: Denoising Collaborative Information for Robust Semantic ID Generation](https://arxiv.org/abs/2510.25622) | arXiv'25 | / |
| *CEMG* | [CEMG: Collaborative-Enhanced Multimodal Generative Recommendation](https://arxiv.org/abs/2512.21543) | MMM'26 | / |
| *DECOR* | [Learning Decomposed Contextual Token Representations from Pretrained and Collaborative Signals for Generative Recommendation](https://arxiv.org/abs/2509.10468) | SIGIR'26 | [![Github](https://img.shields.io/github/stars/yliuaa/DECOR.svg?style=social&label=Github)](https://github.com/yliuaa/DECOR) |
| *GateSID* | [GateSID: Adaptive Gating for Balancing Semantic and Collaborative Signals in Recommendation](https://arxiv.org/abs/2603.22916) | arXiv'26 | / |
| *SID Staleness* | [Mitigating Collaborative Semantic ID Staleness in Generative Retrieval](https://doi.org/10.1145/3805712.3809877) | SIGIR'26 | / |
| *UNGER* | [UNGER: Generative Recommendation with A Unified Code via Semantic and Collaborative Integration](https://arxiv.org/abs/2502.06269) | arXiv'25 | / |
| *SaviorRec* | [SaviorRec: Semantic-Behavior Alignment for Cold-Start Recommendation](https://arxiv.org/abs/2508.01375) | arXiv'25 | / |
| *Bi-Level Tokenization* | [Bi-Level Optimization for Generative Recommendation: Bridging Tokenization and Generation](https://doi.org/10.1145/3805712.3809632) | SIGIR'26 | / |
| *PRISM* | [PRISM: Purified Representation and Integrated Semantic Modeling for Generative Sequential Recommendation](https://arxiv.org/abs/2601.16556) | arXiv'26 | / |
| *QuaSID* | [Stop Treating Collisions Equally: Qualification-Aware Semantic ID Learning for Recommendation at Industrial Scale](https://arxiv.org/abs/2603.00632) | arXiv'26 | / |
| *Rethinking Sem-Collab* | [Rethinking Semantic Collaborative Integration: Why Alignment Is Not Enough](https://doi.org/10.1145/3805712.3808539) | SIGIR'26 | / |

## Cold-Start Recommendation with Semantic IDs

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *MoToRec* | [MoToRec: Sparse-Regularized Multimodal Tokenization for Cold-Start Recommendation](https://doi.org/10.1609/aaai.v40i18.38558) | AAAI'26 | / |
| *ColdGenRec* | [Cold-Starts in Generative Recommendation: A Reproducibility Study](https://arxiv.org/abs/2603.29845) | SIGIR'26 | [![Github](https://img.shields.io/github/stars/zhangzhen-research/ColdGenrec.svg?style=social&label=Github)](https://github.com/zhangzhen-research/ColdGenrec) |
| *GR Cold-Item Reachability* | [Can Generative Recommendation Reach Cold Items? A Temporal Perspective on Semantic-ID Generation](https://arxiv.org/abs/2607.21101) | arXiv'26 | [![Github](https://img.shields.io/github/stars/Lucas-PJ/GRColdItemReachability.svg?style=social&label=Github)](https://github.com/Lucas-PJ/GRColdItemReachability) |
| *GTI* | [Grounded Token Initialization for New Vocabulary in LMs for Generative Recommendation](https://arxiv.org/abs/2604.02324) | arXiv'26 | / |

## Cross-Domain Transfer with Semantic IDs

Using the shared semantic structure of semantic IDs to transfer knowledge across recommendation domains/platforms without explicit source-target alignment.

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *Quantizing Intent* | [Quantizing Intent: Cross-Domain Semantic IDs from Organic Activity for Industrial Ranking](https://arxiv.org/abs/2606.01396) | arXiv'26 (LinkedIn) | / |
| *GenCDSR* | [Empowering Cross-Domain Sequential Recommendation with Hybrid Tokenization and Serial-Parallel Decoding](https://arxiv.org/abs/2607.28659) | RecSys'26 | [![Github](https://img.shields.io/github/stars/Applied-Machine-Learning-Lab/RecSys2026_GenCDSR.svg?style=social&label=Github)](https://github.com/Applied-Machine-Learning-Lab/RecSys2026_GenCDSR) |
| *MetaRec* | [Transferable Sequential Recommendation via Vector Quantized Meta Learning](https://arxiv.org/abs/2411.01785) | IEEE BigData'24 | / |
| *RecGPT* | [RecGPT: A Foundation Model for Sequential Recommendation](https://aclanthology.org/2025.emnlp-main.513/) | EMNLP'25 | [![Github](https://img.shields.io/github/stars/HKUDS/RecGPT.svg?style=social&label=Github)](https://github.com/HKUDS/RecGPT) |
| *RecBase* | [RecBase: Generative Foundation Model Pretraining for Zero-Shot Recommendation](https://aclanthology.org/2025.emnlp-main.786/) | EMNLP'25 | / |

## Cross-Task Unification & Semantic Planning

Semantic IDs as a shared representation unifying recommendation with search/retrieval and other tasks, and early work on using semantic IDs for planning/reasoning about what the next exposure should accomplish.

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *SIDReasoner* | [Reasoning over Semantic IDs Enhances Generative Recommendation](https://arxiv.org/abs/2603.23183) | KDD'26 | [![Github](https://img.shields.io/github/stars/HappyPointer/SIDReasoner.svg?style=social&label=Github)](https://github.com/HappyPointer/SIDReasoner) |
| *SIGMA* | [SIGMA: A Semantic-Grounded Instruction-Driven Generative Multi-Task Recommender at AliExpress](https://doi.org/10.1145/3805712.3808421) | SIGIR'26 (Industry) | / |
| *UniSearch* | [UniSearch: Rethinking Search System with a Unified Generative Architecture](https://arxiv.org/abs/2509.06887) | arXiv'25 | / |

## Related Surveys & Tutorials

### Surveys

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *Item-ID Survey* | [A Survey of Item Identifiers in Generative Recommendation: Construction, Alignment, and Generation](https://doi.org/10.36227/techrxiv.176945895.52184668/v1) | TechRxiv'26 | [![Github](https://img.shields.io/github/stars/HKBU-LAGAS/Awesome-Item-ID-Gen-RecSys.svg?style=social&label=Github)](https://github.com/HKBU-LAGAS/Awesome-Item-ID-Gen-RecSys) |
| *Practitioner's Handbook* | [Generative Recommendation with Semantic IDs: A Practitioner's Handbook](https://doi.org/10.1145/3746252.3761612) | CIKM'25 | / |
| *VQ4Rec Survey* | [Vector Quantization for Recommender Systems: A Review and Outlook](https://arxiv.org/abs/2405.03110) | arXiv'24 | [![Github](https://img.shields.io/github/stars/Jyonn/VQ4Rec.svg?style=social&label=Github)](https://github.com/Jyonn/VQ4Rec) |
| *Gen-Rec Data/Model/Tasks* | [A Survey on Generative Recommendation: Data, Model, and Tasks](https://arxiv.org/abs/2510.27157) | arXiv'25 | / |
| *Gen-RecSys* | [A Review of Modern Recommender Systems Using Generative Models (Gen-RecSys)](https://doi.org/10.1145/3637528.3671474) | KDD'24 | / |
| *Gen Search & Rec Survey* | [A Survey of Generative Search and Recommendation in the Era of Large Language Models](https://arxiv.org/abs/2404.16924) | arXiv'24 | / |
| *LLM4Rec Survey* | [A Survey on Large Language Models for Recommendation](https://arxiv.org/abs/2305.19860) | arXiv'23 | [![Github](https://img.shields.io/github/stars/WLiK/LLM4Rec-Awesome-Papers.svg?style=social&label=Github)](https://github.com/WLiK/LLM4Rec-Awesome-Papers) |
| *LLM4Rec TOIS Survey* | [How Can Recommender Systems Benefit from Large Language Models: A Survey](https://doi.org/10.1145/3678004) | TOIS'24 | [![Github](https://img.shields.io/github/stars/CHIANGEL/Awesome-LLM-for-RecSys.svg?style=social&label=Github)](https://github.com/CHIANGEL/Awesome-LLM-for-RecSys) |

### Tutorials

| Method | Paper Title | Published At | Code |
|:---:|:---|:---:|:---:|
| *Tutorial* | [Tutorial on Large Language Models for Recommendation](https://doi.org/10.1145/3604915.3609494) | RecSys'23 | / |
| *Tutorial* | [Large Language Models for Recommendation: Progresses and Future Directions](https://doi.org/10.1145/3589335.3641247) | WWW'24 (Companion) | / |
| *Tutorial* | [Recommendation with Generative Models (Gen-RecSys)](https://doi.org/10.1145/3701551.3703485) | WSDM'25 | / |
| *Tutorial* | [Navigating Large Language Models for Recommendation: From Architecture to Learning Paradigms and Deployment](https://doi.org/10.1145/3726302.3731696) | SIGIR'25 | / |
| *Tutorial* | [A Tutorial on Recent Advances in Generative Conversational Recommender Systems](https://doi.org/10.1145/3705328.3748010) | RecSys'25 | / |

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
