# Joey Victorino

I architect agentic security systems that can be audited and operated at scale. The pattern is the same whether the system is a governed private-AI platform or an incident-response tool: route work to the right model with automatic failover, let agents act only through signed tool definitions under a deny-wins policy, record every model call and tool call in an encrypted append-only log, validate claims deterministically before anyone acts on them, and retain nothing by default. A technical claim is not evidence; the code below is built so the evidence is reproducible.

## Systems

| Repo | What it proves | Status |
|---|---|---|
| [assay](https://github.com/joeyvictorino/assay) | Multi-model continuous security-validation harness: provider routing with failover and budgets, Ed25519-signed tools with a trust store, deny-wins policy engine, AES-256-GCM hash-chained audit log, zero data retention as a tested property, cross-model overlap measurement on authorized labs | in progress, public from day one |
| [tasia](https://github.com/joeyvictorino/tasia) | Fail-closed configuration review for private-AI stacks (Go); evidence never carries secret values by construction | released |
| [orbit-ir](https://github.com/joeyvictorino/orbit-ir) | Reconciles AI-agent transcripts against control-plane records; findings carry file and line references; precision and recall only when ground truth exists | v0.2.0 |
| [phylaram](https://github.com/joeyvictorino/phylaram) | Live physical-memory acquisition for Windows with byte-accurate error isolation and an independent offline verifier | alpha |

The post-quantum line in my bio refers to a peer mesh I architected that secures node-to-node WebSocket links with ML-KEM-768 key exchange and ML-DSA-65 mutual authentication, with trust-gated data transfer. I wrote that platform's public design documentation; the architecture is summarized, without naming the product, on [joeyvictorino.com](https://joeyvictorino.com).

## Benchmarks

Edge-inference numbers for small open-weight models on Apple silicon (llama.cpp tuning sweep, context-length curve, MLX comparison) will be published with raw data and regeneration scripts in `edge-inference-bench`. No numbers are quoted here until that repo contains them.

## Writing

Field notes at [joeyvictorino.com/field-notes](https://joeyvictorino.com/field-notes/).
