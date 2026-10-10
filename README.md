# Joey Victorino

I architect agentic security systems that can be audited and operated at scale. The pattern is the same whether the system is a governed private-AI platform or an incident-response tool:

- route work to the right model, with automatic failover and budgets;
- let agents act only through signed tool definitions, under a deny-wins policy;
- record every model call and tool call in an encrypted, append-only log;
- validate claims deterministically before anyone acts on them;
- retain nothing by default.

A technical claim is not evidence. Every repository below is built so the evidence can be reproduced from a clean clone.

## Systems

| Repo | What it proves | Status |
|---|---|---|
| [assay](https://github.com/joeyvictorino/assay) | Multi-model continuous security-validation harness: provider routing with failover and budgets, Ed25519-signed tools verified against a trust store, a deny-wins policy engine, an AES-256-GCM hash-chained audit log, deterministic checkers that mark each finding validated, refuted or theorized, and zero data retention as a tested property. 17 architecture decision records. | v0.3.0 released; CI runs it against three authorized labs. No multi-model result published yet |
| [edge-inference-bench](https://github.com/joeyvictorino/edge-inference-bench) | Reproducible method for benchmarking small open-weight models on Apple silicon: llama.cpp tuning sweep, context-length curve, MLX comparison, with the measurement conditions recorded beside every result | Method and scripts published; no results yet |
| [tasia](https://github.com/joeyvictorino/tasia) | Fail-closed configuration review for private-AI stacks (Go); evidence never carries secret values by construction | v0.1.1 |
| [orbit-ir](https://github.com/joeyvictorino/orbit-ir) | Reconciles AI-agent transcripts against control-plane records; findings carry file and line references; precision and recall only when ground truth exists | v0.2.0 |
| [phylaram](https://github.com/joeyvictorino/phylaram) | Live physical-memory acquisition for Windows with byte-accurate error isolation and an independent offline verifier | alpha |

### Where to start in assay

- Signed tools and the trust store: [`internal/toolsig/toolsig.go`](https://github.com/joeyvictorino/assay/blob/main/internal/toolsig/toolsig.go)
- Deterministic validation of findings: [`internal/validate`](https://github.com/joeyvictorino/assay/tree/main/internal/validate)
- Transcript reconciliation: [`internal/reconcile/reconcile.go`](https://github.com/joeyvictorino/assay/blob/main/internal/reconcile/reconcile.go)
- Design decisions: [`docs/adr`](https://github.com/joeyvictorino/assay/tree/main/docs/adr)
- Committed runs, each linked to the CI run that produced it: [`results`](https://github.com/joeyvictorino/assay/tree/main/results)

The post-quantum line in my bio refers to a peer mesh I architected that secures node-to-node WebSocket links with ML-KEM-768 key exchange and ML-DSA-65 mutual authentication, with trust-gated data transfer. I wrote that platform's public design documentation; the architecture is summarized, without naming the product, on [joeyvictorino.com](https://joeyvictorino.com).

## Standards work

- **volatility3** ([PR #2045](https://github.com/volatilityfoundation/volatility3/pull/2045), open): makes linked-list walks report an unreadable node instead of silently returning a shorter list. Forensic parsers should fail closed.
- **Signed tool definitions for MCP** ([draft](https://github.com/joeyvictorino/assay/blob/main/docs/proposals/signed-tool-manifests-for-mcp.md)): RFC 8785 canonical signing, a trust-store key id, and four verification reason codes, with assay as the reference implementation. A draft for discussion, not an adopted proposal.

## Writing

Field notes at [joeyvictorino.com/field-notes](https://joeyvictorino.com/field-notes/). Start with:

- [A technical claim is not evidence](https://joeyvictorino.com/field-notes/a-technical-claim-is-not-evidence)
- [Agents act only through signed tools](https://joeyvictorino.com/field-notes/agents-act-only-through-signed-tools)
- [Zero data retention is a test, not a sentence](https://joeyvictorino.com/field-notes/zero-data-retention-is-a-test-not-a-sentence)
- [A model's score for its own work is not a result](https://joeyvictorino.com/field-notes/a-models-score-for-its-own-work-is-not-a-result)
