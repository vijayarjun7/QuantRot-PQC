# QuantRot-PQC

> HD³ rotation reduces KV-cache coefficient dynamic range
> for post-quantum secure LLM inference.

---

## Status

| Milestone | Status |
|---|---|
| Theory | ✅ Complete |
| Experiments | ✅ Complete |
| Paper draft | ✅ Complete |
| IACR ePrint | ✅ Submitted — paper number pending |
| arXiv cs.CR | 🔄 Endorsement pending |
| Workshop submission | ⬜ Planned |

---

## Main Result

HD³ rotation reduces L∞ norm by **40.1%** on 500 real
KV vectors from Llama-3.2-1B — double the ≥20% threshold.

| Dataset | L∞ Before | L∞ After | Reduction | H1 Status |
|---|---|---|---|---|
| Synthetic (d=256, n=1000) | 0.1907 | 0.1904 | 0.2% | Not Supported |
| Real Llama-3.2-1B (d=64, n=500) | 0.5407 | 0.3239 | **40.1%** | **Supported** ✅ |

Kurtosis drops from 6.15 → -0.09 confirming near-Gaussian
concentration after rotation.

---

## Paper

**Title:** QuantRot-PQC: HD³ Rotation Reduces KV-Cache
Coefficient Dynamic Range for Post-Quantum Secure LLM Inference

**Author:** Venkata Vijaya Kumari D.

**IACR ePrint:** coming within 1-2 business days

**arXiv:** pending cs.CR endorsement

---

## Research Claim

> We propose QuantRot-PQC, a t-design-based random unitary
> pre-rotation applied to LLM KV-cache vectors prior to
> CRYSTALS-Kyber polynomial encoding. By redistributing vector
> energy across dimensions, the HD³ rotation produces concentrated
> coordinate distributions with variance proxy approximately 1/d,
> reducing the centered coefficient dynamic range (L∞ spread in
> centered Zq representation) after scaling into polynomial form.
> The pre-rotation is public, invertible, input-independent, and
> operates entirely in the plaintext domain prior to Kyber's
> algebraic operations. It does not alter the Module-LWE problem
> instance. A formal security reduction is left for future work.

---

## Hypotheses

| Hypothesis | Result |
|---|---|
| H1: HD³ reduces L∞ norm ≥20% on real KV vectors | ✅ SUPPORTED — 40.1% reduction |
| H1-synthetic: same on isotropic Gaussian vectors | ❌ Null (expected — rotation-invariant) |
| H2: Pipeline latency acceptable vs vanilla Kyber | ❌ Python overhead confound — compiled kernel needed |

---

## Experiments

| Experiment | File | Key Result |
|---|---|---|
| Kyber-512 baseline | `experiments/01_baseline/` | 6.25 μs encapsulation |
| H1 synthetic | `experiments/02_h1_rotation/` | 0.2% reduction (null, expected) |
| H1 real KV | `experiments/03_real_kv/` | 40.1% reduction ✅ |
| H2 pipeline | `experiments/04_full_benchmark/` | Python overhead confound |

All experiments in:
👉 https://github.com/vijayarjun7/pqc-kv-cache-demo

---

## Paper

```
paper/
├── main.tex                  LaTeX source
└── QuantRot-PQC-v1.pdf      Final paper (8 pages)
```

---

## Hardware

```
MacBook Air (Apple M4, 24GB RAM, macOS 26.5.1)
Python 3.14.2
liboqs-python (CRYSTALS-Kyber-512)
meta-llama/Llama-3.2-1B via HuggingFace
```

---

## References

1. CRYSTALS-Kyber spec v3.02 — https://pq-crystals.org/kyber
2. TurboQuant — https://arxiv.org/abs/2504.19874
3. Brandão et al. 2016 — https://arxiv.org/abs/1208.0692
4. Harrow & Mehraban 2018 — https://arxiv.org/abs/1809.06957
5. Albrecht et al. 2015 — https://eprint.iacr.org/2015/046

---

## Related

**Demo repo:** https://github.com/vijayarjun7/pqc-kv-cache-demo
Simulates PQC overhead on LLM KV-cache with QuantRot-inspired
optimization and interactive Streamlit dashboard.

---

## Author

**Venkata Vijaya Kumari D.**
Independent Researcher | Coppell, TX
vijayaqa.rv7@gmail.com
https://linkedin.com/in/vijayakumari007
https://github.com/vijayarjun7
