# QuantRot-PQC
Quantum-inspired optimization of post-quantum cryptographic operations for secure, resource-constrained LLM KV-cache transmission.

## Research Question
Can quantum t-design unitary circuits reduce the latency and memory overhead of PQC operations (CRYSTALS-Kyber) in LLM KV-cache transmission pipelines?

## Status
Active research — targeting ArXiv submission Q3 2026.

## Approach
- Baseline: TurboQuant (Hadamard rotation + KV-cache quantization)
- Proposed: Replace Hadamard with quantum t-design unitaries (QuantRot)
- Extension: Apply t-design structure to accelerate Kyber NTT lattice operations
- Models: Mistral-7B, Phi-3-mini
- Tools: PennyLane, PyTorch, HuggingFace Transformers, liboqs

## Structure (coming soon)
- /circuits — quantum t-design circuit implementation
- /baseline — TurboQuant Hadamard reproduction
- /experiments — benchmarking scripts
- /paper — draft sections

## Author
Venkata Vijaya Kumari D | vijayaqa.rv7@gmail.com
