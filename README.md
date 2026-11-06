# Islamic Skills (IslamAI) 🕋✨
**A Tiered Architectural System for Canonical Quranic Retrieval, Morphological Precision, Tafsir Discipline, and Structural Navigation**

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Protocol](https://img.shields.io/badge/MCP-quran.ai-emerald.svg)](https://modelcontextprotocol.io)
[![vLLM](https://img.shields.io/badge/vLLM-Compatible-purple.svg)](https://vllm.ai)
[![Skill](https://img.shields.io/badge/Agent_Skill-Specification_v2-orange.svg)](skills/islamic-skills)

Islamic Skills is an open-source, production-grade agentic framework that integrates three seminal repositories:
1. **`hurmoz.git`** — Micro Linguistic Precision (Root ➔ Lemma ➔ Awzan Morphology & Concordance)
2. **`IslamAI.git`** — Macro Interpretive Depth (Selection Gate, Single/Multi-Source Tafsir & Editorial Disclaimers)
3. **`aslam.git`** — Spatial Structural Navigation (Surah Discourse Architecture & Mushaf Metadata)

Coupled with the **quran.ai Model Context Protocol (MCP)**, this framework elevates Islamic AI systems from probabilistic hallucination to verifiable, canonical truth retrieval.

---

## 🏛️ Architecture Overview

```
                               ┌────────────────────────────────────────────────┐
                               │           User / Application Prompt            │
                               └───────────────────────┬────────────────────────┘
                                                       │
                               ▼───────────────────────▼────────────────────────┐
                               │  Core Philosophy: "Canonical Or Nothing"       │
                               │  - Session Grounding Nonce Check               │
                               │  - Context-First Workflow                      │
                               └───────────────────────┬────────────────────────┘
                                                       │
         ┌─────────────────────────────────────────────┼─────────────────────────────────────────────┐
         │                                             │                                             │
         ▼                                             ▼                                             ▼
┌─────────────────────────────────┐       ┌─────────────────────────────────┐       ┌─────────────────────────────────┐
│     Layer A (hurmoz.git)        │       │     Layer B (IslamAI.git)       │       │      Layer C (aslam.git)        │
│   Linguistic & Morphological    │       │     Interpretive & Tafsir       │       │    Structural & Navigational    │
│  - Awzan Patterns               │       │  - Selection Gate Enforcement   │       │  - Discourse Architecture       │
│    (Ghafir vs Ghaffar vs Ghafur)│       │  - Single / Multi-Source Tafsir │       │  - Legal-Diplomatic Sequencing   │
│  - Lemma & Paradigm Mapping     │       │  - Classical Scholarly Corpus   │       │  - Mushaf Metadata              │
│  - Vertical Root Concordance    │       │  - AI Editorial Disclaimer      │       │    (Juz, Hizb, Ruku, Page)      │
└────────────────┬────────────────┘       └────────────────┬────────────────┘       └────────────────┬────────────────┘
                 │                                         │                                         │
                 └─────────────────────────────────────────┼─────────────────────────────────────────┘
                                                           │
                               ▼───────────────────────────▼────────────────────────┐
                               │       quran.ai MCP Tool Execution Engine           │
                               │   fetch_quran | fetch_tafsir | morphology_lookup   │
                               └───────────────────────────┬────────────────────────┘
                                                           │
                               ▼───────────────────────────▼────────────────────────┐
                               │         Canonical YAML Frontmatter Receipt         │
                               │           + Grounded Scholarly Synthesis           │
                               └────────────────────────────────────────────────────┘
```

---

## ⚡ The Four-Stage Operational Workflow

1. **Search Broadly**: Use `search_quran` or `search_tafsir` to locate thematic candidate passages.
2. **Fetch Selectively**: Shortlist 3–7 candidate verses and retrieve exact Uthmani text via `fetch_quran` / `fetch_translation` using the session nonce.
3. **Ground Deeply**: Pass through the Selection Gate by calling `fetch_tafsir` with verified mufassir editions (Ibn Kathir, al-Tabari, al-Qurtubi, al-Jalalayn, al-Sa'di).
4. **Synthesize & Disclaim**: Produce grounded answers with YAML receipts. If drawing modern analytical inferences, append the AI Editorial Disclaimer.

---

## 📦 Repository Structure

```
islamic_skills/
├── skills/
│   └── islamic-skills/
│       ├── SKILL.md                          # Anthropic / OpenAI standard skill spec
│       ├── scripts/
│       │   ├── receipt_validator.py          # Validates canonical receipts
│       │   └── quran_mcp_client.py           # Python client for MCP stdio
│       ├── references/
│       │   ├── layer_a_hurmoz_morphology.md  # Detailed morphology breakdown
│       │   ├── layer_b_islamai_tafsir.md     # Selection gate & mufassir specs
│       │   ├── layer_c_aslam_navigation.md   # Discourse architecture breakdown
│       │   └── quran_ai_mcp_spec.md          # Full MCP protocol specification
│       └── assets/
│           ├── grounding_receipt_template.yaml
│           └── system_prompt_fragment.md
├── mcp_server/
│   ├── server.py                             # Fast stdio MCP server implementation
│   └── tools/
│       ├── grounding.py                      # Nonce generation & token defense
│       ├── morphology_hurmoz.py              # Root-lemma-pattern engine
│       ├── tafsir_islamai.py                 # Multi-edition tafsir engine
│       └── navigation_aslam.py               # Discourse & metadata navigation
├── vllm/
│   ├── run_vllm_islamic_skills.sh            # vLLM launch script
│   ├── vllm_tool_config.json                 # vLLM tool calling config
│   ├── chat_template_hermes_toolcall.jinja   # Jinja2 chat template for tool calling
│   └── serve_vllm_mcp.py                     # vLLM agent proxy
├── schemas/
│   ├── openai_tools.json                     # OpenAI function calling definitions
│   ├── anthropic_tools.json                  # Anthropic Claude tool definitions
│   └── mcp_tools.json                        # Standard MCP JSON schema
├── adapters/
│   ├── openai_agent.py                       # OpenAI / vLLM client adapter
│   └── langchain_toolkit.py                  # LangChain StructuredTool wrapper
└── tests/
    ├── test_grounding_nonce.py               # Nonce & receipt test suite
    ├── test_hurmoz_morphology.py             # Layer A morphology test suite
    ├── test_islamai_tafsir_gate.py           # Layer B tafsir gate test suite
    └── test_aslam_navigation.py              # Layer C navigation test suite
```

---

## 🚀 Quickstart & Usage

### 1. Installation
```bash
git clone https://github.com/islamai/islamic-skills.git
cd islamic-skills
pip install -r requirements.txt
```

### 2. Run Test Suite
```bash
python3 -m unittest discover tests
```

### 3. Start MCP Server
```bash
python3 -m mcp_server.server
```

### 4. Serve with vLLM
```bash
bash vllm/run_vllm_islamic_skills.sh meta-llama/Llama-3.1-8B-Instruct 8000
```

---

## 📜 Canonical Receipt Example

```yaml
---
source: "quran.ai"
surah: 9
ayah: 6
arabic_uthmani: "وَإِنْ أَحَدٌ مِّنَ الْمُشْرِكِينَ اسْتَجَارَكَ فَأَجِرْهُ حَتَّىٰ يَسْمَعَ كَلَامَ اللَّهِ ثُمَّ أَبْلِغْهُ مَأْمَنَهُ"
translation_edition: "sahih-international"
translation_text: "And if any one of the polytheists seeks your protection, then grant him protection..."
tafsir_edition: "ibn-kathir"
nonce: "QAI-98A1B2C3D4"
verification_status: "canonical-verified"
---
```

---

## ⚖️ License
Apache-2.0 License. Open for scholarly research, community applications, and AI alignment.
