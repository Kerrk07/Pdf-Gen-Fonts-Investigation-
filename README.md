# PDF Font Layout Investigation

A lightweight workspace to investigate font layout and rendering in file generation. The focus is on language coverage from Chinese, Japanese, Korean (CJK) to complex text layout (CTL) scripts, and documenting when custom TTF/OTF font files are not required.

**Objectives**
- Compare layout/rendering across PDF, DOCX, and XLSX generation.
- Verify coverage for: Chinese, Japanese, Korean; Arabic, Hebrew; Indic (e.g., Devanagari, Bengali, Tamil); Thai, Khmer, and more.
- Identify when system fonts and fallbacks are sufficient versus when embedding is needed.
- Summarize trade‑offs of embedding fonts vs. relying on platform/default fonts.

**Why Not TTF/OTF (In Many Cases)**
- Office formats (DOCX/XLSX) reference fonts by family name; they do not embed fonts by default. System fonts and fallbacks often provide acceptable results and keep files small.
- Many PDF generators can subset or embed system fonts automatically; for Latin text, core PDF fonts may be enough. For CJK/CTL, we will validate whether platform fonts and shaping engines are sufficient without bundling TTF/OTF.
- Final guidance will document when embedding is still necessary (e.g., strict brand fonts, offline portability, or limited target environments).

**Planned Tests**
- Layout fidelity: kerning, ligatures, line/word breaking, hyphenation, vertical metrics.
- CJK specifics: punctuation spacing, full/half‑width handling, line wrap behavior.
- CTL specifics: Arabic shaping and RTL, Indic conjuncts/halants, Thai/Khmer line breaking.
- Mixed‑language documents to observe font fallback behavior.

**Artifacts**
- `samples/` — minimal source inputs per language/script.
- `outputs/` — generated PDF/DOCX/XLSX files for comparison.
- `scripts/` — utilities to generate files and diff outputs.
- `notes/` — findings, edge cases, and recommendations.

**Next Steps**
- Add baseline samples for CJK and CTL.
- Set up generation scripts for PDF/DOCX/XLSX.
- Record findings in `notes/` and refine guidance on avoiding TTF/OTF where feasible.

Status: Work in progress.
