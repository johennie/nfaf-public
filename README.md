# NFAF: Narrative Flattening Analysis Framework (0.5.0)

**Author:** Johennie Helton
**Status of This Document:** Working Draft Specification (v0.5.0)
**Date:** September 2025

## 1. Status of This Document 

This document is a **Working Draft Specification** of the Narrative Flattening Analysis Framework (NFAF). It is released for academic and research purposes and may be updated, replaced, or obsoleted at any time prior to version 1.0.

This specification addresses AI-mediated narrative flattening. Domain-emergent flattening is acknowledged but out of scope (see §10).

NFAF v0.5 presents a systematic framework derived from theoretical foundations and observed patterns in AI-mediated transformations. Broader empirical validation across corpora, languages, and domains, as well as eventual systematic implementations, remain priorities for future versions.

**Purpose**
- Defines terminology, analytic stages, and rubric dimensions for detecting **narrative flattening** in AI-mediated transformations (translation, summarization, rewriting, and related processes).
- **NFAF** is non-prescriptive: it separates detection from judgment.
- Intended for use in research, teaching, and non-commercial prototyping.
- White papers, case studies, and domain-specific applications **SHOULD** cite this specification but **MAY** extend it with illustrative examples.

**Conformance**
An implementation conforms to this specification if it:
1. Applies at least one rubric dimension (§7) to a source/target narrative pair.
2. For conformance with this specification, implementers MUST carry out Stages 1–5 and 7 as defined in §6, *adapting them as needed for their domain.* Stage 6 is REQUIRED only in high-stakes contexts.
3. Produces an alignment manifest (§6.3) recording omissions, additions, or drift.
4. Discloses observed flattening indicators (§5.9).

Partial conformance **MAY** be declared when only a subset of stages or rubric dimensions is implemented, provided the deviation is explicitly documented.

Keywords **MUST, MUST NOT, SHOULD, SHOULD NOT,** and **MAY** are to be interpreted as described in [RFC 2119]. These directives specify how analysts should apply the framework consistently, not whether observed changes are desirable or problematic, such evaluations remain domain-specific.

**Intellectual Property Notice**
NFAF is published as the **pre-existing intellectual property of Johennie Helton.** This specification is provided for research and citation purposes only.
- No commercial implementation rights or co-ownership are granted. Any commercial use or integration REQUIRES prior written permission from the author.
- For non-commercial research prototypes, users **MUST** cite this specification and **MUST** disclose any deviations.
- Redistribution **SHOULD** preserve version information (v0.5.0) and persistent identifiers (DOI, ORCID).

## 2. Citation
If you reference this framework in research or teaching, please cite as follows:

Helton, J. (2025). NFAF: Narrative Flattening Analysis Framework (v0.5.0). Zenodo. https://doi.org/10.5281/zenodo.16885076

*The example above is formatted in APA style. Researchers MAY adapt to MLA, Chicago, or other disciplinary standards, provided the DOI is preserved.*

### Persistent Identifiers

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.16885076.svg)](https://doi.org/10.5281/zenodo.16885076)  
[![ORCID](https://img.shields.io/badge/ORCID-0009--0003--2175--3239-green?logo=orcid)](https://orcid.org/0009-0003-2175-3239)

**DOI:** 10.5281/zenodo.16885076  
**ORCID:** 0009-0003-2175-3239

---

## 3. Abstract 
**NFAF (Narrative Flattening Analysis Framework)** is a modular method for detecting and characterizing *narrative flattening* across AI-mediated transformations, including translation, summarization, rewriting, and related processes. *Narrative flattening* refers to the convergence of AI-generated text toward standardized patterns that affect stylistic voice, idiomatic texture, and cultural specificity. It manifests as *erosion* (loss of distinctive semantic, stylistic, cultural, or affective features) or *inflation* (addition of generic elements that override the original signal).
A central mechanism is the *hidden pivot:* an implicit or explicit relay language through which AI systems may route mediations, with outputs that may show signs consistent with hidden-pivot processing. *Narrative flattening* is treated here as an empirical trace of hidden pivot effects, visible in measurable erosion of cadence, idiom, and cultural register. 
**NFAF** defines analytic stages and rubric dimensions that provide a reproducible basis for documenting and comparing flattening across corpora and domains. Grounded in narratology, translation theory, digital humanities, and NLP, **NFAF** offers a replicable way to analyze whether, where, and how AI outputs converge toward hidden pivots, and what nuance is lost in the process.

| **Flattening category**     | **Indicators**                                                                                                                                                                                                        |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Structural & Alignment**  | - Structural drift <br/>- Segment Omission <br/>- Dialogue Flattening <br/>- Event Compression/Collapsing <br/>- Discourse Link Collapse                                                                              |
| **Cadence**                 | - Homogenized cadence <br/>- Loss of prosodic markers / flattened pacing                                                                                                                                              |
| **Stylistic**               | - Loss of idiomatic expressions <br/>- Quotation loss / paraphrase masking <br/>- Neutralized or homogenized register                                                                                                 |
| **Semantic & Interpretive** | - Semantic drift <br/>- Neutralization of emotional tone <br/>- Over-generalization <br/>- Premature disambiguation (over-specificity) <br/>- Canonical pull* <br/>- Domain transfer <br/>- Back-translation mismatch |

_Table 1. Categories of narrative flattening and their indicators._ 
*Canonical pull = tendency of AI systems to gravitate toward standardized or widely circulated formulations, overriding text-specific variation.*


This specification defines *flattening* in two distinct contexts: 
- (a) *AI-mediated flattening,* the primary focus of NFAF, where narrative distinctiveness is eroded through translation, summarization, rewriting, or related processes performed by artificial intelligence 

- (b) *domain-emergent flattening,* recognized but out of scope here, where flattening arises from practices internal to specific fields (e.g., journalistic false balance, legal compression of testimony, political simplification). This document addresses (a). For discussion of (b), see §10.

---

## 4. Introduction
The **Narrative Flattening Analysis Framework (NFAF)** provides a modular framework to detect, describe, and compare the loss, convergence, or homogenization of cultural, emotional, and stylistic features *if present* in narratives transformed by machine mediation such as translation, summarization, rewriting, or other processes. 

**NFAF** is not domain-specific. It contains a common theoretical and methodological core while deliberately avoiding prescriptive thresholds or universal acceptability criteria. A reduction in variance that signals voice loss in literature, for example, may constitute acceptable compression in legal summarization. Interpretation must therefore be guided by domain expertise, use case requirements, and stakeholder values. For example, literary analysis may prioritize voice preservation and cultural authenticity; legal applications may emphasize semantic precision and structural fidelity; journalism may balance accessibility with source integrity. This modularity enables specialized implementations (e.g., Literature, Law) while maintaining consistent analytical stages and ethical principles.

**NFAF** recognizes two sources of flattening: those originating from AI mediation and those arising from domain emergence. **NFAF** applies to *AI-mediated flattening,* where narrative distinctiveness is eroded through artificial intelligence processes. *Domain-emergent flattening,* where flattening arises from professional practices themselves (e.g., journalistic false balance, legal compression of testimony, political simplification) is out of scope for v0.5.0 but is addressed as a possible extension in §10.

AI-mediated transformations often reflect algorithmic optimization toward pivot-language outputs that may appear universally fluent but are less contextually situated. **NFAF** positions these effects as systematic convergence patterns observable in outputs, regardless of the internal architecture of the model. **NFAF** treats such convergence as an empirical trace of **hidden pivot** effects, consistent with relay-language processing, whether implicit in training distributions or explicit in chained mediations.

Comparable critiques of homogenization can be found across fields. In translation studies, (Berman 2000) catalogued systematic distortions in his negative analytic, (Venuti 1995) emphasized the risks of domestication, and (Spivak 2000) highlighted the ethical duty to preserve singular voice. Recent work on machine translation reinforces these concerns: (Schneider 2022) identifies English functioning as a hidden pivot in digital multilingualism, and (Vieira 2023) highlights how infrastructures shape translation practices and reinforce convergence. In digital humanities and media theory, (Drucker 2014) critiques assumptions of interpretive neutrality, echoing concerns about voice and context.

**NFAF** complements rather than replaces quantitative metrics such as BLEU or ROUGE. It asks *different questions entirely,* focusing on dimensions of meaning preservation that surface-level similarity measures cannot capture. However, **NFAF** does not claim universal applicability: its categories derive primarily from Western narratology, translation studies, and journalistic and legal traditions, and may need extension or adaptation in diverse cultural and disciplinary contexts.

The following sections define **NFAF**’s key concepts and analytic dimensions, outlining the indicators and stages that make flattening measurable across different domains and mediation types.

**Current focus:** Applying **NFAF** to **narrative voice in literary text,** with emphasis on preserving cultural and emotional signals in AI-mediated transformation. Sections §7–§8 are illustrative; only §7 provides worked evidence in v0.5.0. The framework is grounded in both theoretical and observed patterns; broader empirical validation across corpora, languages, and domains, as well as potential systematic implementations, remain priorities for future versions.


_Note: NFAF is published as pre-existing intellectual property of Johennie Helton. This specification is provided for research and citation purposes only. **No commercial implementation rights or co-ownership are granted.** For non-commercial research prototypes, cite this spec and disclose deviations._

---

## 5. Definitions

*Note:* Keywords **MUST, MUST NOT, SHOULD, SHOULD NOT,** and **MAY** are to be interpreted as described in [RFC 2119]. These directives specify how analysts should apply the framework consistently, not whether observed changes are desirable or problematic, such evaluations remain domain-specific.

```
NFAF analyzes output patterns, not internal mechanisms. When we describe 'pivots' or 'convergence effects,' we refer to observable regularities in transformed texts, not claims about how AI systems internally process information.
```

### 5.1 Narrative (adapts)
A **narrative** is any structured account of events, experiences, or arguments (whether linguistic, visual, or multimodal) that conveys meaning through deliberate sequencing, framing, or voice. This definition *adapts* broad narratological accounts (Genette 1980; Bal 1985; Ryan 2004), treating discourse and framing as central to meaning.
- Narratives **MUST** be analyzed with attention to distinctive signals such as voice, style, cultural cues.  
- Narratives **MAY** be literary, journalistic, scientific, legal, cultural, or digital-born in form.  
- Narratives **MAY** be linear or nonlinear, explicit or implicit, but are always shaped by formal, stylistic, and perspectival choices tied to context.  
- Any mediation or transformation of a narrative **MUST** respect the integrity of these signals. The source **SHOULD** remain accessible alongside the modified version to prevent erasure of voice or context.  

In this specification, narrative is considered primarily in the context of **AI-mediated transformations** (§6). Other forms of narrative reduction or simplification are acknowledged but treated separately under **domain-emergent flattening** (§10).

---

### 5.2 Narrative Flattening (defines)
**Narrative flattening** is defined by this specification as the reduction, erosion, or homogenization of a narrative’s distinctive signals (its voice, style, cultural cues, or emotional intensity) through processes of transformation or mediation. Note that when texts go through multiple AI mediations, narrative flattening effects might compound.

Comparable critiques are found in translation theory (Berman 1985; Venuti 1995; Spivak 2000), where mediation reshapes voice and culture. **NFAF** reframes these concerns as reproducible, algorithmic effects of AI mediation, echoing computational linguistics on semantic shift (Hamilton et al. 2016) and digital humanities critiques of interpretive neutrality (Drucker 2014). 

Whether such reduction constitutes a problem depends on domain context and transformation goals; **NFAF** provides tools for detection and categorization, not evaluation.


### 5.3 Flattening 
**Flattening** is the systematic *reduction of variance in narrative voice* across transformations and can be observed in several recurrent forms. Forms of flattening describe recurrent ways narrative distinctiveness is reduced during mediation:
- **Erosion:** Loss or weakening of key narrative elements, such as semantic nuance, stylistic rhythm, cultural references, or affective tone.
- **Inflation:** Insertion or exaggeration of generic features absent from the source.
- **Speculative Addition/Inference:** The introduction of details absent from the source, often drawn from the training data on canonical texts, precedent cases, or analogous contexts. This can prematurely resolve ambiguities in a way not supported by the original source.
- **Omission/Compression (context-dependent):** Removal or condensation of source segments (sentences, paragraphs, dialogue, quotations). In summarization, omission may be expected but should always be signaled to preserve accountability; in translation or rewriting, omission of substantive content constitutes flattening unless explicitly documented.

Whether by erosion, inflation, inference, or omission, the result is outputs that are more standardized, less contextually situated, and ultimately less distinctive at the cost of human voice and cultural nuance. The effects appear across domains: in literature as homogenized rhythm or reduced figurative density; in journalism as genericized news summaries; in law as legally imprecise translations.

#### 5.3.1 Contexts of flattening  
**NFAF** distinguishes two contexts:
- **AI-mediated flattening (normative focus):**  
  Reduction of distinctiveness caused by artificial intelligence systems during translation, summarization, rewriting, or related transformations.  
  - Analysts **MUST** evaluate AI outputs against the source narrative for losses of cadence, voice, cultural register, and other rubric dimensions (§7).  
  - AI-mediated flattening **MUST** be documented using the analytic stages (§6).  
  - Results **SHOULD** disclose both explicit omissions and subtle homogenizations.

- **Domain-emergent flattening (acknowledged, out of scope in v0.5.0):**  
  Reduction of distinctiveness arising from institutional or professional practices (e.g., journalistic false balance, legal compression of testimony, political simplification).  
  - Domain-emergent flattening is **recognized** but **MUST NOT** be treated as normative in v0.5.0.  
  - Future extensions (e.g., NFAF-J for Journalism, NFAF-L for Law, NFAF-P for Politics) **MAY** adapt the framework to these contexts (§10).

**Scope of v0.5.0**  
Unless explicitly stated otherwise, *narrative flattening* in this specification refers to **AI-mediated flattening.**

---

### 5.4 Pivot
In **NFAF**, a **pivot** is any intermediate form: linguistic, cultural, or semiotic, through which mediated processes converge.

NFAF distinguishes two key dimensions:
- **Centroid Pivot** (§5.4.2): the generalized phenomenon of convergence toward dominant defaults. Within this, **hidden pivot** (§5.4.1) designates cases where convergence toward an unobserved intermediary is inferred from outputs. Hidden pivot may manifest in both **relay** (multi-step) and **single-step** mediation.
- **Pivot Form** (§5.4.2): the specific centroid defaults (language, culture, register) that shape mediation outcomes.

```text
Pivot (umbrella category)
├── Centroid Pivot = generalized convergence toward dominant defaults
├    └── Hidden Pivot = inferred convergence toward an unobserved intermediary
├    ├── Relay (multi-step mediation)
├    └── Single-step (direct mediation with inferred centroid pull)
└── Pivot Form = the specific centroid defaults (language + culture + register) shaping mediation
```
*Figure 1. Pivot hierarchy.*


**Adaptation note:** This extends the notion of a *pivot language* in translation studies and NLP, generalizing it to multimodal, cross-domain contexts and explicitly including cultural register.

```text

    Input (language or modality)
          ↓
       [Pivot stage: single-step or relay]
          ↓
    Pivot Form (linguistic + cultural attractor)
          ↓
    Output (language or modality)

* Illustrative schematic only; not a claim about system internals.
```

*Figure 2. General pivot schematic.*


#### 5.4.1 Hidden Pivot (adapts)
The term **hidden pivot** originates in translation studies, where English often functions as an invisible relay in multilingual systems (Schneider 2022; Vieira 2023). In **NFAF**, a **hidden pivot** is defined more broadly as a subtype of **centroid pivot,** identified when convergence toward an unobserved intermediary can be inferred from outputs.

In **NFAF**, hidden pivot operates as an interpretive lens for diagnosing convergence patterns, without presupposing a single causal mechanism. Such patterns may arise from relay processing, training data dominated by English, architectural constraints favoring English-like structures, or algorithmic choices (e.g., English as development and evaluation default).

Whereas in translation studies **hidden pivot** typically denotes a processing mechanism, in **NFAF** it denotes an *output pattern:* a way of reading systematic convergence without requiring knowledge of its source. The practical effect is that outputs bear the texture and influence of a centroid pull toward a pivot form: in many cases, English language and globalized cultural defaults.

Hidden pivots may appear in two forms: *single-step* and *relay*.
- A **single-step pivot** occurs when only the final output is visible but carries traces of an intermediate attractor.  
- A **relay pivot** occurs when intermediate outputs reveal the pivot explicitly.  

Empirical studies provide evidence that non-English to non-English translations often carry Anglicized traces, consistent with **hidden pivot** effects:
- *FR→ES (Vanmassenhove & Shterionov 2019):* Neural MT outputs exhibit reduced lexical richness, shorter clauses, and neutralized register, features aligned with English stylistic defaults, despite English not being source or target.
- *FR→PT, ES→PT (Torres & Ramos 2018):* Portuguese translations display overuse of Anglicized terminology and phraseology in contexts where Romance-native equivalents exist.
- *IT↔ES, FR↔ES, PT↔FR (Popović et al. 2016):* Documented “translationese” effects of simplification and normalization consistent with English-driven training bias.

These findings support the inference that English operates as a hidden pivot. **NFAF** treats such convergence as an empirical trace of hidden pivot processing: detectable in outputs even when English is neither the input nor the output language.

#### 5.4.2 Centroid Pivot (defines; generalizes)
**Centroid Pivot (CP)** is a conceptual model coined in this specification to generalize the **hidden pivot** beyond multilingual translation, modeling convergence toward central forms in any modality. That is, **CP** denotes the systematic convergence of mediated outputs toward a culturally or statistically central form, regardless of domain or modality.
* Hidden pivots are a specific linguistic manifestation of CP.
* CP applies equally to text, visual, musical or other semiotic systems, where convergence toward dominant defaults can be observed.
* CP is not a claim about model architecture; it is an interpretive framework derived from regularities in outputs.
* CP **MUST NOT** be assumed uniform: different systems may exhibit different convergence patterns, depending on training distributions.

#### 5.4.3 Pivot Form (defines)
A **Pivot Form** is the specific language + cultural register that functions as the attractor in a given mediation.
* Pivot Forms are **training-data dependent** and system-specific.
* They may differ across models.
* In relay scenarios, each system may apply its own Pivot Form, and may produce layered or compounded flattening.

```text
   Example: P1 = Internet English + globalized culture; P2 = Mandarin + Chinese digital culture.

    Model A (Pivot Form P1) FR → [P1] → PT 
	+ 
	Model B (Pivot Form P2) PT → [P2] → ES
	
- Model A aligns FR to Pivot Form P1 (Internet English + culture).
- Model B aligns PT to Pivot Form P2 (Mandarin + Chinese culture).
- ES shows traces of both P1 and P2.

* Relay pivots illustrate system-specific convergence; variation reflects training data differences, not uniform architecture.
```

*Figure 3. Multi-system relay pivot (distinct Pivot Forms).*


**Directives**
* Analysts **SHOULD** document observed Pivot Forms descriptively (e.g., ‘Internet English + globalized culture’), not as fixed taxonomies.
* Analysts **MUST** treat pivot effects as output-based inferences, not assumptions about system internals.
* Identification of pivots **MAY** rely on observable regularities, whether or not intermediate outputs are visible.
* Pivot Forms **MUST NOT** be assumed neutral or universal; they may reflect systemic pulls toward dominant defaults.
* CP **MUST NOT** be assumed identical across systems; variation is expected and should be documented.

---

### 5.5 Voice & Cadence Metrics (adapts)
**Voice & Cadence Metrics** are quantitative and qualitative measures used to assess a text’s stylistic rhythm, pacing, and intensity, specifically to determine whether its narrative rises and falls are preserved during transformation. This definition adapts methods from stylistics (Leech & Short 1981), computational authorship attribution (Burrows 2002), and stylometric analysis (Stamatatos 2009) to the context of AI-mediated transformation.
- Metrics are descriptive indicators of variation and distinctiveness; they do not prescribe universal thresholds of acceptability.
- Because cadence conveys meaning, any reduction in rhythm, figurative density, or stylistic modulation **MUST** be recognized as flattening rather than “clarification.”  
- Analysts **MUST** document cadence shifts observed across aligned segments (§6).  
- Metrics **MAY** include:
	- Structural indicators: sentence length variance, clause complexity (e.g., prose, journalism).
	- Stylistic indicators: figurative density, idiomatic clusters (e.g., metaphor clusters in literary style).
	- Rhythmic indicators: punctuation-driven pacing, repetition, emphasis (e.g., legal clauses, journalistic headlines).
	- Dialogic/prosodic indicators: turn-taking, speech markers (e.g., emphasis, turn-taking in poetry or conversation).

Voice & Cadence Metrics provide the primary diagnostic layer for detecting loss of stylistic distinctiveness. They are descriptive of **surface outputs**, not claims about system internals; they can be observed and documented even when underlying model pathways remain unknown.

---

### 5.6 Drift (adapts)
**Drift**, in **NFAF**, refers to the systematic shifts—whether intentional or emergent, that arise when a narrative undergoes transformation. Drift alters either the scaffold (structure and discourse relations) or the semantics (meaning and resonance).

Within **NFAF**, drift is a descriptive category: it captures shifts in scaffold or semantics introduced by mediation. Some drifts contribute to flattening (§5.3), while others reshape structure or meaning without necessarily diminishing voice.

Drifts may be identified as structural or semantic; however, most transformations can be examined through both lenses. Researchers are encouraged to adopt the lens most relevant to their question and corpus.

#### 5.6.1 Structural Drift
**Structural Drift** refers to changes in the narrative’s scaffold: the arrangement of segments, discourse relations (contrast, cause, elaboration), speaker turns, or quoted material.  
- Analysts **MUST** document structural drift whenever scaffolding is altered without disclosure.  
- Structural drift **MAY** manifest as:  
  - **Segment Omission:** Missing dialogue, attributions, or text (null alignment).  
  - **Dialogue Flattening:** Removal of speaker attributions or turns.  
  - **Event Collapsing:** Fusion of steps that are meaningful to the narrative.  
  - **Inflation (structural):** Addition of dialogue or attributions that alter discourse framing.  

This category resonates with work on discourse structures and relations (Mann & Thompson 1988; van Dijk 2008).

#### 5.6.2 Semantic Drift
Semantic Drift refers to systematic or cumulative changes in meaning between a source and transformed text. Surface fidelity alone is insufficient; analysts **MUST** document hidden shifts so that ambiguity and nuance are not silently overwritten.  
- Semantic drift **MAY** manifest as:  
  - **Lexical Drift:** Substitution, loss, or generalization of specific word choices.  
  - **Syntactic Drift:** Shifts in sentence structure that alter emphasis or rhythm.  
  - **Pragmatic Drift:** Changes to implied meaning, tone, or cultural resonance.  
  - **Inflation (semantic):** Introduction of new propositional content absent from the source.  

This notion aligns with linguistic theories of semantic change and with Digital Humanities accounts of interpretive “drift” in computational reading (Ramsay 2011; Jockers 2013). NFAF applies it specifically to shifts introduced by AI mediation.

#### 5.6.3 Taxonomy Diagram

```text
                 ┌───────────────┐
                 │     Drift     │
                 └───────┬───────┘
                         │
         ┌───────────────┴───────────────┐
         │                               │
 ┌───────▼───────┐               ┌───────▼───────┐
 │ Structural    │               │ Semantic      │
 │ Drift         │               │ Drift         │
 │ (scaffold)    │               │ (meaning)     │
 └───────┬───────┘               └───────┬───────┘
         │                               │
  - Segment omission              - Lexical drift
  - Dialogue flattening           - Syntactic drift
  - Event collapsing              - Pragmatic drift
  - Inflation (structural)        - Inflation (semantic)  
```
*Figure 4 Taxonomy of drift in NFAF (structural vs semantic).* 


**Normative scope:** Both structural and semantic drift compromise narrative fidelity. Analysts **MUST** distinguish between them: structural drift alters scaffold and discourse relations, while semantic drift alters meaning and resonance.

---

#### 5.7 Narrative alignment (adapts)
**Narrative alignment** is adapted in NFAF to mean the segment- or unit-level mapping between a source narrative and its transformed version. Alignment enables side-by-side analysis and is a prerequisite for identifying omissions, additions, or shifts in meaning. 

- Analysts **MUST** perform alignment when evaluating AI-mediated transformations. Without such mapping, flattening may occur invisibly.  
- Alignment **MUST** preserve transparent traceability between source and output segments, thereby maintaining the integrity of the source narrative.  
- Alignment **MAY** be implemented using manual annotation, computational tools, or hybrid methods, provided the mapping is explicit and reproducible.  
- Comparable practices include parallel corpora in translation studies, alignment tools in NLP (Gale & Church 1993), and text comparison methods in law, journalism, and scientific abstracts.  

In **NFAF,** **alignment** is not only a methodological step but a humanistic accountability tool. It ensures that mediated texts remain anchored to their originals, preventing silent erasure of voice or context.

```
    Source Narrative     →     Transformed Narrative
    [Segment A] --------→ [Segment A’]
    [Segment B] --------→ [Segment B’]
    [Segment C] --------→ (omitted)
    [Segment D] --------→ [Segment D + added material]
    
    Alignment reveals omissions, additions, and shifts
```

*Figure 5. Alignment schematic. Alignment exposes divergences between source and transformed narratives.*


---

### 5.8 Signal Preservation (adapts)
**Signal preservation** is adapted in NFAF to mean the degree to which a narrative’s core elements - tone, imagery, prosody, and culturally specific forms - are retained during transformation. Preservation is a normative requirement: losses **MUST** be made visible and attributable to the mediation process.

- Analysts **MUST** disclose any loss of narrative signals so that readers can evaluate the meaning and integrity of the transformed text relative to its source.  
- Preservation **MUST** include both stylistic signals (e.g., tone, imagery, prosody, cultural registers) and structural signals (e.g., speaker turns, quotations, paragraphing).  
- The undocumented loss of these signals **MUST** be treated as flattening.  
- Preservation **MAY** be partial, but omissions or compressions **MUST** be documented as such.  

Signal preservation applies across domains, whether in literary rewriting, journalistic summarization, legal translation, or scientific abstraction. Without explicit preservation, flattening occurs invisibly, erasing both context and accountability.

Comparable concerns appear in archival science (provenance, integrity) and information theory, but NFAF repositions them around narrative voice, cultural register, and emotional resonance.

---

### 5.9 Flattening Indicators (defines)
**Flattening indicators** are defined in NFAF as reusable signs that a narrative’s distinctiveness has been reduced during an AI-mediated transformation. Their presence serves as a red flag, signaling potential erasure or overwriting of cultural and emotional meaning, and may necessitate human review. 
- Indicators are **observable symptoms**.  
- **Drift (§5.6)** names types of change; indicators operationalize these shifts for detection.  
- Analysts **MUST** document flattening indicators whenever they appear.  
- Indicators **SHOULD** be evaluated in relation to alignment (§5.7) and signal preservation (§5.8).  
- **NFAF** should be understood as a located framework, reflecting particular theoretical traditions. Its categories may not map cleanly onto all cultural or narrative systems.

#### 5.9.1 Qualitative indicators

##### 5.9.1.1 Structural & Alignment Indicators
- **Structural drift**  
- **Segment omission:** unmatched source segments (sentences/paragraphs) in alignment.  
- **Dialogue flattening:** removal of quoted speech or speaker attributions; monologizing multi-turn scenes, i.e., reducing polyphonic scenes to a single speaker voice.
- **Event collapsing:** fusing discrete actions or time steps into generic summaries.  
- **Discourse link collapse:** loss of explicit connectives (“however,” “therefore”), erasing contrast or causality.  

##### 5.9.1.2 Cadence Indicators
- **Homogenized cadence:** loss of rhythm, irony, suspense, or lyrical quality.  
- **Loss of prosodic markers/flattened pacing:** reduced variance in sentence length or paragraph flow; disappearance of punctuation or figurative clusters that carry rhythm.  

##### 5.9.1.3 Stylistic Indicators
- **Loss of idiomatic expressions:** unique idioms replaced with generic phrases.  
- **Quotation loss / paraphrase masking:** quotes replaced with unmarked paraphrase that shifts stance or intensity.  
- **Neutralized register:** distinctive voice features smoothed into generic phrasing.  

##### 5.9.1.4 Semantic & Interpretive Indicators
- **Semantic drift**  
- **Neutralization of emotional tone:** transformation of emotions into neutral reporting.  
- **Over-generalization:** replacement of specific cultural markers with universal terms.  
- **Premature disambiguation/over-specificity:** unwarranted resolution of ambiguity where the source permits multiple interpretations.  
- **Canonical pull:** convergence toward widely circulated formulations or precedent versions rather than the given source.  
- **Domain transfer:** insertion of terminology from similar but non-identical contexts.  
- **Back-translation mismatch:** apparent source fidelity that, upon back-translation, reveals lexical or collocational drift not licensed by the source (heuristic red flag, not proof).  

The following table lists the **qualitative indicators of flattening**.  
These are cues you can notice just by **reading side-by-side**: something missing, something dulled, or something added that shifts the voice.  
Use this as a **checklist**: scan the source and mediated text, tick off any indicators you spot, and then note which flattening form they belong to.

| **Flattening Form (§5.3)** | **Indicator (§5.9.1)**                  | **Description**                                                                             |
| -------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------- |
| **Erosion**                | **Loss of idiomatic expressions**       | Colorful sayings are replaced with plain phrases.                                           |
| **Erosion**                | **Neutralized register**                | Distinctive voice or style is smoothed into generic, neutral language.                      |
| **Erosion**                | **Neutralization of emotional tone**    | Strong emotions are toned down into milder, neutral wording.                                |
| **Erosion**                | **Loss of prosodic markers**            | Rhythm and pacing cues (like dashes, ellipses, lyrical flow) are stripped away.             |
| **Erosion**                | **Semantic drift**                      | The meaning shifts subtly away from the source text.                                        |
| **Erosion**                | **Over-generalization**                 | Specific cultural details are replaced with vague or universal terms.                       |
| **Inflation**              | **Quotation loss / paraphrase masking** | Direct quotes are turned into indirect paraphrases, often padded with extra words.          |
| **Inflation**              | **Event collapsing**                    | Several distinct actions or events are merged into one generic summary.                     |
| **Inflation**              | **Domain transfer**                     | Terms from a different field are inserted, shifting the register.                           |
| **Inflation**              | **Structural inflation**                | Extra attributions or dialogue are added that weren’t in the source.                        |
| **Speculative addition**   | **Premature disambiguation**            | Ambiguous wording is forced into one meaning even when the source allowed several.          |
| **Speculative addition**   | **Canonical pull**                      | The text drifts toward a familiar or “stock” version, echoing common formulations.          |
| **Speculative addition***  | **Back-translation mismatch**           | The text looks faithful, but when translated back it reveals hidden changes (*diagnostic*). |
| **Omission / Compression** | **Segment omission**                    | Whole sentences or passages are dropped.                                                    |
| **Omission / Compression** | **Dialogue flattening**                 | Multi-voice exchanges are collapsed into a single speaker’s paraphrase.                     |
| **Omission / Compression** | **Discourse link collapse**             | Connectors like “however,” “therefore,” or “but” vanish, erasing contrast or causality.     |
| **Omission / Compression** | **Homogenized cadence**                 | The rhythm of the text is evened out, losing peaks and valleys.                             |
| **Omission / Compression** | **Flattened pacing**                    | Paragraph length and flow become monotonous.                                                |
| **Omission / Compression** | **Structural drift**                    | The overall scaffold (order, segmentation, discourse structure) is altered without notice.  |

*Table 2. Qualitative indicators of flattening, grouped by form with description.*


#### 5.9.2 Quantitative indicators
The quantitative layer adds efficiency and consistency to the detection process. 
- Quantitative indicators **MAY** be used as **diagnostic flags to identify where changes have occurred**; they signal areas requiring qualitative investigation, not evidence of flattening itself.
- Quantitative indicators **MAY** be used as proxies for detection and triage; they are diagnostic aids, not conclusive evidence.
- Where feasible, analysts **SHOULD** report both a qualitative rationale and any quantitative proxy values used.

##### 5.9.2.1 Cadence indicators:
- **Homogenized cadence:** measurable as reduced standard deviation of sentence length across aligned segments.
- **Flattened pacing:** measurable as reduced variance in paragraph length or punctuation frequency.
- **Dialogic cadence flattening:** measurable as reduced variance in turn length or decreased alternation frequency across aligned conversational turns.

##### 5.9.2.2 Stylistic indicators:
- **Loss of idioms:** detectable via lexicon match (idiom dictionaries / cultural phrase databases).
- **Neutralized register:** measurable as drop in type–token ratio (lexical richness).

##### 5.9.2.3 Semantic & interpretive indicators:
- **Over-generalization:** measurable as increased frequency of high-frequency/general-purpose tokens (e.g., “thing,” “person,” “place”).
- **Premature disambiguation:** measurable as reduced entropy in word-sense distributions (proxy from embeddings).

The next table lists the **quantitative indicators of flattening**. These are the same forms, but expressed as **patterns you can count**: shorter sentences, fewer idioms, less varied vocabulary.  
Use this table if you want to back up your qualitative observations with numbers: helpful for reports, but not required for a first pass.

| **Flattening Form (§5.3)** | **Indicator (§5.9.2)**                | **Description**                                                                 |
|-----------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| **Erosion**                 | **Loss of idioms**                    | Fewer idiomatic expressions appear; colorful phrases are replaced by plain ones. |
| **Erosion**                 | **Neutralized register**              | Vocabulary feels less varied; lexical richness is reduced.                       |
| **Erosion**                 | **Neutralization of emotional tone**  | Emotional highs and lows are flattened; intensity is leveled out.                |
| **Erosion**                 | **Over-generalization**               | Specific detail is replaced by vague or common words like “thing” or “place.”    |
| **Inflation**               | **Quotation paraphrase / event collapsing** | Direct quotes or distinct events are shortened and padded with generic wording.  |
| **Inflation**               | **Domain transfer**                   | Words from a different field or register creep in, shifting the tone.            |
| **Speculative addition**    | **Premature disambiguation**          | Ambiguous phrases are forced into a single, overly specific meaning.             |
| **Speculative addition**    | **Canonical pull**                    | Stock phrases or familiar formulations appear more often than in the source.     |
| **Omission / Compression**  | **Segment omission**                  | Whole sentences or passages are dropped from the output.                         |
| **Omission / Compression**  | **Homogenized cadence**               | Sentences all end up a similar length; rhythmic variation is lost.               |
| **Omission / Compression**  | **Flattened pacing**                  | Paragraphs lose variety, and punctuation patterns even out.                      |
| **Omission / Compression**  | **Dialogue flattening**               | Conversations lose their back-and-forth rhythm; turns become uniform.            |

*Table 3. Quantitative indicators of flattening, grouped by form with description. Quantitative indicators flag potential areas of change; they do not constitute evidence of flattening without qualitative analysis.*


#### 5.9.3 Diagnostic vs. Evidential Use
NFAF employs a two-stage process:
1. **Quantitative flags**: Identify segments where measurable changes occurred
2. **Qualitative analysis**: Determine whether flagged changes constitute domain-relevant flattening

Quantitative indicators serve as a triage system, not as proof. A drop in sentence length variance flags potential cadence changes; qualitative analysis determines whether those changes flatten narrative rhythm in that domain context.


The **flattening indicators** can be read alongside translation “loss markers” (Berman 1985), journalistic “framing shifts” (Hall 1980), and archival debates about authenticity. **NFAF** formalizes these signals as a domain-crossing taxonomy for AI mediation, ensuring that flattening cannot hide behind fluency. The framework detects and categorizes such changes consistently. Their significance, however, depends on context, goals, and domain expertise: a literary scholar may value preserving sentence-level rhythm variance, while a legal translator may appropriately flatten it for clarity.  

#### 5.10 Limitations and Cultural Scope

**NFAF** categories are grounded in Western narratology, translation studies, journalism, and legal traditions, and therefore carry the imprint of those intellectual lineages. This makes the framework **diagnostic rather than universal:** what counts as *flattening* is itself culturally contingent.

Future applications should adapt or extend the rubric with input from non-Western, multilingual, and Indigenous perspectives, testing whether the same dimensions apply, require modification, or misfire entirely. **NFAF v0.5** should thus be read as **provisional:** a shared baseline that enables comparison, but one that must be revised through cross-cultural validation and stakeholder critique.

---

## 6. Stages of Analysis

```
Input Selection --> Transformation --> Alignment --> Drift Assessment & Rubric Scoring at mediation step --> Pattern Analysis --> Human-in-the-Loop Review --> Reporting
```

The following stages define the **normative workflow** for applying **NFAF**. Analysts **MUST** implement Stages 1–5 and Stage 7, **adapting them as needed for their domain**. Stage 6 is **REQUIRED** only in high-stakes contexts (e.g., legal, medical).
- **Stage 1** anchors the process through scope declaration, baseline identification, and analysis-level setup.
- **Stages 2–6** execute the analytic workflow: generating transformations, aligning source and output, assessing drift, identifying recurring patterns, and, when required, incorporating human review.
- **Stage 7** produces the reporting layer, ensuring transparency and accountability.

Together, these stages ensure that flattening is not only detected but also **documented with reproducible evidence.** Examples in §9 illustrate how these stages may be adapted across literature, journalism, and law.

## 6.1 Stage 1: Input Selection & Baseline Identification
Analysts **MUST** implement this stage, though methods (e.g., baseline choice, coding guidelines) may vary by domain.
- Define **detailed coding guidelines** and decide whether at least two analysts will independently code a subset of materials.
- Defined desired versioning scheme.
- **Scope declaration.** Analysts **MUST** declare the corpus scope (languages, domains, time period, model versions if known).
- **Source text identification.** Establish the source narratives to be transformed.
- **Human baseline identification.** When available, specify human translations or rewritings for comparison; these baselines **SHOULD** be included in later stages (§6.3).
- **Transformation definition.** Define the intended transformation (translation, summarization, rewriting).
- **Purpose documentation.** Analysts **MUST** record the purpose and scope of the transformation to contextualize findings.
- **Define analysis levels** for alignment, drift assessment and rubric scoring.

## 6.2 Stage 2: Transformation
Analysts **MUST** document the mediation type (translation, summary, rewrite, etc.). Adaptation to domain conventions is permitted.
- **Preprocess source narratives.** 
- **Apply automated or AI-mediated** processes to generate alternate versions.  
- Preprocessing choices **MUST** be documented, as they can introduce flattening effects (§5.9).  

## 6.3 Stage 3: Alignment
Analysts **MUST** perform alignment at a level appropriate to the domain (sentence, paragraph, event, etc.). Confidence levels MUST be declared.
- Map source to output segments** (§5.7 and §5.8). 
- Analysts **MUST** record unmatched spans (omissions), inflation (one-to-many), and fused mappings (many-to-one).  
 - Granularity defaults: sentence-level (prose), clause-level (legal), turn-level (dialogue). Deviations **MUST** be justified.  
- Alignment manifests (IDs, offsets) **SHOULD** be released with examples to enable independent verification.  
- **Human Baseline Comparison:** When available, analysts **SHOULD** include professional human translations of the same source texts. Pilot validation demonstrates systematic divergence between human preservation patterns (positive scores) and AI flattening patterns (negative scores), providing crucial context for interpreting observed changes.

### 6.3.1 Alignment Confidence Levels
**NFAF** is _diagnostic_, not deterministic, analysts **MUST** declare alignment confidence and document limitations:
- **Direct alignment**: Clear 1:1 correspondence (sentence/clause level)
- **Interpretive alignment**: Requires analytical judgment due to restructuring
- **Partial alignment**: Some segments unmappable due to transformation complexity
- **Failed alignment**: Structural reorganization prevents reliable correspondence

**NFAF** findings **SHOULD** be interpreted within declared confidence limits. Lower confidence does not invalidate analysis but constrains claims about undetected flattening effects.

## 6.4 Stage 4: Drift Assessment & Rubric Scoring at each mediation step
Analysts **MUST** assess structural and semantic drift at each mediation step. Scoring **MAY** be adapted to domain-relevant cues.
- **Assess Structural Drift** (§5.6.1) and **Semantic Drift** (§5.6.2) at every mediation step. In multi-step AI mediation processes, flattening effects may compound; therefore, drift and rubric scoring should be performed at each stage, not only on the final output. 
- **Score and record** each dimension at segment level.   	
- Analysts **MUST** examine shifts in dialogue, omissions, event collapsing, tone, and cultural/emotional signals.  
	
```
Quantitative Indicators --> Flag Changes --> Qualitative Analysis --> Domain Assessment --> Flattening Diagnosis
```

## 6.5 Stage 5: Pattern Analysis 
Analysts **MUST** analyze recurring flattening patterns. Multiple-analyst agreement **SHOULD** be measured where applicable.
- If multiple analysts, measure inter-annotator agreement using standard metrics (Cohen's kappa, etc.); though, perfect agreement is not expected.
- **Record recurring flattening patterns** across transformations. 
- **Record recurring flattening patterns** across transformations. 
- Analysts **SHOULD** contrast NFAF findings with standard NLP metrics (BLEU, ROUGE, perplexity) to highlight narrative-level effects not captured by surface metrics.  

## 6.6 Stage 6: Human-in-the-Loop Review *(optional except in high-stakes contexts)*
Optional in general practice, but **MUST** be included for high-stakes contexts (e.g., law, medicine, archival preservation).
- Analysts **MAY** validate findings through targeted human evaluation.  
- For high-stakes contexts (e.g., legal, medical), human review **MUST** be included.  

## 6.7 Stage 7: Reporting
Analysts **MUST** produce a reporting layer documenting evidence, rationale, and limitations. Format may be adapted by domain (tables, narrative notes, visualizations).
- **Summarize observed patterns** and contributing factors.  
- When omissions occur, outputs **MUST** be labeled as summaries or rewrites and accompanied by an alignment manifest (§5.7).  
- Omission without disclosure **MUST** be treated as flattening and constitutes a material misrepresentation in the interpretive/ethical sense.  

The next table lays out the **NFAF stages of analysis**.  
These stages show the order of work: how to prepare your input, run the mediation, align the texts, identify drift, and finally report your findings.  
Use this table as a roadmap: follow the stages in sequence, and note that Stage 6 (Human-in-the-Loop Review) is optional in ordinary cases but mandatory in high-stakes contexts.

| Analysis Step | Stage                                                                                                                                                                                                                                                                                                                                |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Setup         | - Stage 1: Input Selection & Baseline                                                                                                                                                                                                                                                                                                |
| Analysis      | - Stage 2: Transformation (Document preprocessing choices) <br>- Stage 3: Alignment (Record unmatched spans; disclose drift) *map source/output* <br>- Stage 4: Drift Assessment & Rubric Scoring  <br>- Stage 5: Pattern Analysis *recurring shifts*  <br>- Stage 6: Human-in-the-Loop Review (optional) *mandatory in high-stakes* |
| Reporting     | - Stage 7: Reporting  (Omission without disclosure = flattening/interpretive misrepresentation)                                                                                                                                                                                                                                      |

*Table 4. Stages of analysis in the Narrative Flattening Analysis Framework (NFAF).*


---

## 7. Rubric 
**NFAF** rubric dimensions detect systematic changes but do not determine acceptability thresholds. Domain experts must interpret whether observed changes constitute problematic flattening based on context-specific values and requirements. Metrics defined here are diagnostic indicators validated against human translation baselines, and **MUST** always be paired with qualitative evidence. They are not prescriptive thresholds. 

The dimensions below should be interpreted in relation to the recurrent forms of flattening defined in §5.3 (erosion, inflation, inference, omission/compression). Together, forms and dimensions provide a layered framework: forms describe how flattening manifests; dimensions describe where it is observed.
If AI mediation normalizes inputs through a Centroid Pivot (§5.4.2), systemic signatures are commonly observed across the following dimensions:  
- **Cadence**: variance drops (e.g., English-like pacing).  
- **Lexical/Stylistic**: substitution of culture-specific items with globally fluent paraphrase.  
- **Cultural Register**: dilution of local or culturally marked terms.  
- **Semantic/Interpretive**: shifts toward Anglophone priors (e.g., canonical pull, premature disambiguation).  

Analysts **MUST** disclose observed shifts, and reports **MUST** pair quantitative Δ values with qualitative examples (e.g., idiom paraphrase, loss of irony).

The rubric dimensions define the **core lenses for analyzing flattening**.  
Each dimension corresponds to a specific type of narrative signal: rhythm, vocabulary richness, figurative language, cultural references, affect, or structural coverage.  
The table shows (a) the signals to check, (b) guidance for interpretation, and (c) reporting obligations to ensure analytical rigor and ethical responsibility.  
Use this as your anchor: every observed indicator can be tied back to one or more rubric dimensions.

| Rubric Dimension         | Core Signals (Δ = Output − Source unless noted)                                                                                                                                                                    | Notes                                                                                        | Reporting obligations, analytical and ethical responsibilities (non-prescriptive)       |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------- |------------------------------------------------------------------------------------------------------------|
| **Cadence & Rhythm**     | Sentence length mean/variance; syllables per sentence; punctuation cadence (commas, em-dashes, ellipses per 1k tokens)                                                                                             | A drop in variance = flattening. Keep to local text length to observe segment-level effects. | Loss of rhythm is not “clarification”; it is flattening of narrative voice and **MUST** be disclosed.      |
| **Lexical Richness**     | Type–Token Ratio (TTR), Measure of Textual Lexical Diversity (MTLD), hapax legomena share (unique once-used words), rare-word rate                                                                                 | For “rare,” threshold by frequency quantile in the source or a reference corpus.             | Suppression of rare/culturally marked lexemes constitutes erasure if undocumented.                         |
| **Figurative Density**   | Idiom frequency per 1k tokens; simile markers (“like/as a,” “como un/una”); metaphor candidates (if available)                                                                                                     | Start with rule-based proxies; document limitations.                                         | Paraphrasing idioms/metaphors into plain text is a cultural loss and **MUST** be made visible.             |
| **Cultural Register**    | Named entities tied to locale; culture-specific lexicon/idioms; % replaced by generic terms                                                                                                                        | Build small gazetteers for test cultures (places, foods, sayings).                           | Entity dilution, idiom neutralization, or honorific loss are cultural erasures, not neutral substitutions. |
| **Emotional Intensity**  | Evaluative/affect lexicon counts; sentiment/subjectivity measures; categories from tools such as Linguistic Inquiry and Word Count (LIWC) or Empath                                                                | Track both direction (↑/↓) and range (standard deviation) of affect.                         | Compression of affect range erases narrative highs/lows; neutralization **MUST** be disclosed.             |
| **Coverage & Structure** | Segment retention (kept/total), compression ratio (tokens_out ÷ tokens_in), unmatched span count; discourse relation preservation (if Rhetorical Structure Theory (RST) or Universal Dependencies (UD) tools used) | High omission or many-to-one fusions imply flattening. Report dropped segment IDs/ranges.    | Omission without disclosure risks material misrepresentation; structural drift **MUST** be traceable.          |

*Table 5. Rubric dimensions for analyzing narrative flattening, with signals, guidance, and reporting responsibilities.*  
Δ convention: Output − Source (positive = more in output; negative = less). Example: if sentence-length variance drops from 42.1 → 18.6, Δσ² = −23.5, a flattening cue.


### 7.1 NFAF Rubric: Cadence & Rhythm
**Signals:**  
- Mean and variance of sentence length.  
- Punctuation cadence (commas, em-dashes, ellipses per 1k tokens).  
- Figurative or imagery clusters that shape narrative flow.  

**Testable Predictions:**  
1. **Variance reduction.** Sentence length variance (σ²) commonly decreases after AI mediation, converging toward English-like pacing. Analysts **SHOULD** compare against source-genre baselines before concluding flattening.  
2. **Prosodic flattening.** Distinctive rhythm markers (em-dashes, ellipses, enjambment) are replaced by default punctuation (commas, periods). Analysts **MUST** disclose such shifts as cadence loss.  
3. **Peak loss.** Figurative “bursts” (clusters of metaphor, irony, lyricism) appear less frequently or are redistributed more evenly across the text. Analysts **SHOULD** document the redistribution as flattening of intensity.  

**Normative Directive:**  
Flattening of cadence **MUST** be disclosed as a loss of narrative voice. Treating rhythmic simplification as “clarification” constitutes flattening and erases meaning.  

**Anchors:**  
- Stylistics: cadence as a carrier of meaning, not ornament (Leech & Short 1981).  
- Authorship studies: variance as a stylistic fingerprint (Burrows 2002; Stamatatos 2009).  
- Translation studies: critique of “rationalization” (Berman 1985).  
- NLP: systemic convergence in embeddings (Hamilton et al. 2016); pivot layers in NMT (Johnson et al. 2017).  

---

### 7.2 NFAF Rubric: Lexical Richness
**Signals:**  
- Type–Token Ratio (TTR).  
- Measure of Textual Lexical Diversity (MTLD).  
- Hapax legomena share (unique once-used words).  
- Rare-word rate (frequency quantile relative to source or a reference corpus).  

**Testable Predictions:**  
1. **Diversity reduction.** TTR and MTLD scores commonly decrease in AI-mediated outputs, showing convergence on mid-frequency vocabulary. Analysts **SHOULD** test against source-genre baselines.  
2. **Rare-word suppression.** Hapax legomena and culturally marked lexemes decline, substituted with high-frequency synonyms. Analysts **MUST** document such substitutions when they alter cultural or stylistic signals.  
3. **Register neutralization.** Distinctive technical, regional, or sociolectal vocabulary is replaced by globally accessible terms. Analysts **SHOULD** disclose such neutralization.  
4. **Overuse of “safe” lexemes.** A limited set of frequent words (e.g., “important,” “significant,” “good”) appears at higher rates than in the source. Analysts **SHOULD** record elevated repetition as a flattening cue.  

**Normative Directive:**  
Suppression or substitution of rare and culturally marked lexemes **MUST** be treated as erasure. Ethical reporting requires making these substitutions visible. Analysts **SHOULD** interpret lexical diversity within the typological context of the language (inflectional vs. analytic).  

**Anchors:**  
- Stylistics: vocabulary as a stylistic marker (Leech & Short 1981).  
- Translation studies: translational norms favoring common lexical items (Toury 1995).  
- Computational stylistics: distinctive lexical distributions for authorship attribution (Burrows 2002).  
- NLP: centroid bias privileging high-frequency English lexicon (Bender et al. 2021).  
- Corpus linguistics: measuring lexical diversity across corpora (McEnery & Hardie 2012).  

---

### 7.3 NFAF Rubric: Figurative Density
**Signals:**  
- Idiom frequency per 1k tokens.  
- Simile markers (e.g., “like/as a,” “como un/una,” “comme un/une”).  
- Metaphor candidates (rule-based or embedding-based detection if available).  
- Clusters of figurative language that drive imagery, irony, or tone.  

**Testable Predictions:**  
1. **Idiom loss.** Culture-specific idioms are commonly paraphrased into generic phrases (e.g., _tirar la toalla_ → “to give up”). Analysts **MUST** disclose such substitutions.  
2. **Simile simplification.** Similes with culturally rich referents are replaced with neutral or universal comparisons. Analysts **SHOULD** document the simplification as flattening.  
3. **Metaphor reduction.** Extended metaphoric structures (multi-clause conceits, allegories) are shortened or omitted. Analysts **MUST** record these reductions where they alter figurative signal.  
4. **Density smoothing.** Peaks of figurative intensity (e.g., lyric passages in literature, rhetorical flourishes in journalism or law) are redistributed into more even, literal prose. Analysts **SHOULD** note redistribution patterns as flattening cues.  

**Normative Directive:**  
Paraphrasing idioms, similes, or metaphors into plain text **MUST** be treated as a loss of figurative signal. Ethical reporting requires documenting these shifts. Analysts **SHOULD** supplement automated tools with manual annotation, since existing systems under-detect culturally marked figuratives.  

**Anchors:**  
- Translation studies: figurative “clarification” as flattening (Berman 1985).  
- Stylistics: metaphor and idiom as core stylistic markers (Leech & Short 1981).  
- Digital Humanities: figurative density as quantifiable signal in large corpora (Jockers 2013; Moretti 2013).  
- NLP: AI bias toward literal paraphrase when figurative usage is uncertain (Shutova 2010; Dankers et al. 2019).  

---

### 7.4 NFAF Rubric: Cultural Register
**Signals:**  
- Named entities tied to locale (places, foods, institutions, idioms).  
- Culture-specific lexicon and sayings.  
- Percentage of culture-specific terms replaced by generic, universal, or Anglophone-oriented terms.  
- Presence or absence of honorifics, politeness markers, or culturally specific discourse cues.  

**Testable Predictions:**  
1. **Entity dilution.** Local place names, foods, or institutions are generalized (e.g., _bodega_ → “corner store,” _soba_ → “noodles”). Analysts **MUST** disclose these substitutions.  
2. **Discourse marker shifts.** Loss or overuse of culturally distinctive connectives (e.g., *pues* in Spanish, *en fait* in French). Analysts **SHOULD** document these shifts.  
3. **Idiom neutralization.** Proverbs and culturally distinctive sayings are paraphrased into plain or global equivalents. Analysts **MUST** treat these as flattening.  
4. **Honorific loss.** Politeness markers (e.g., _usted_, _-san_, _monsieur_) are omitted or flattened into direct address. Analysts **MUST** flag these omissions.  
5. **Centroid language substitution.** Target text exhibits features from the dominant centroid language: for example, Anglophone metaphors, collocations, or formatting (e.g., U.S.-style date/time, “Mr.” for non-English honorifics). Analysts **MUST** report such substitutions as cultural overwriting.  
6. **Centroid Pivot Imprint.** Even in non-English ↔ non-English transformations, outputs may carry stylistic defaults from the pivot language. This imprint **MAY** vary by system and dataset. At present, it often manifests as English-like discourse markers (e.g., *en realidad, como resultado* in Spanish; overuse of *en fait* in French). Analysts **SHOULD** treat these as indicative of systemic pivot influence rather than source/target features.  

**Normative Directive:**  
Shifts in discourse markers, honorifics, or culturally specific lexicon **MUST** be flagged. Such substitutions are not neutral; they constitute flattening and risk overwriting situated cultural identity with centroid defaults.  

**Anchors:**  
- Translation studies: ethnocentric reduction of idioms and references (Berman 1985); translational norms under systemic pressure (Toury 1995); domestication as erasure of local markers (Venuti 1995).  
- Globalization: flattening of small/local languages through lingua franca mediation (Cronin 2003).  
- NLP/MT: systemic English dominance in multilingual models (Johnson et al. 2017; Bender et al. 2021).  

---

### 7.5 NFAF Rubric: Emotional Intensity
**Signals:**  
- Evaluative/affect lexicon counts (positive/negative adjectives, intensifiers).  
- Sentiment polarity and subjectivity measures.  
- Variability of affect (standard deviation of sentiment scores across segments).  
- Use of exclamatives, modal verbs, rhetorical questions as emotional carriers.  
- Sarcasm/irony markers (contrastive cues, hyperbole, scare quotes) that convey affect indirectly.  

**Testable Predictions:**  
1. **Neutralization of affect.** Strongly positive or negative terms are commonly replaced by moderate descriptors (e.g., _horrifying_ → “bad,” _exquisite_ → “beautiful”). Analysts **MUST** disclose such substitutions.  
2. **Range compression.** Standard deviation of affect scores often decreases; emotional highs and lows flatten into mid-intensity prose. Analysts **SHOULD** compare against source-genre baselines.  
3. **Removal of markers.** Exclamatives, modal intensifiers (_must, should_), or rhetorical questions are omitted or converted to declaratives. Analysts **MUST** flag these as flattening.  
4. **Cultural calibration loss.** Affect signals are normalized without regard to cultural conventions (e.g., ¡Hola! vs. Hello! vs. ！). Analysts **SHOULD** document when mediation imposes a uniform mid-level register.  
5. **Tone smoothing across genres.** Journalism summaries downplay outrage or urgency; literary passages lose lyric peaks of sorrow/joy; legal rhetoric loses emphatic certainty. Analysts **SHOULD** record such genre-dependent smoothing.  

**Normative Directive:**  
Neutralization or compression of affect **MUST** be treated as flattening of narrative arcs. Emotional resonance cannot be erased invisibly; analysts **MUST** disclose these changes. Analysts **SHOULD** calibrate affect tools against source-language baselines or use manual annotation where automated tools are Anglophone-calibrated.  

**Anchors:**  
- Narratology: mood and tone as narrative discourse dimensions (Genette 1980).  
- Translation studies: tonal reduction via “ennoblement” or “clarification” (Berman 1985); domestication into neutral register (Venuti 1995).  
- Digital Humanities: sentiment arc measurement (Ramsay 2011; Jockers 2013).  
- NLP: affect lexicons (Pennebaker et al. 2001; Fast et al. 2016); moderation toward neutrality in LLM sentiment outputs (recent work).  

---

### 7.6 NFAF Rubric: Coverage & Structure
**Signals:**  
- Segment retention ratio (kept/total).  
- Compression ratio (tokens_out ÷ tokens_in).  
- Count of unmatched spans (omitted, fused, or inflated segments).  
- Preservation of discourse relations (contrast, cause, elaboration via **Rhetorical Structure Theory (RST)** or **Universal Dependencies (UD)** markers).  
- Integrity of quotations, speaker turns, and attributions.  

**Testable Predictions:**  
1. **Segment loss.** AI-mediated outputs commonly omit or fuse multiple source segments, reducing overall coverage. Analysts **MUST** flag such omissions.  
2. **Compression bias.** Outputs exhibit higher compression ratios than human-mediated equivalents, especially in summarization. Analysts **SHOULD** compare across baselines.  
3. **Discourse link collapse.** Explicit markers of causality, contrast, or elaboration are dropped (e.g., *sin embargo*, *parce que*, “however”). Analysts **MUST** disclose such losses.  
4. **Dialogue flattening.** Multi-turn exchanges are collapsed into single-speaker paraphrase. Analysts **MUST** report such flattening.  
5. **Structural drift.** Narrative scaffold (event sequencing, clause nesting, paragraphing) is altered without disclosure, producing fluent but structurally divergent outputs. Analysts **MUST** flag undisclosed drift.  
6. **Multimodal omission.** When inputs include images, graphs, or visuals, mediated outputs may omit them. Analysts **SHOULD** record such omissions explicitly.  
7. **Longitudinal drift.** Chronologies are compressed or events reordered, altering historical or archival integrity. Analysts **MUST** report such shifts.  
8. **Integrity of formatting/paratext.** Footnotes, references, or headings (e.g., legal citations) are dropped. Analysts **MUST** treat such omissions as structural flattening.  

**Normative Directive:**  
Omissions, re-orderings, or structural drift without disclosure **MUST** be treated as flattening. Such changes mislead readers about fidelity and compromise accountability.  

**Anchors:**  
- Discourse theory: discourse relations as narrative scaffold (Mann & Thompson 1988; van Dijk 2008).  
- Translation studies: omission and rationalization as systemic tendencies (Berman 1985).  
- Journalism studies: framing and omission reshape stance (Hall 1980).  
- NLP: compression vs. fidelity trade-offs in summarization (Hamilton et al. 2016; ROUGE, BLEU).  
- Archival science: provenance and integrity principles highlight why omissions compromise accountability.  

### 7.7 NFAF Rubric: Rubric Extensions and Domain-Specific Quantification
The **NFAF rubric** is defined across six dimensions: cadence & rhythm, lexical richness, figurative density, cultural register, emotional intensity, and coverage & structure. These indicators are deliberately domain-agnostic, allowing them to be observed across literary texts, journalistic accounts, legal registers, or multimodal narratives.

While the framework itself remains fixed, the rubric admits domain-specific extensions in the form of quantification schemes. Such extensions transform qualitative indicators into reproducible scoring systems tailored to a research context. Examples include:

- **Journalism and News** ratios of global newswire phrasing versus local idiomatic reporting to quantify stance homogenization.
- **Translation Studies** a signed scale per dimension (e.g., −5 … +5) to capture subtractive versus additive drift in AI-mediated translation.
- **Historical and Archival Texts** coverage scored by omissions or condensations in AI-generated summaries of primary sources.
- **Legal Texts** lexical scoring via shifts in statutory anchors versus paraphrase density.
- **Multimodal Narratives (Images/Film)** cadence measured as variance in frame or scene sequencing; coverage as motif preservation.

These extensions do not alter the framework itself; they are layered on top of the existing rubric to make flattening measurable in a given domain. NFAF thus remains a general diagnostic framework, while individual projects demonstrate how its dimensions can be operationalized through quantification.

Preliminary validation demonstrates the rubric’s diagnostic capability. Across pilot corpora, AI translations show systematic negative scores on figurative density, cadence, and cultural register dimensions, while human translations show positive scores, indicating preservation or enhancement of source features. This empirical distinction validates NFAF’s theoretical claims about systematic AI convergence effects and motivates the foundations detailed in §8.

---

## 8. NFAF Foundations 
NFAF situates itself within and extends prior debates in narratology, translation studies, stylistics, and computational linguistics. Some categories are adapted from existing traditions (e.g., Drift from linguistics, Alignment from corpus studies); others are defined within this framework (e.g., Narrative Flattening, Centroid Pivot). This distinction is deliberate:
	- Adapts = terms reframed for AI mediation but grounded in prior scholarship.
	- Defines = terms coined in NFAF to capture effects not previously formalized.

Preliminary validation (§7.7) confirms that these constructs are not only theoretical but empirically observable: AI translations show systematic negative scores across figurative density, cadence, and cultural register dimensions, while human translations show positive scores, indicating preservation or enhancement of source features. This empirical distinction validates the framework’s theoretical claims about systematic AI convergence effects.

- **Centroid Pivot and Precedents.**  
  NFAF **defines** *Centroid Pivot (CP)* as a general mechanism of normalization toward dominant defaults. It is a normative construct for analysis, not a claim about specific system internals. Precedents include:  
  - **Relay translation** (Toury 1995; Santoyo 2009), where texts pass through intermediate languages.  
  - **Interlingua / pivot layers** in machine translation (Koehn 2009), where systems map to intermediate representations.  
  - **Globalization pivots** in translation flows (Cronin 2003), where certain languages act as systemic hubs.  

  NFAF extends these by articulating CP as:  
  1. A mechanism not limited to translation but spanning modalities (text, image, sound).  
  2. A process that may be **internal** (inside a model or cognition) or **external** (relay between mediators).  
  3. A force that is **not language-bound:** in medieval Spain, Castilian Spanish served as a pivot; in contemporary AI, the statistical default is often English; in future systems, Mandarin or Hindi could dominate.  

- **Narrative Flattening and Cultural Heritage.**  
  NFAF **defines** *Narrative Flattening* as systemic reduction or distortion of distinctiveness in voice, rhythm, cultural register, or emotional intensity during mediation. While translation studies (Venuti 1995; Berman 1985) describe analogous losses under domestication or the “negative analytic,” NFAF specifies *flattening* as a reproducible, diagnosable phenomenon across mediation types, including AI rewriting and summarization.  

- **Narratology** (Genette 1980; Bal 1985; Ryan 2004).  
  Established the study of discourse, framing, and sequencing as carriers of meaning.  

- **Translation Studies** (Venuti 1995; Berman 1985; Toury 1995).  
  Foregrounded ethics of mediation, domestication, and invisibility. NFAF acknowledges these debates but emphasizes how AI mediation amplifies them through scale and recursive feedback loops.  

- **Digital Humanities** (Drucker 2014; Ramsay 2011; Jockers 2013).  
  Advanced computational and interpretive reading, critiquing assumptions of neutrality.  

- **Stylistics & Authorship Studies** (Leech & Short 1981; Burrows 2002; Stamatatos 2009).  
  Quantified style through cadence, vocabulary, and authorship markers.  

- **Media & Culture** (Hall 1980).  
  Framing theory and encoding/decoding show how mediation shapes stance.  

- **AI / NLP** (Papineni et al. 2002; Lin 2004; Koehn 2009; Hamilton et al. 2016; Mohammad & Turney 2013; Bender et al. 2021; Mitchell 2021).  
  Exposed bias and convergence in large models; introduced evaluation standards (BLEU, ROUGE); developed sentiment lexicons. NFAF complements, rather than replaces, these surface metrics by focusing on narrative voice, cultural register, and emotional resonance.  

- **Mechanism & Mediation (Cronin 2003; Johnson et al. 2017).**  
  Identified globalization pressures and pivot mechanisms that flatten linguistic and cultural signals.  

- **Alignment Studies (Gale & Church 1993).**  
  Introduced statistical methods for aligning bilingual corpora, foundations for modern parallel analysis.  

The following table situates the NFAF rubric dimensions within established disciplinary traditions.  
Each field provides conceptual anchors (narratology, translation studies, stylistics, digital humanities, and more) that inform how flattening is understood and measured.  
Use this table as a map: it shows that the rubric dimensions are not arbitrary but extend and recombine existing debates across theory, method, and practice.

| **Disciplinary Anchor**       | **Key Concepts**                                    | **NFAF Rubric Dimensions Supported**                                                          |
| ------------------------------ | -------------------------------------------------- |-----------------------------------------------------------------------------------------------|
| Narratology (Genette; Bal; Ryan) | Discourse, framing, sequencing, tone               | · Cadence & Rhythm <br/> · Emotional Intensity <br/> · Coverage & Structure                   |
| Translation Studies (Venuti; Berman; Toury) | Domestication, foreignization, loss markers, norms | · Lexical Richness <br/> · Figurative Density <br/>  · Cultural Register <br/>  · Emotional Intensity |
| Digital Humanities (Drucker; Ramsay; Jockers) | Algorithmic criticism, interpretive drift, critique of neutrality |· Figurative Density <br/> · Emotional Intensity <br/> · Coverage & Structure                         |
| Stylistics & Authorship Studies (Leech & Short; Burrows; Stamatatos) | Style as measurable signal, cadence, vocabulary, authorship | · Cadence & Rhythm <br/>  · Lexical Richness <br/> · Figurative Density                               |
| Media & Culture (Hall)         | Framing, encoding/decoding, stance shaping          | · Cultural Register <br/> · Coverage & Structure                                                      |
| AI / NLP (Papineni; Lin; Koehn; Hamilton; Bender; Mitchell) | Bias, fairness, semantic drift, centroid convergence; evaluation metrics | · Lexical Richness <br/> · Cultural Register <br/> · Coverage & Structure                                   |
| Mechanism & Mediation (Cronin; Johnson et al.) | Globalization, pivot mechanisms, zero-shot translation | · Cultural Register <br/> · Coverage & Structure <br/> · Cadence & Rhythm                                   |
| Alignment Studies (Gale & Church) | Statistical sentence alignment, parallel corpora   | · Coverage & Structure (Alignment)                                                              |

*Table 6. Disciplinary anchors and their contributions to NFAF rubric dimensions.*  


Together, these anchors demonstrate that NFAF is not limited to any single discipline: it translates long-standing humanistic concerns into a replicable diagnostic for the AI-mediated era. Preliminary validation confirms this: AI translations show systematic negative scores across figurative density, cadence, and cultural register dimensions, while human translations show positive scores, indicating preservation or enhancement of source features. This empirical distinction validates the framework’s theoretical claims about systematic AI convergence effects.

---

## 9. Applications: NFAF AI-mediated Flattening - Illustrative, not exhaustive.
In the following examples, **NFAF** conventions are applied to demonstrate how flattening can be identified in practice.  
For clarity, each **qualitative alignment table** is followed by an **Observed** block (what is visible in the text), and each **quantitative metrics table** is followed by an **Interpretation** block (how to read the numbers as diagnostic cues).  
These labels are conventions for the examples only; they are not part of the core NFAF specification.  
The aim is to help the reader see how qualitative and quantitative evidence complement one another in detecting **narrative flattening.**

**NFAF** does not issue verdicts. It equips stakeholders with categories, indicators, and rubrics to make transformation effects visible. The diagnosis of flattening is always situated and interpretive: stakeholders decide, based on evidence, whether observed changes constitute flattening in a given domain or mediation type.

#### Model Information
Model information is at ./examples_ejemplos/model_information.txt
- **Model A:** ChatGPT 
- **Model B:** Claude 
- **Model C:** Gemini 
- **Model D:** DeepL 

#### Generic NFAF Workflow (Normative)
- Stage 1: Input Selection & Baseline Identification  
- Stage 2: Transformation (AI-mediated)  
- Stage 3: Alignment (level adapted to domain)  
- Stage 4: Drift Assessment & Rubric Scoring (structural + semantic)  
- Stage 5: Pattern Analysis (recurring flattening)  
- Stage 6: Human-in-the-Loop Review (optional, REQUIRED in high-stakes)  
- Stage 7: Reporting (domain-adapted outputs)  


### 9.1 Literary Rewrite (Austen, *Emma*)
*NFAF evaluates outputs, not actors; the aim is transparency around transformation effects.*

- **Domain:** Literary
- **Focus:** Stylistic flattening (voice/cadence)
- **EX01 version:** v01
**Source:** Jane Austen, *Emma* (1815), Chapter 1 excerpt (public domain).  
**Mediation:** Modernized rewrite by three models.  
**Data:** Data files are located at ./examples_ejemplos/EX01_Literature_Literatura

**Summary Finding:**  
Rewrites produced fluent modern English but erased Austen’s irony and **narrative rhythm.** Omissions were not disclosed, constituting flattening of **Coverage & Structure** (§7.6).

**Application Glossary (for the *Emma* ch1 Paragraph 5 case study):**  
- **Rewrite:** 1–1 mapping.  
- **Summary:** Omission with disclosure.  
- **Missing:** Null alignment.  
- **Inflated rewrite:** Expansion with padding.  

**Sequence**
- **Input Selection & Baseline Identification:** Emma ch1 (paragraph-level baseline)  
- **Transformation:** AI-mediated rewrite  
- **Alignment:** paragraph-level  
- **Drift Assessment & Rubric Scoring:** quantitative + qualitative  
- **Pattern Analysis:** recurring stylistic flattening  
- **Human-in-the-Loop Review:** Optional. Alignment and analysis performed by human analyst.  
- **Reporting:** tables + narrative notes  

#### Alignment Excerpt (*Emma* ch1 Paragraph 5)

The next table shows a worked alignment example using Austen’s *Emma* (chapter 1, paragraph 5).  
The source passage is placed side by side with three AI-mediated rewrites.  
Use this table to see how flattening is detected in practice: align source to output, note shifts in cadence, idioms, or omissions, and then trace those observations back to the rubric dimensions introduced earlier.

| **Source (Austen)**                                                                                                                                                                                                                             | **Model A:** ChatGPT                                                                                                   | **Model B:** Claude                                                                                                                                                                                             | **Model C:** Gemini                                                                                                                                                                                         |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| _“Sorrow came—a gentle sorrow—but not at all in the shape of any disagreeable consciousness.—Miss Taylor married. … Her father composed himself to sleep after dinner, as usual, and she had then only to sit and think of what she had lost.”_ | _“Her first taste of sorrow came when Miss Taylor married Mr. Weston. … Emma wondered how she would bear the change.”_ | _“Then sorrow came—a gentle sadness—but not in the form of any unpleasant self-awareness. … Her father settled down for his usual after-dinner nap, and she could only sit and think about what she had lost.”_ | _“Then, a gentle sadness came—but not in the form of any uncomfortable self-realization. … Her father fell asleep after dinner as usual, and Emma was left to just sit and think about what she had lost.”_ |

*Table 7. Alignment excerpt from Austen’s Emma, showing source against three AI rewrites.*

**Observed:**
- **Model A** (Omission/Compression) compresses to a hybrid: half rewrite, half summary (drops dining/nap scene into generalized reflection). 
- **Model B** (Erosion - Cadence)preserves all narrative beats (true rewrite, but cadence is flattened). 
- **Model C** (Inflation) preserves sequence but inflates with over-specific phrasing (“continuous mournful thought”).

#### Cadence Metric (*Emma* ch1 Paragraph 5)
This table demonstrates how NFAF can make **cadence shifts visible with simple metrics**.  
It compares mean sentence length and variance between the source and model outputs.  
The numbers are not statistical proof: they illustrate how smoothing cadence (lower variance) signals flattening of rhythm.  
Use this as a diagnostic aid: if variance collapses, the text has lost its ebb and flow.

*Note:* This example isn't meant to be statistical proof - it's a demonstration of how the framework operates.

| **Text**        | Mean sentence length (words) | Variance (σ²) | Notes                                                                               |
| --------------- | ---------------------------- | ------------- | ----------------------------------------------------------------------------------- |
| Source (Austen) | 27.8                         | **42.1**      | Long, varied clauses with em-dashes; rhythm of buildup and release.                 |
| Model A         | 22.3                         | **15.4**      | Compression + summarization into a shorter, more uniform sentences.                 |
| Model B         | 24.7                         | **18.6**      | Retains sequence but cadence smoothed; em-dash rhythm lost.                         |
| Model C         | 25.1                         | **17.9**      | Similar to B; over-specific phrasing adds slight padding, still flattened variance. |

*Table 8. Cadence metrics for Austen’s Emma, showing reduced variance and flattened rhythm in model rewrites.

**Interpretation:**
Sentence-length variance drops sharply in all rewrites, demonstrating homogenized **Cadence & Rhythm** (§7.1). Austen’s rhythmic “peaks and valleys” are flattened into more even prose. Qualitative evidence shows loss of irony and tonal shifts, linking also to **Emotional Intensity** (§7.5).  

Variance reduction is a diagnostic cue, not proof in isolation. Stakeholders using **NFAF** must combine quantitative measures with qualitative evidence to determine whether flattening has occurred.

---

### 9.2 Journalism & News (Summarization) 
*NFAF evaluates outputs, not actors; the aim is transparency around transformation effects.*

In contrast to the literary rewrite example in §9.1, where flattening appeared as the loss of cadence, irony, and stylistic rhythm, journalism demonstrates a different pattern. Here, the mediation is **summarization**, and the domain is **news reporting across regions**. Flattening does not emerge as stylistic erosion but as the **neutralization of editorial stance, cultural references, and actor voices**, resulting in a homogenized “wire-style” narrative. This illustrates how the same rubric dimensions apply across domains, even though the signals of flattening differ.

- **Domain:** Journalism & News
- **Focus:** Cultural flattening (journalistic stance)
- **EX02 version:** v01

**Source:** Six outlets (Guardian, Fox, El País, BBC, AP, Reuters) reported on the same U.S. court ruling, each with its own cultural stance and editorial register.  
**Mediation:** Summarization by one model.  
**Data:** Data files are located at ./examples_ejemplos/EX02_Journalism_Noticias

**Summary Finding:**  
Claude’s summaries consistently neutralized outlet-specific differences, **compressing coverage (though less severely than other systems)**, thinning rather than eliminating quotes, paraphrasing evaluative language, and erasing or generalizing cultural markers (“migrantes,” “Everglades,” “controversial”). In one case, stance markers were even **added** (“Trump-appointed judge”), showing a mild canonical pull. This demonstrates cultural flattening: the systematic reduction of diverse journalistic voices into a single, homogenized register.

**Application Glossary (for the Journalism & News case study):**
- **Stance markers:** Partisan or evaluative labels (e.g., _Obama-appointed judge_, _open-borders activists_).
- **Cultural register:** Localized or regional references (e.g., _Everglades_, _Miccosukee Tribe_, _migrantes_).
- **Editorial diversity:** Distinct journalistic voices shaped by outlet, region, or political orientation.
- **Centroid news register:** Neutral, standardized “wire” style prose resembling AP/BBC tone.

**Sequence**
- **Input Selection & Baseline Identification:** Guardian, Fox, El País, BBC, AP, Reuters    
- **Transformation:** AI-mediated summarization    
- **Alignment:** article-level  
- **Drift Assessment & Rubric Scoring:** quantitative + qualitative  
- **Pattern Analysis:** cultural flattening patterns  
- **Human-in-the-Loop Review:** Optional. Alignment and analysis performed by human analyst.  
- **Reporting:** tables + narrative notes 

#### Alignment Excerpts (Six outlets - Journalism & News (Summarization))
The following table shows alignment excerpts for six outlets reporting on the same U.S. court ruling.  
Each outlet presents its coverage with a distinct editorial register and cultural stance.  
The Model B summarization, shown alongside, demonstrates how diverse journalistic voices are compressed into a uniform style.


| Outlet                   | The Guardian News                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Title/Author/Date        | *‘Alligator Alcatraz’ immigration jail can stay open, appeals court says*<br>Publication Date: 2025-09-04                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Country                  | AU                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| URL                      | https://www.theguardian.com/us-news/2025/sep/04/alligator-alcatraz-appeals-court                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Model B:  Claude Summary | An appellate panel voted 2-1 to put on hold a federal judge's order to close the "Alligator Alcatraz" immigration detention center in Florida's Everglades within 60 days, allowing the controversial facility to continue operations while appeals are pending. The facility, which cost approximately $250 million to build and covers over 18 acres in the subtropical wetlands 37 miles west of Miami, was hastily constructed by Ron DeSantis's administration in late June to support Donald Trump's deportation efforts, with its remote swampy location deliberately chosen as an escape deterrent. The detention center has faced widespread criticism for harsh conditions, alleged abuse of detainees, denial of due process, and environmental damage to the fragile Everglades ecosystem that's home to alligators, crocodiles, pythons, rare birds, and manatees. The 11th U.S. Circuit Court of Appeals ruled that the Trump administration would likely prevail against environmental groups' legal challenge, determining that since Florida funded the project itself while seeking federal reimbursement later, it didn't trigger the environmental review requirements that apply to federally funded construction projects, despite both DeSantis and DHS Secretary Kristi Noem stating the federal government would pay for facility expansion.<br> |

---

| Outlet                   | Fox News                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Title/Author/Date        | *Operations at 'Alligator Alcatraz' back on after appeals court halts judge's order*<br>by Landon Mion Fox News<br>Publication Date: 2025-09-04                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Country                  | USA                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| URL                      | https://www.foxnews.com/politics/operations-alligator-alcatraz-back-after-appeals-court-halts-judges-order                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Model B:  Claude Summary | A federal appeals court voted 2-1 to halt a lower court judge's order that would have ended operations at the "Alligator Alcatraz" immigration detention center in Florida's Everglades, allowing the facility to resume holding migrant detainees while the appeal process continues. The controversial facility, built quickly by Governor Ron DeSantis's administration in June at a single-runway training airport in the Everglades to support President Trump's mass deportation efforts, had faced a preliminary injunction from U.S. District Judge Kathleen Williams requiring operations to wind down by October and detainees to be transferred elsewhere. Environmental groups including Friends of the Everglades, the Center for Biological Diversity, and the Miccosukee Tribe had successfully argued that the facility violated federal environmental review requirements for the sensitive wetlands ecosystem. While DeSantis celebrated the appeals court decision saying "Alligator Alcatraz is open for business" and the Department of Homeland Security called it a victory against "open-borders activists," environmental advocates described it as devastating for the Everglades and vowed to continue their legal fight to ultimately shut down what they consider an ill-conceived facility causing ecological harm.<br> |

---

| Outlet                   | El Pais                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Title/Author/Date        | *Un tribunal de apelaciones permite que el centro de detención Alligator Alcatraz siga operando* <br>by Nicholas Dale Leal, El Pais<br>Publication Date: 2025-09-04<br>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Country                  | ES                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| URL                      | https://elpais.com/us/migracion/2025-09-05/un-tribunal-de-apelaciones-permite-que-el-centro-de-detencion-alligator-alcatraz-siga-operando.html                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Model B:  Claude Summary | Un tribunal federal de apelaciones ordenó suspender la decisión de la jueza Kathleen Williams de poner fin a las operaciones de "Alligator Alcatraz," el controvertido centro de detención para migrantes en los Everglades de Florida, con un panel de tres jueces en Atlanta votando 2-1 para mantener en suspenso la orden de la jueza mientras se resuelve la apelación, argumentando que sirve al interés público. La instalación, que fue construida en solo una semana a finales de junio, había enfrentado una orden judicial preliminar el 21 de agosto que requería que las operaciones cesaran en un plazo de 60 días, con los detenidos transferidos a otros centros y el equipo removido, siguiendo una demanda de Friends of the Everglades, el Center for Biological Diversity y la tribu Miccosukee alegando violaciones de las leyes federales de revisión ambiental para la construcción en humedales sensibles. La administración republicana del gobernador Ron DeSantis construyó la instalación en una pista aérea aislada rodeada de humedales para apoyar los esfuerzos del presidente Donald Trump de deportar a migrantes indocumentados, con su ubicación remota en los Everglades diseñada como un elemento disuasorio contra fugas que le valió su apodo en referencia a la famosa prisión de la bahía de San Francisco. La instalación ganó atención significativa cuando Trump la visitó el día de la inauguración y sugirió que podría servir como modelo para futuros centros de detención a nivel nacional como parte de su plan para expandir la infraestructura de deportaciones, mientras el Departamento de Seguridad Nacional celebró el fallo del jueves como una victoria para "el pueblo estadounidense, el estado de derecho y el sentido común" contra lo que caracterizaron como "activistas de fronteras abiertas" que intentan impedir que las fuerzas del orden remuevan a criminales peligrosos de las comunidades.<br> |

---

| Outlet                   | BBC News                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Title/Author/Date        | *'Alligator Alcatraz' immigration centre can stay open, appeals court rules* <br>by Jude Sheerin, BBC News<br>Publication Date: 2025-09-04                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Country                  | UK                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| URL                      | https://www.bbc.com/news/articles/crl5ry3rgzro                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Model B:  Claude Summary | A federal appeals court in Atlanta overturned a lower court order that would have shut down "Alligator Alcatraz," an immigration detention facility located in Florida's Everglades, allowing it to continue operations. The 2-1 ruling by Trump-appointed judges granted Florida and the Department of Homeland Security's request to block an injunction while litigation continues, with the court concluding that officials would likely succeed in arguing the facility isn't subject to federal environmental review requirements since it hasn't received federal funding. The controversy centers around a converted airport in the UNESCO World Heritage wetlands that was transformed into a detention center in July, with environmental groups and the Miccosukee Tribe arguing it should have undergone proper environmental assessments before opening. While Florida Governor Ron DeSantis celebrated the decision and the Department of Homeland Security called it a victory for law enforcement, environmental advocates described it as a devastating blow to the Everglades ecosystem and indicated the legal battle would continue.<br> |

---

| Outlet                  | AP News                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Title/Author/Date       | *Appeals court panel stops order to wind down operations at ‘Alligator Alcatraz’ in Everglades*<br>Mike Schneider, AP News<br>Publication Date: 2025-09-04                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Country                 | USA                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| URL                     | https://apnews.com/article/florida-immigration-alligator-alcatraz-1a7138a46272a8c9a2fb59ddc5eed4f6                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Model B: Claude Summary | A federal appeals court panel in Atlanta voted 2-1 to stay a lower court judge's order that would have ended operations at the "Alligator Alcatraz" immigration detention center in Florida's Everglades by the end of October, allowing the facility to continue holding detainees while the appeal process unfolds. U.S. District Judge Kathleen Williams had issued a preliminary injunction requiring the facility to wind down operations, transfer detainees elsewhere, and remove equipment and fencing following a lawsuit by Friends of the Everglades, the Center for Biological Diversity, and the Miccosukee Tribe, who argued that state and federal officials violated environmental review requirements for construction in sensitive wetlands. The facility was rapidly constructed by Governor Ron DeSantis's administration in late June on an isolated airstrip to support President Trump's deportation efforts, with its remote Everglades location deliberately chosen as an escape deterrent similar to the California island prison it was named after. The appeals court majority accepted arguments from state and federal defendants that environmental impact requirements don't apply since the federal government hasn't spent money to build or operate the facility despite Florida seeking federal grant funding, while Trump, who toured the facility in July and suggested it as a nationwide model, and DeSantis celebrated the ruling as keeping the detention center "open for business" against what DHS characterized as attempts by "open-borders activists" to hinder law enforcement.<br> |

---

| Outlet                  | Reuters News                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Title/Author/Date       | *'Alligator Alcatraz' operations may continue, divided US appeals court rules*<br>By Dietrich Knauth, Reuters news                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Country                 | EU                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| URL                     | https://www.reuters.com/legal/government/alligator-alcatraz-operations-may-continue-divided-us-appeals-court-rules-2025-09-04                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Model B: Claude Summary | The 11th U.S. Circuit Court of Appeals ruled in a split decision to allow the "Alligator Alcatraz" migrant detention center in Florida to resume operations, blocking a lower court order that had halted new detainee intake and construction work. The facility, which cost $250 million to build and covers over 18 acres at a former airport site 37 miles west of Miami, is strategically located in subtropical wetlands surrounded by Big Cypress National Preserve and Everglades National Park, where alligators, crocodiles, and pythons create imagery the White House has leveraged to demonstrate immigration enforcement determination. The appeals court's majority opinion sided with the Trump administration against environmental groups Friends of the Everglades and the Center for Biological Diversity, ruling that since Florida funded the project without federal construction funds, it didn't require federal environmental review despite promises from Governor DeSantis and DHS Secretary Kristi Noem that the federal government would pay for expansion. Trump, who toured the facility and called it a template for nationwide implementation, described it as housing "some of the most menacing migrants—some of the most vicious people on the planet," while the facility has detained 900 migrants so far and could potentially house thousands, making it central to his aggressive immigration enforcement agenda that has defined his political platform for a decade.<br> |

*Table 9.  Alignment excerpts (six outlets) with one AI summarization.*

#### Rubric Analysis ( Six outlets - Summary Journalism & News) 
The next table applies the NFAF rubric dimensions to the journalism case.  
It highlights how source signals (regional stance, figurative density, cultural references, emotional tone, and structural coverage) are transformed in summarization.  

| Rubric Dimension         | Source Signal (Regional Coverage)                                                   | Expected Flattening (Summarization)              | **Model B: Claude (Observed across regions)**                                                                                                                                                                      |
| ------------------------ | ----------------------------------------------------------------------------------- | ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Rhythm & Cadence**     | Mix of leads, quotes, attribution; outlet-specific sentence rhythms                 | Simplified syntax; more uniform declaratives     | **Mostly** cadence flattening, but not uniform: variance drops for **Fox** and **BBC**, is roughly unchanged for **Guardian**, and **spikes upward** for **AP** and **Reuters** (over-segmentation/fragmentation). |
| **Figurative Density**   | Evaluatives (“controversial,” “victory,” “grave ecological damage”); charged quotes | Removal/paraphrase of charged language           | Figurative language is **routinely neutralized or paraphrased** (“heartbreaking blow” → “difficult outcome”).                                                                                                      |
| **Cultural Register**    | Local markers: Everglades, Miccosukee Tribe, EU framing; partisan labels            | Generalization into generic categories           | Cultural specifics are **often generalized/omitted**; outputs tend toward generic “authorities vs. migrants” framing.                                                                                              |
| **Emotional Intensity**  | Outlet stance varies (humanitarian, enforcement, procedural)                        | “Balanced” reframing; smoothed edges             | **Tone neutralized**; affective edges softened into procedural/legal phrasing.                                                                                                                                     |
| **Coverage & Structure** | 500–750 tokens; several quotes; multi-actor attributions                            | 30–50% length; fewer actors; many-to-one fusions | **Heavy compression** (~40–55% of source). **Most quotes reduced but not eliminated** (0–3 retained per piece). Stakeholder voices **thinned** rather than fully erased.                                           |
| **Indicators**           | Distinct outlet stances and cultural signals                                        | Homogenized “centroid news” voice                | **Erosion** (stance neutralization, cultural generalization) with **Omission/Compression** (coverage loss). Cadence flattening **often** present but **not universal** with Claude.                                |

*Table 10. Rubric Analysis for Journalism & News example using six outlets by one AI summarization.*

---

This table provides outlet-specific notes that trace exactly what was lost or neutralized in each case.  
By comparing sources to Model B outputs, the table makes visible the omission of partisan framing, cultural markers, and regional context.  
Together, these notes show how plural journalistic registers converged on a single, neutralized narrative.

| ID                   | Flattening_Notes                                                                                                                                                                                                                                                                                                         |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **01 Guardian (AU)** | Coverage compressed (**577→313, −46%**). Quotes **1→1** (unchanged). Cadence roughly flat (**σ² 454.0→458.1, +4.1**). Regional color toned down; stance language softened (e.g.: _“controversial” → “facility”_).                                                                                                        |
| **02 Fox (USA)**     | Coverage compressed (**631→312, −51%**). Quotes **8→3** (kept a few). Cadence **flattens** (**σ² 355.3→346.0, −9.3**). Partisan markers largely neutralized.                                                                                                                                                             |
| **03 El País (ES)**  | Coverage **modestly** compressed (**747→634, −15%**). Quotes **5→6** (_approx.; heuristic over punctuation_). Cadence **spikier** (**σ² 602.1→771.0, +168.9**). Cultural refs reduced (e.g., Everglades/Miccosukee −2); stance markers slightly **added** (+1), indicating mild **speculative addition/canonical pull**. |
| **04 BBC (UK)**      | Coverage compressed (**502→299, −40%**). Quotes **6→2**. Cadence **flattens** (**σ² 300.7→246.2, −54.5**). Procedural frame preserved; details pared back.                                                                                                                                                               |
| **05 AP (USA)**      | Coverage compressed (**715→355, −50%**). Quotes **8→3**. Cadence **disrupted/spikier** (**σ² 208.3→685.8, +477.5**), suggesting fragmentation alongside longer sentences.                                                                                                                                                |
| **06 Reuters (EU)**  | Coverage compressed (**734→333, −55%**). Quotes **8→2**. Cadence **spikier** (**σ² 468.0→544.2, +76.2**). International frame narrowed toward US-centric phrasing.                                                                                                                                                       |

*Table 11. Flattening Notes for Journalism & News (Summarization) example using six outlets.*


**Observed:**
- **Model B (Claude)** neutralizes stance (**Erosion**), compresses coverage (**Omission/Compression**), and erases cultural specificity (**Cultural Register flattening**).
- Distinct voices: progressive (_Guardian_), conservative (_Fox_), European (_Reuters_), Spanish/Latino (_El País_), and neutral/procedural (_BBC_, _AP_) collapse into a single **centroid news register.**
- While Claude occasionally retains one or two direct quotes, the overall pattern  tends toward neutralization, partisan identifiers omitted, and cultural references erased.
- In journalistic contexts, flattening manifests not as loss of literary style (as in _Emma_ ch1) but as the **erasure of editorial diversity and stance plurality** in the public sphere.
- This aligns with the rubric dimensions of **Cultural Register (§7.4)**, **Emotional Intensity (§7.5)**, and **Coverage & Structure (§7.6)**, alongside cadence convergence (**Cadence & Rhythm §7.1**).

**NFAF** does not automatically classify shorter length as flattening. Instead, stakeholders may diagnose flattening when compression disproportionately erases stance markers, cultural references, or actor voices essential to narrative diversity.

**Note:** Summarization inherently involves compression. **NFAF** does not prescribe thresholds for acceptable loss; responsibility for diagnosis resides with the stakeholder.

---

### 9.3 Law (Case T-612/17 para. 27 & 704 - Translation) 
*NFAF evaluates outputs, not actors; the aim is transparency around transformation effects.*

- **Domain:** Law
- **Focus:** Jurisdictional flattening (legal register + statutory anchors)
- **EX03 version:** v01

**Source:** Court of Justice of the EU, Case T-612/17 (*Google v Commission*), Judgment excerpt, para. 27 and 704 (public domain).  
**Mediation:** EN → ES by DeepL, with comparison to official EUR-Lex ES translation, then back-translation (ES → EN by DeepL).
**Data:** Data files are located at ./examples_ejemplos/EX03_Law_Legal  
**Summary Finding:**  
In this example, translation drift emerges less through omission and more through **tense/aspect smoothing** and **register dilution.** In para. 27, DeepL’s choice of _llegaba_ (imperfect) instead of the legal pluperfect _había llegado_ weakens the finality of the Commission’s provisional conclusion. In para. 704, the official Spanish preserves civil law procedural anchors (_petitum_, _subsidiario_), while DeepL collapses these into the Anglophone-generic “alternative claim.” Across both, the outputs converge toward a simplified register that can attenuate the juridical weight of decisions. Whether this constitutes flattening is a stakeholder judgment. 
The stakeholders need to evaluate this instance of **jurisdictional flattening.**

**Sequence**
- **Input Selection & Baseline Identification:** Court of Justice of the EU, Case T-612/17 (*Google v Commission*)    
- **Transformation:** AI-mediated translation + back-translation    
- **Alignment:** paragraph-level   
- **Drift Assessment & Rubric Scoring:** qualitative (tense, aspect, register)  
- **Pattern Analysis:** jurisdictional flattening  
- **Human-in-the-Loop Review:** REQUIRED in high-stakes (legal context), note - alignment and analysis perform by human  
- **Reporting:** rubric table + flattening notes 

This table presents selected alignment excerpts from the European Commission’s antitrust decision in the _Google Shopping_ (Court of Justice of the EU, Case T-612/17) case. The passages were first translated from English into Spanish using DeepL, then back-translated into English using DeepL. Placing the source, translation, and back-translation side by side makes it possible to detect subtle divergences at the level of aspect, tense, and legal register. These small shifts illustrate how even high-fidelity translation systems may reconfigure **binding force** in legal texts.

| **Paragraph** | **Source EN**                                                                                                                               | **Official ES**                                                                                                                                                           | **Model D:** DeepL EN→ES                                                                                                                 | **Model D:** DeepL ES→EN (Back-EN)                                                                         | **Observed Drift**                                                                                                                                                                                                                                                    |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **27**        | “…adopted a statement of objections … in which **it reached the provisional conclusion** that the practices at issue constituted an abuse…” | “…notificó a Google el pliego de cargos, en el que **había llegado, con carácter provisional, a la conclusión** de que las prácticas… constituían un abuso…”              | “…adoptó un pliego de cargos … en el que **llegaba a la conclusión provisional** de que las prácticas en cuestión constituían un abuso…” | “…in which it **provisionally concluded** that the practices… constituted an abuse…”               | **Aspect drift**: Source “reached” (perfective, decisive) → DeepL “llegaba” (imperfective, ongoing). Legal weight of finality softened. Stakeholders may diagnose this as flattening because it alters the **decisional force** of the Commission’s act.              |
| **704**       | “Consequently, the **claim put forward in the alternative** for annulment or reduction of the fine must be rejected.”                       | “Por lo tanto, procede desestimar **el punto del petitum** … en el que se solicita, **con carácter subsidiario**, la supresión de la multa o la reducción de su importe.” | “Por consiguiente, debe desestimarse **la pretensión subsidiaria** de anulación o reducción de la multa.”                                | “Consequently, the **alternative claim** for annulment or reduction of the fine must be rejected.” | **Register drift**: Official ES encodes civil law procedure (_petitum_, “subsidiary”). DeepL generalizes to “pretensión subsidiaria,” back to “alternative claim.” Loss of **documentary anchor** + **procedural nuance**. Flattened into Anglophone-generic “claim.” |

*Table 12. Alignment excerpt (Law, Para. 27 & 704), showing EN source, official ES, DeepL ES, and back-translation.*

#### Rubric Analysis (Case T-612/17 para. 27 & 704 - Translation) 
The following rubric table applies the **NFAF categories** to the law example, focusing on structural alignment, semantic drift, and register. Unlike literature or journalism, the legal domain foregrounds **precision in modality and aspect**: a single verb choice may carry significant interpretive weight. The analysis highlights how DeepL’s outputs handle these features, and where flattening may emerge.

| **Rubric Dimension**     | **Source Signal (EN → ES official)**                                          | **Expected Flattening (Translation)**                    | **DeepL (Observed)**                                                                                                                          |
| ------------------------ | ----------------------------------------------------------------------------- | -------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| **Cadence & Rhythm**     | Decisive, bounded clause (“reached the provisional conclusion”).              | Possible smoothing into less final cadence.              | Para. 27: perfective “reached” → imperfective _llegaba_. Weakens closure, reads as ongoing.                                                   |
| **Lexical Richness**     | Legal collocations fixed: “provisional conclusion”; “petitum”; “subsidiario.” | Neutralization of specialized legal lexis.               | Para. 27: “controvertidas” → “en cuestión.” Para. 704: _petitum_ dropped; _subsidiario_ generalized to “alternative claim.”                   |
| **Cultural Register**    | EU procedural formulas (Latinisms, juridical connectors like _por ende_).     | Drift toward generic logical markers.                    | Para. 704: _por ende_ → _por lo tanto_. Loss of civil law resonance, alignment with conversational register.                                  |
| **Coverage & Structure** | Unified clause tying act to consequence (abuse finding → infringement).       | Temporal or structural drift.                            | Para. 27: Aspectual shift makes conclusion sound provisional as an act, not just as a status. Structure preserved but temporal force diluted. |
| **Emotional Intensity**  | None (strictly procedural).                                                   | No expected flattening; tone neutral.                    | Neutrality maintained.                                                                                                                        |
| **Indicators**           | Legal force depends on verb aspect + statutory anchors.                       | Aspectual or register shifts dilute perceived authority. | Jurisdictional flattening visible: imperfect aspect + loss of procedural anchors erode sense of decisional finality.                          |

*Table 13. Rubric Analysis for Law (Translation, para. 27 & 704, EN→ES→EN via DeepL).*

**Observed:**
- **Tense/Aspect Shift:** _Reached_ (perfective, decisive) → _llegaba_ (imperfective, ongoing). This shift weakens juridical finality by recasting a settled conclusion as a process still in motion. 
- **Register Drift:** _Controvertidas_ (specialized legal register) → _en cuestión_ (everyday descriptive). The specialized judicial tone is diluted into a generic phrasing.
- **Connector Flattening:** _Por ende_ (formal, judicial connective) → _por lo tanto_ (neutral logical link). A procedural marker is reduced to a common logical transition, flattening institutional register.
- **Agency Drift (Back-EN):** Source stresses the _act of reaching a provisional conclusion_; back-translation reframes this as _provisionally concluding_, shifting the provisionality from the **status of the conclusion** to the **Commission’s action.**

---

This table synthesizes observed divergences into interpretive notes. The focus is not on overt mistranslation but on **jurisdictional flattening**: a gradual leveling of legal force through subtle choices in tense and register. The notes stress that such flattening does not nullify meaning but may dilute the perception of **finality, authority, or closure** within the legal discourse. These examples demonstrate how NFAF can be extended beyond literature and journalism to systematically interrogate flattening in the legal domain.

| Excerpt / Focus                                                                                        | Observed Drift                                                                                                      | Flattening Note                                                                                                                                | NFAF Dimensions                                   |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------- |
| **Para. 27: “it reached the provisional conclusion” → “que llegaba a la conclusión provisional”**      | Aspect drift: perfective → imperfective (_reached_ → _llegaba_). Back-EN: “provisionally concluded.”                | Jurisdictional flattening: a binding act reframed as an ongoing process. Weakens closure of Commission’s decision.                             | §7.4 Cultural Register, §7.6 Coverage & Structure |
| **Para. 704: “claim put forward in the alternative” → “pretensión subsidiaria” → “alternative claim”** | Loss of civil law anchors (_petitum_, _subsidiario_ nuance). Generalized into Anglophone-style “alternative claim.” | Register flattening: procedural precision compressed into generic claim language. Juridical specificity of the EU civil law context is erased. | §7.2 Structural Drift, §7.4 Cultural Register     |
| **Back-translation echo**                                                                              | Imperfective nuance and generalized register reappear in EN, fixing flattening into the text cycle.                 | Demonstrates how subtle shifts propagate across mediation chains, entrenching a “centroid” Anglophone legal style.                             | §7.2 Structural Drift                             |
| **Implication for stakeholders**                                                                       | Legal experts must assess whether aspect/register shifts alter enforceability or interpretation of rulings.         | NFAF leaves thresholds to stakeholders: here flattening is domain-specific, requiring legal judgment to determine materiality.                 | §8 Stakeholder Diagnostics                        |

*Table 14: Flattening Notes for Law (Translation & Back-Translation)*

**Interpretation:**  
In this example for the legal domain, flattening does not appear as stylistic erosion (as in literature) or stance neutralization (as in journalism). Instead, it manifests as **jurisdictional flattening**: the subtle weakening of legal force through aspectual smoothing, register dilution, and loss of procedural anchors. An imperfect verb (_llegaba_) or the substitution of _petitum_ with “alternative claim” does not erase meaning, but it shifts the perceived **finality and authority** of the text toward a more generic Anglophone legal style. Such drift is not inherently “error,” but it carries stakes: legal stakeholders must judge whether the flattening materially alters interpretation or enforceability.

---

### 9.4 Cross-Domain Applications 

**NFAF** is not limited to the examples in (§9); it can be applied across different domains, each with its own focus, mediation type, and common flattening pattern.

The following table illustrates representative domains where NFAF has been or can be applied. Each domain suggests a likely mediation type and flattening pattern. These are **illustrative only** and are not exhaustive or prescriptive.  

| **Domain**               | **Focus**                                                                              | **Mediation Type**               | **Pattern Statement**                                                                                                                                                                                               |
| ------------------------ | -------------------------------------------------------------------------------------- | -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Literature               | Stylistic flattening (voice/cadence)                                                   | Translation                      | *AI-mediated translation commonly flattens **Cadence & Rhythm** (§7.1) and **Emotional Intensity** (§7.5), neutralizing stylistic signatures and converging toward standardized modern prose.*                      |
| Journalism & News        | Cultural flattening (journalistic stance)                                              | Summarization                    | *AI-mediated summarization often flattens **Cultural Register** (§7.4), reducing partisan, regional, and evaluative markers into a globally standardized news register.*                                            |
| Law                      | Jurisdictional flattening (legal register + statutory anchors)                         | Translation                      | *AI-mediated translation may reduce **Coverage & Structure** (§7.6) and **Lexical Richness** (§7.2), compressing argumentation and erasing jurisdictional nuance into globally legible but less precise registers.* |
| Culture & Representation | Flattening of cultural/historical narratives into generalized, globally neutral frames | Summarization / Image Generation | *AI-mediated summarization collapses **Cultural Register** (§7.4), stripping contextual markers and diluting temporal depth, converging situated perspectives into linear, event-focused accounts.*                 |
| Historical & Archival    | Temporal register shifts; anachronistic insertions in historical texts                 | Rewriting                        | *AI-mediated rewriting alters **Coverage & Structure** (§7.6), introducing anachronistic simplifications that flatten historical narratives.*                                                                       |
| Scientific Publications  | Conceptual flattening (specialized registers)                                          | Rewriting                        | *AI-mediated rewriting reduces **Lexical Richness** (§7.2) and **Figurative Density** (§7.3), simplifying terminology and neutralizing disciplinary nuance into generalized, lay-accessible prose.*                 |

*Table 15. Cross-domain applications of NFAF, showing representative domains, mediation types, and example flattening patterns (illustrative only).*


---

## 10. Extensions: NFAF Domain-Emergent Flattening Across Domains - Illustrative, not exhaustive.
While NFAF v0.5.0 focuses on **AI-mediated flattening**, the framework also highlights the potential to study **domain-emergent flattening**: cases where professional practices themselves flatten narrative voice, stance, or meaning.  
These extensions are illustrative only and **outside the normative scope of this document.** 
Future versions (e.g., NFAF-J, NFAF-L, NFAF-P) may formalize and add different domains.  

### 10.1 Journalism (NFAF-J) - Illustrative 
- **Signals:** Balance markers, stance framing, partisan vs. neutral lexicon.  
- **Pattern Statement:** Journalistic practices may create **false balance**, neutralize stance, or converge reporting into a **globalized news register.**  
- **Status:** Out of scope for NFAF v0.5.0; possible extension.  

### 10.2 Law (NFAF-L) - Illustrative 
- **Signals:** Testimony scaffolding, legal citations, register fidelity.  
- **Pattern Statement:** Judicial practices may compress testimony, omit narrative context, or erode nuance in written opinions.  
- **Status:** Out of scope for NFAF v0.5.0; possible extension.  

### 10.3 Politics (NFAF-P) - Illustrative 
- **Signals:** Issue framing, sloganization, binary simplification.  
- **Pattern Statement:** Political discourse often simplifies complex issues into **binary framings** (e.g., for/against), flattening deliberative nuance.  
- **Status:** Out of scope for NFAF v0.5.0; possible extension.  

---     

## 11. References 
Bal, Mieke. 1985. _Narratology: Introduction to the Theory of Narrative_. Toronto: University of Toronto Press.

Bender, Emily M., Timnit Gebru, Angelina McMillan-Major, and Shmargaret Shmitchell. 2021. “On the Dangers of Stochastic Parrots: Can Language Models Be Too Big?” In _Proceedings of the 2021 ACM Conference on Fairness, Accountability, and Transparency (FAccT ’21)_.

Berman, Antoine. 2000. Translation and the trials of the foreign. In L. Venuti (Ed.), _The Translation Studies Reader_ (pp. 284–297). Routledge.

Burrows, John. 2002. “Delta: A Measure of Stylistic Difference and a Guide to Likely Authorship.” _Literary and Linguistic Computing_ 17 (3): 267–287.

Cronin, Michael. 2003. _Translation and Globalization_. London: Routledge.

Dankers, Verna, Marek Rei, and Ekaterina Shutova. 2019. “Modelling the Interplay of Metaphor and Emotion through Multitask Learning.” In _Proceedings of the 57th Annual Meeting of the Association for Computational Linguistics (ACL)_, 2218–2229.

Drucker, Johanna. 2014. _Graphesis: Visual Forms of Knowledge Production_. Cambridge, MA: Harvard University Press.

Fast, Ethan, Binbin Chen, and Michael S. Bernstein. 2016. “Empath: Understanding Topic Signals in Large-Scale Text.” In _Proceedings of the 2016 CHI Conference on Human Factors in Computing Systems_, 4647–4657. New York: ACM.

Gale, William A., and Kenneth W. Church. 1993. “A Program for Aligning Sentences in Bilingual Corpora.” _Computational Linguistics_ 19 (1): 75–102.

Genette, Gérard. 1980. _Narrative Discourse: An Essay in Method_. Ithaca: Cornell University Press.

Hall, Stuart. 1980. “Encoding/Decoding.” In _Culture, Media, Language_. London: Routledge.

Hamilton, William L., Jure Leskovec, and Dan Jurafsky. 2016. “Diachronic Word Embeddings Reveal Statistical Laws of Semantic Change.” In _Proceedings of the 54th Annual Meeting of the Association for Computational Linguistics (ACL)_.

Johnson, Melvin, Mike Schuster, Quoc V. Le, Maxim Krikun, Yonghui Wu, Zhifeng Chen, Nikhil Thorat, et al. 2017. “Google’s Multilingual Neural Machine Translation System: Enabling Zero-Shot Translation.” _Transactions of the Association for Computational Linguistics_ 5: 339–351.

Jockers, Matthew L. 2013. _Macroanalysis: Digital Methods and Literary History_. Urbana: University of Illinois Press.

Koehn, Philipp. 2009. _Statistical Machine Translation_. Cambridge: Cambridge University Press.

Leech, Geoffrey, and Mick Short. 1981. _Style in Fiction_. London: Longman.

Lin, Chin-Yew. 2004. “ROUGE: A Package for Automatic Evaluation of Summaries.” In _Text Summarization Branches Out: Proceedings of the ACL-04 Workshop_, 74–81.

Mann, William C., and Sandra A. Thompson. 1988. “Rhetorical Structure Theory: Toward a Functional Theory of Text Organization.” _Text_ 8 (3): 243–281.

McEnery, Tony, and Andrew Hardie. 2012. _Corpus Linguistics: Method, Theory and Practice_. Cambridge: Cambridge University Press.

Menocal, María Rosa. 2002. _The Ornament of the World: How Muslims, Jews, and Christians Created a Culture of Tolerance in Medieval Spain_. Boston: Little, Brown.

Mitchell, Margaret. 2021. “Bias and Fairness in Natural Language Processing.” _AI Magazine_ 42 (3): 36–52.

Mohammad, Saif M., and Peter D. Turney. 2013. “Crowdsourcing a Word–Emotion Association Lexicon.” _Computational Intelligence_ 29 (3): 436–465.

Moretti, Franco. 2013. _Distant Reading_. London: Verso.

Papineni, Kishore, Salim Roukos, Todd Ward, and Wei-Jing Zhu. 2002. “BLEU: A Method for Automatic Evaluation of Machine Translation.” In _Proceedings of the 40th Annual Meeting of the Association for Computational Linguistics (ACL)_, 311–318.

Pennebaker, James W., Martha E. Francis, and Roger J. Booth. 2001. _Linguistic Inquiry and Word Count: LIWC 2001_. Mahwah, NJ: Lawrence Erlbaum Associates.

Popović, M., Toral, A., & Sánchez-Cartagena, V. 2016. _Impact of translationese on machine translation performance_. Proceedings of the 19th Annual Conference of the European Association for Machine Translation (EAMT 2016).

Ramsay, Stephen. 2011. _Reading Machines: Toward an Algorithmic Criticism_. Urbana: University of Illinois Press.

Ryan, Marie-Laure. 2004. _Narrative as Virtual Reality_. Baltimore: Johns Hopkins University Press.

Santoyo, Julio-César. 2009. _A través del espejo: estudios de traducción en la Edad Media_. León: Universidad de León.

Schneider, B. 2022. _Multilingualism and AI: The regimentation of language in the age of digital capitalism_. Signs and Society, 10(3), 362–387. https://doi.org/10.1086/721757

Shutova, Ekaterina. 2010. “Models of Metaphor in NLP.” In _Proceedings of the 48th Annual Meeting of the Association for Computational Linguistics (ACL)_.

Spivak, G. C. 2000. "The politics of translation". In L. Venuti (Ed.), _The Translation Studies Reader_ (pp. 397–416). Routledge.

Stamatatos, Efstathios. 2009. “A Survey of Modern Authorship Attribution Methods.” _Journal of the American Society for Information Science and Technology_ 60 (3): 538–556.

Toury, Gideon. 1995. _Descriptive Translation Studies and Beyond_. Amsterdam: John Benjamins.

Torres, C., & Ramos, I. 2018. _Anglicisms in Portuguese translations: Evidence from EU institutional texts_. Meta, 63(2), 456–476.

van Dijk, Teun A. 2008. _Discourse and Context: A Sociocognitive Approach_. Cambridge: Cambridge University Press.

Vanmassenhove, E., & Shterionov, D. 2019. _Lost in translation: Loss of lexical richness in neural machine translation_. Proceedings of Machine Translation Summit XVII, Dublin.

Venuti, Lawrence. 1995. _The Translator’s Invisibility: A History of Translation_. London: Routledge.

Vieira, L. N. 2023. _Translation infrastructures in the age of AI. Translation Studies_, 16(1), 1–18.


---

## 12. Appendix: Citation Formats 
If you use or reference this framework, please cite:

```bibtex
@software{helton_nfaf_2025,
  author       = {Helton, Johennie},
  title        = {NFAF: Narrative Flattening Analysis Framework (v0.4.1)},
  year         = 2025,
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.16885076},
  url          = {https://doi.org/10.5281/zenodo.16885076}
}
