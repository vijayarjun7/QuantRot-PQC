# QuantRot-PQC

HD³ Rotation Reduces KV-Cache Coefficient Dynamic Range
for Post-Quantum Secure LLM Inference

## Status
Paper draft complete — IACR ePrint submission pending

## Main Result
HD³ rotation reduces L∞ norm by **40.1%** on 500 real
Llama-3.2-1B KV vectors — double the ≥20% threshold.
Kurtosis drops from 6.15 to -0.09 (near-Gaussian).
H1 SUPPORTED on real transformer KV vectors.

## This Repo Contains

paper/
main.tex               — LaTeX source
QuantRot-PQC-v1.pdf    — Final paper draft

## Related Repo
Simulation demo and experiments:
https://github.com/vijayarjun7/pqc-kv-cache-demo

Experiments include:
- 01_baseline: Kyber-512 baseline (6.25 μs, liboqs)
- 02_h1_rotation: H1 synthetic null result (0.2%)
- 03_real_kv: H1 real Llama-3.2-1B (40.1% — SUPPORTED)
- 04_full_benchmark: H2 pipeline latency

## Hardware
MacBook Air (Apple M4, 24GB RAM, macOS 26.5.1)
Python 3.14.2, liboqs-python, Llama-3.2-1B

## Author
Venkata Vijaya Kumari D.
vijayaqa.rv7@gmail.com
