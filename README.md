**OWASP AI Attack Surface Framework (AI-AS-FW)**
(Alternative names to avoid confusion with “ASM” / “Attack Surface Detector”: **AI Attack Surface Mapping**, **AI Surface Atlas**, **AI System Attack Surface Guide**.)

## Mission

Provide a **standard, repeatable, vendor-neutral method** to identify, classify, and document the **attack surfaces of AI systems** across common architectures (LLM apps, RAG, agentic AI, classical ML pipelines), enabling consistent threat modeling, control selection, and security testing.

## Vision

Make AI security assessments faster and more consistent by standardizing the **system decomposition step**: the “map” that connects architectures to risks, requirements, and tests.

## Target audience

* AppSec / Product Security engineers
* Security architects and threat modelers
* ML engineers / LLM app developers
* Red team / purple team
* SOC / detection engineering (secondary: telemetry mapping)
* GRC teams who need “what to ask for” based on architecture

## Problem statement

Organizations adopt AI systems faster than they can model risk. Existing guidance often jumps straight to “Top 10 risks” or “control checklists,” but teams lack a shared method to enumerate:

* AI-specific components (model gateway, vector DB, prompt store, tool router, memory, training pipeline)
* Trust boundaries (user ↔ app ↔ model provider ↔ tools ↔ data)
* Entry points and abuse channels (prompt, retrieved content, tool outputs, model supply chain)

This project standardizes that mapping so other OWASP resources can be applied accurately.

## Scope (in-scope)

1. **Taxonomy** of AI attack surfaces (components, interfaces, data flows, trust zones)
2. **Reference architectures / patterns** with attack-surface decompositions, e.g.:

   * LLM API wrapper
   * RAG with vector DB + connectors
   * Agentic AI with tools / function calling
   * Fine-tuning pipeline + model registry
   * Multi-tenant inference service
3. **Trust boundary + data flow templates** (C4-style, DFD-style)
4. **Crosswalk mappings**:

   * Surfaces ↔ OWASP Top 10 for LLM Apps / ML Security Top 10 / MCP Top 10 (where relevant) ([OWASP Foundation][1])
   * Surfaces ↔ AISVS / LLMSVS / MLSVS control areas ([OWASP Foundation][6])
   * Surfaces ↔ OWASP AI Testing Guide layer categories (App/Model/Infra/Data) ([OWASP Foundation][7])
   * Optional: Surfaces ↔ AIBOM fields (as an input/output integration point) ([Owaspaibom][9])
5. **Attack Surface Review methodology** (a checklist/process to run in design reviews)

## Out of scope (non-goals)

* A new “Top 10” list (we map to existing ones)
* A full verification standard (we map to existing SVSs)
* Vendor/product comparisons or endorsements
* Publishing weaponized exploit kits or step-by-step offensive playbooks
* Replacing AIBOM (we integrate, not duplicate)

## Deliverables

**Release v0.1 (MVP)**

* AI attack surface taxonomy (v0.1)
* 3 reference patterns + diagrams + “surface cards”
* Crosswalk: surfaces → (LLM Top 10 + ML Top 10) mapping
* Attack Surface Review worksheet (Markdown + optional spreadsheet)

**Release v0.2**

* Add agentic AI + tool ecosystem pattern
* Crosswalk additions: AISVS/LLMSVS/MLSVS
* “Telemetry suggestions” appendix (what to log per surface)

**Release v1.0**

* Pattern library ≥ 10 common architectures
* Stable taxonomy + versioned PDF export
* Community-maintained mapping tables and change log

## Success metrics

* Referenced by other OWASP AI projects (cross-links)
* Used as a standard input in AI threat modeling workshops
* Community contributions: new patterns + mapping PRs
* Adoption: downloads/stars/citations in talks or blogs

## Collaboration plan (alignment with OWASP ecosystem)

* Coordinate with OWASP GenAI Security Project for GenAI/LLM patterns ([OWASP Gen AI Security Project][2])
* Coordinate with OWASP AI Testing Guide for test-case linkage ([OWASP Foundation][7])
* Coordinate with AISVS / LLMSVS / MLSVS maintainers for mapping validation ([OWASP Foundation][6])
* Coordinate with OWASP AIBOM for supply chain surface definitions ([Owaspaibom][9])
* Reference OWASP MCP Top 10 where MCP servers/connectors appear as a surface ([OWASP Foundation][3])

## Governance

* Project leads + maintainers listed in README
* Monthly community call (notes published)
* PR review rules (2-approver for taxonomy changes)
* Clear versioning (SemVer-like for taxonomy + mappings)

## Licensing

MIT

