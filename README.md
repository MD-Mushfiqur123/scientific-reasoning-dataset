# 🔬 Sovereign Bengali Scientific Reasoning Dataset
> **High-Entropy Chain-of-Thought (CoT) Dataset for Pure STEM Reasoning in Bengali**  
> Maintained by **Md Mushfiqur Rahim & L**  
> Ingestion Forge: [https://md-mushfiqur123.github.io/dataset-collector/](https://md-mushfiqur123.github.io/dataset-collector/)

[![Dataset Status](https://img.shields.io/badge/Status-Active%20Ingestion-10B981?style=for-the-badge)](https://md-mushfiqur123.github.io/dataset-collector/)
[![Gatekeeper](https://img.shields.io/badge/Gatekeeper-83%25%20Jaccard%20Deduplication-38BDF8?style=for-the-badge)](./core/gatekeeper.py)
[![Domains](https://img.shields.io/badge/Domains-Physics%20%7C%20Chemistry%20%7C%20Math%20%7C%20Biology-F59E0B?style=for-the-badge)](./shards/)
[![License](https://img.shields.io/badge/License-Apache%202.0-8B5CF6?style=for-the-badge)](./LICENSE)

---

## 📌 Overview
The **Sovereign Bengali Scientific Reasoning Dataset** is a dedicated, zero-fluff fine-tuning corpus designed to train next-generation open-weights LLMs in pure, high-depth Bengali scientific thinking.

Every record in this dataset contains:
1. **Challenging Scientific Problem (`prompt`)**: Olympiad and university-grade problems across STEM.
2. **Deep Chain-of-Thought (`thinking`)**: Internal reasoning from first principles with verified equations, calculus, and dimensional consistency.
3. **Pristine Final Solution (`solution`)**: Accurate institutional conclusion with bold boxed answers and proper SI units.

---

## 🏛️ 4 Core Scientific Domains

| Domain | Native Title | Focus & Scope | Storage Shard |
|---|---|---|---|
| **Physics** | পদার্থবিজ্ঞান | Classical mechanics, thermodynamics, electromagnetism, optics, quantum theory | [`shards/physics_verified.jsonl`](./shards/physics_verified.jsonl) |
| **Chemistry** | রসায়ন | Organic mechanisms, reaction kinetics, hybridization, thermochemistry | [`shards/chemistry_verified.jsonl`](./shards/chemistry_verified.jsonl) |
| **Mathematics** | উচ্চতর গণিত | Calculus (limits, derivatives, integrals), coordinate geometry, algebra, proofs | [`shards/mathematics_verified.jsonl`](./shards/mathematics_verified.jsonl) |
| **Biology** | জীববিজ্ঞান | Molecular biology, cellular respiration, genetics, biochemistry, human physiology | [`shards/biology_verified.jsonl`](./shards/biology_verified.jsonl) |

---

## 🛡️ The 83% Duplicate Gatekeeper Spec
To prevent data contamination and low-entropy repetitions:
- Every submission is screened against all existing samples using **Character 4-Gram and Shingle Jaccard Overlap**.
- If repeat similarity $\ge 83\%$, the record is automatically **declined**.
- Only pristine, informative records with $< 83\%$ overlap are admitted.

---

## 📋 JSONL Record Schema
```json
{
  "id": "mushfiqur_physics_1729080000000",
  "domain": "physics",
  "prompt": "একটি কণার অবস্থান ভেক্টর r(t) = 3t^2 i + 4t j। t = 2 সেকেন্ডে বেগ এবং ত্বরণ নির্ণয় করো।",
  "thinking": "এখানে অবস্থান r(t) দেওয়া আছে। বেগ v(t) = dr/dt = 6t i + 4 j। ত্বরণ a(t) = dv/dt = 6 i। t = 2 s এ v = 12i + 4j (মান 12.65 m/s) এবং a = 6i m/s^2।",
  "solution": "t = 2 সেকেন্ডে কণাটির বেগ v = 12i + 4j (মান 12.65 m/s) এবং ত্বরণ a = 6i m/s^2।",
  "timestamp": "2026-10-16T19:25:00Z",
  "contributor": "github:@contributor"
}
```

---

## 🚀 How to Contribute
You can contribute records with zero setup or API keys:
1. Visit the live web studio: **[https://md-mushfiqur123.github.io/dataset-collector/](https://md-mushfiqur123.github.io/dataset-collector/)**
2. Paste your AI Chain-of-Thought output (or click **🎲 LOAD SAMPLE** to test).
3. Click **`🚀 SUBMIT & PUSH TO DATASET`**.
4. The automated GitHub Actions Ingestion Bot will verify your submission and commit it to this repository automatically!

---

## 📄 License
This dataset is distributed under the **Apache 2.0 License**. Free for research, academic, and commercial fine-tuning.
