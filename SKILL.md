---
name: pt-legal-mcp-skill
description: Official Portugal (PT) legislation, multi-tier court precedent research, and citation verification skill.
version: 2.0.0
author: JurisAtlas
license: MIT
---

# Portugal Legal Research & Multi-Tier Case Law Skill (`pt-legal-mcp`)

Use this skill whenever the user asks a legal question, drafts a pleading or contract, or researches case law across any judicial instance in **Portugal (PT)**.

## Verification & Research Rules

1. **Citation Verification:** Never fabricate a statutory provision or case citation. Query `search_legislation`, `search_case_law`, `search_tiered_court_decisions`, or `verify_citation` before citing any authority (e.g., `ECLI:PT:STJ:2024:123.22.0T8LSB.L1.S1 or Diário da República`).
2. **Multi-Tier Judicial Coverage:**
   - **First Instance (Trial / Municipal / District):** 23 Tribunais Judiciais de Comarca & Tribunais Administrativos e Fiscais de Círculo (TAF)
   - **Second Instance (Cantonal / Regional / Appellate):** 5 Tribunais da Relação (Lisboa, Porto, Coimbra, Évora, Guimarães) & 2 Tribunais Centrais Administrativos (TCA Sul & TCA Norte)
   - **Supreme & Constitutional Instance:** Supremo Tribunal de Justiça (STJ), Supremo Tribunal Administrativo (STA) & Tribunal Constitucional (TC)
   - **Primary Tiered Database:** DGSI Bases Jurídico-Documentais (dgsi.pt — STJ, STA, 5 Tribunais da Relação & 2 TCA) (`http://www.dgsi.pt`)
