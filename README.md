# NFAF: Narrative Flattening Analysis Framework

**Author:** Johennie Helton  
**Status:** Public Specification (v0.4.0)  

---
## Citation & Authorship  

If you reference this framework in research or teaching, please cite as follows:  

Helton, J. (2025). *NFAF: Narrative Flattening Analysis Framework* (v0.4.0). Zenodo.  
https://doi.org/10.5281/zenodo.16885076  

*Note: Citation shown in APA style. Please adapt as needed for MLA, Chicago, or other formats.*  

### Persistent Identifiers

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.16885076.svg)](https://doi.org/10.5281/zenodo.16885076)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0003--2175--3239-green?logo=orcid)](https://orcid.org/0009-0003-2175-3239)

---

## 1. Abstract <br>
**NFAF (Narrative Flattening Analysis Framework)** is a modular analytical method for detecting and analyzing how AI-mediated transformations (translation, summarization, rewriting, and related processes) reduce a narrative's distinctiveness. It defines flattening as the erosion, compression, or homogenization of narrative voice, stylistic texture, and cultural signals, and provides a rubric of indicators to make those changes visible: cadence & rhythm, lexical richness, figurative density, cultural register, emotional intensity, and structural coverage (extent to which narrative elements are preserved or omitted). Grounded in narratology, translation theory, digital humanities, and NLP, NFAF offers a replicable way to analyze where and how AI outputs converge toward neutral, "centroid" language at the cost of nuance.

| **Category**                | **Indicators**                                                                                                                                                                                                  |
| --------------------------- |-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Structural & alignment**  | - Structural drift <br>- Segment Omission <br>- Dialogue Flattening <br>- Event Compression/Collapsing <br>- Discourse Link Collapse                                                                            |
| **Cadence**                 | - Homogenized cadence <br>- Flattened pacing <br>- Loss of prosodic/flattened pacing markers                                                                                                                    |
| **Stylistic**               | - Loss of idiomatic expressions <br>- Quotation loss / paraphrase masking <br>- Neutralized or homogenized register                                                                                             |
| **Semantic & interpretive** | - Semantic drift <br>- Neutralization of emotional tone <br>- Over-generalization <br>- Premature disambiguation (over-specificity) <br>- Canonical pull* <br>- Domain transfer <br>- Back-translation mismatch |
|                             |                                                                                                                                                                                                                 |
_Table 1. Categories of narrative flattening and their indicators._ 
<br>*Canonical pull = tendency of AI systems to gravitate toward standardized or widely circulated formulations, overriding text-specific variation.*

**NFAF is designed as a modular framework with a common theoretical and methodological core that can be adapted to domain-specific requirements.** For example, literary analysis may prioritize voice preservation and cultural authenticity, legal applications may emphasize semantic precision and structural fidelity, and journalism may balance accessibility with source integrity. This modularity enables specialized implementations (e.g., Literature, Law) while maintaining consistent analytical stages and ethical principles. In this way, NFAF supports both domain-specific inquiry and cross-disciplinary comparison, ensuring coherence while allowing for flexible thresholds, indicator weightings, and acceptability criteria. 

---

## 2. Introduction

The **Narrative Flattening Analysis Framework (NFAF)** is a method for detecting and analyzing the loss, convergence, or homogenization of cultural, emotional, and stylistic features in narratives transformed by machine translation, summarization, rewriting, or other AI-mediated processes. These transformations often reflect algorithmic optimization toward **neutral, generalized, or centroid language** outputs that may appear universally “fluent” but are less contextually situated.

Narrative is defined here in its broadest sense encompassing literary, journalistic, legal, scientific, and cultural domains. Narratives carry rhythm and variance, like a heartbeat, and AI mediation often reduces these peaks and valleys into a steady line. NFAF makes such reductions visible by combining modular stages: alignment, semantic drift detection, as well as qualitative and quantitative analysis. This structure enables reviewers to identify losses or homogenizations, including subtle or cumulative cultural, political, or semantic shifts, while remaining adaptable to domain-specific needs.

NFAF is designed to test, document, and measure where flattening occurs while deliberately avoiding prescriptive thresholds or universal acceptability criteria. A reduction in variance that signals voice loss in literature, for example, may constitute acceptable compression in legal summarization. Interpretation must therefore be guided by domain expertise, use case requirements, and stakeholder values.

Comparable critiques of homogenization can be found across fields, from translation studies (Berman 1985; Venuti 1995) to digital humanities and media theory (Drucker 2014), where questions of voice, context, and interpretive neutrality have long been central. NFAF complements rather than replaces metrics such as BLEU or ROUGE, focusing instead on dimensions of meaning preservation that surface-level similarity measures cannot capture. The following sections define NFAF’s key concepts and analytic dimensions, outlining the indicators and stages that make flattening measurable across different domains and mediation types.

**Current focus:** Applying NFAF to *narrative voice in literary text*, with emphasis on preserving cultural and emotional signals in AI-mediated transformation.

Note: NFAF is published as pre-existing intellectual property of Johennie Helton. This specification is provided for research and citation purposes only. **No rights to implement, commercialize, or assume co-ownership of the framework are granted or implied.**

---
## 3. Definitions

**3.1. Narrative**<br>
A **narrative** is broadly defined as any structured account of events, experiences, or arguments - whether linguistic, visual, or multimodal - that conveys meaning through a deliberate sequence, specific framing, or a distinct voice. Defining a text as a narrative implies that its distinctive signals (voice, style, cultural cues) are not ancillary. Comparable broad definitions appear in narratology (Genette 1980; Bal 1985; Ryan 2004), where discourse and framing are central to how meaning is conveyed. Therefore, any mediation or transformation of a narrative must respect the integrity of these signals, ensuring that the original remains accessible alongside the modified version, thereby preventing erasure of voice or context. 

Narratives are not limited to literary texts; they also encompass diverse forms such as journalistic reporting, scientific writing, legal arguments, digital-born narratives, and cultural expressions. They can be linear or nonlinear, explicit or implicit, but they are always shaped by choices of form, style, and emphasis that reflect specific contexts and perspectives. 

---

**3.2. Narrative Flattening**<br>
**Narrative flattening** is the systematic reduction or distortion of a narrative's distinctiveness when mediated by artificial intelligence systems. It involves the erosion or inflation of signals that constitute a narrative's unique character, including voice, style, cultural references, and domain-specific markers of meaning. Because this process can erase human and cultural nuance, researchers, developers, and users should transparently disclose its presence and avoid presenting flattened outputs as neutral or universal.  
 
Comparable critiques are found in translation theory (Berman 1985; Venuti 1995), where mediation reshapes voice and culture. NFAF reframes these concerns as reproducible, algorithmic effects of AI mediation, echoing computational linguistics on semantic shift (Hamilton et al. 2016) and DH critiques of interpretive neutrality (Drucker 2014). **Flattening** can be observed in several recurrent forms:
- **Erosion:** The loss or weakening of key narrative elements, such as semantic nuance, stylistic rhythm, cultural references, or affective tone.
- **Inflation:** The insertion or exaggeration of generic features not present in the original text.
- **Inference (Speculative Addition):** The introduction of details absent from the source, often drawn from the AI's training data on canonical texts, precedent cases, or analogous contexts. This can prematurely resolve ambiguities in a way not supported by the original source.
- **Omission / Compression (context-dependent):** Removal or condensation of source segments (sentences, paragraphs, dialogue, quotations). In summarization, omission may be expected but should always be signaled to preserve accountability; in translation or rewriting, omission of substantive content is always flattening unless explicitly documented and justified.
<br>

Whether by erosion, inflation, inference, or omission, the result is the same: outputs that are more standardized, less contextually situated, and ultimately less distinctive at the cost of human voice and cultural nuance. The effects are evident across various domains: in literary contexts, it may appear as a homogenized rhythm or reduced figurative density;  in journalism, as genericized news summaries; and in law, as legally imprecise translations.

---

**3.3. Voice & Cadence Metrics** <br>
**Voice & Cadence Metrics** are quantitative measures used to assess a text's stylistic rhythm, pacing, and intensity, specifically to determine whether its narrative rises and falls are preserved during transformation. Since cadence itself conveys meaning, any reduction in rhythm or figurative density should be recognized as a loss rather than a "clarification." 

Examples of these metrics include sentence length variance (prose, journalism), figurative density (literary style, metaphor clusters), punctuation-based rhythm (legal clauses, journalistic headlines), and prosodic markers in poetry or dialogue (emphasis, turn-taking). Related methods in stylistics (Leech & Short 1981), quantitative poetics, and computational authorship studies (Burrows 2002; Stamatatos 2009) demonstrate how rhythm and figurative density carry meaning; NFAF adapts these approaches to detect flattening effects under AI-mediated transformation. 

---

**3.4. Centroid Pivot** <br>
**Centroid Pivot (CP)** is the general **mechanism** by which mediated processes, whether human or algorithmic, normalize inputs toward a culturally or statistically “central” form before producing outputs.  

```
    Input Language/Modality
          ↓
       [Centroid Pivot: either internal (black box) or external (relay)]
          ↓
    Central Form (linguistic, cultural, semiotic default)
          ↓
    Output Language/Modality
```
Notice that CP can be either: <br/>
(a) **internal (black box)** performed by the entity doing the mediation.<br/>
(b) **external** performed by different entities performing mediations in a chain/pipeline.<br/>

- In contemporary AI translation, this central form is often **Centroid English**, a statistical convergence created by Anglophone training data. Its surface expression is **Algorithmic English**, a normalized register that prioritizes fluency and universality over cultural or stylistic specificity. 

```
    French → [CP] → Centroid English → Spanish
    
        Input Language/Modality: French
          ↓
       [Centroid Pivot: internal (black box)]
          ↓
    Centroid English (linguistic, cultural, semiotic default): statistical, hidden via algorithm
          ↓
    Output Language/Modality: Spanish
    
    Here the Centroid Pivot is an internal relay step: it happens inside the model, not as a separate visible translation stage but leaves Anglicized traces. 
    
```
This is an example of CP being performed in an 'internal (black box)' fashion, performed by the entity doing the mediation. In this case the mediation is machine translation, performed by the entity doing the mediation (e.g. an AI model) and the pivot is toward a statistical, hidden Centroid English.

- In historical contexts, Centroid Pivot is visible in relay translation practices. A well-documented case is the Toledo School of Translators in 12th–13th century Spain, where Arabic works on science and philosophy were first rendered into **Castilian Spanish** and only then into Latin. Translation studies frame this as indirect or relay translation (Toury 1995), while cultural historians note how mediation at Toledo shaped what was preserved, neutralized, or erased (Menocal 2002; Santoyo 2009). NFAF situates this as an early precedent of Centroid Pivot: the systemic pull toward a dominant register that, by normalizing through an intermediate mode, risks overwriting nuance in both directions. 

```
    Arabic → [CP] → Castilian Spanish → Latin
    
            Input Language/Modality: Arabic
          ↓
       [Centroid Pivot: external,  Castilian oral mediation, visible]
          ↓
    Castilian Spanish (linguistic, cultural, semiotic default): intermediate text
          ↓
    Output Language/Modality: Latin
    
    The relay is external the mediation with oral intermediaries and leaves Spanish traces.
```
This is an example of CP being performed in an 'external' fashion, performed by a series of entities doing mediation steps. In this case the mediation is human translation, performed by a sequence of distinct mediators in a chain or relay (e.g. the Toledan translators), and the pivot is toward Castilian Spanish.

- In multimodal contexts, pivoting extends beyond text: visual systems may converge on dominant color palettes or composition styles; music systems may converge on standardized tunings or rhythms.  

NFAF emphasizes that Centroid Pivot is never neutral. It reflects the systemic pull of dominant linguistic, cultural, or semiotic defaults, which may erase or overwrite nuance from both source and target. In literary contexts, this tends to mean U.S./U.K. “Internet English”; in other contexts, different pivots may dominate.  

---

**3.5. Centroid English**
- **Centroid English** is the **statistical** form toward which large-scale AI systems converge. It represents the “average” linguistic point in a high-dimensional embedding space, weighted heavily by Anglophone training data, especially U.S./U.K. web sources. As such, Centroid English is not a natural language variety but a statistical centroid: a convergence of frequencies, distributions, and norms.

---

**3.6. Algorithmic English**
- **Algorithmic English** is the **register** that results when models express this statistical convergence in practice. It is a normalized linguistic style that prioritizes fluency, neutrality, and universality over cultural or stylistic specificity. When an AI-mediated process uses this register, it is essential to reference the original text and make the shift explicit so readers can discern what was standardized or lost. In technical contexts, Algorithmic English is sometimes equated with **Centroid English,** highlighting statistical convergence. In broader cultural discussions, it has been described as **'Internet English',** a globally flattened register shaped by large-scale web data, search engines, and social media. In computational terms, it parallels the convergence of language models toward “average” representations, noted in NLP research on bias and distributional smoothing (Bender et al. 2021; Mitchell 2021). Similar concerns arise in linguistics around “Global Englishes” and in Digital Humanities critiques of interpretive neutrality (Drucker 2014). NFAF emphasizes that these convergences are never neutral: they signal standardization at the cost of cultural nuance and stylistic voice.

---

**3.7. Drift** <br>
**Drift** refers to systematic shifts, whether intentional or emergent, that occur when a narrative is transformed, altering either its scaffold (structure and discourse relations) or its semantics (meaning and resonance).

- **Structural Drift** is the change to the narrative’s **scaffold,** the arrangement of segments, discourse relations (contrast, cause, elaboration), speaker turns, or quoted material. Ethical mediation requires preserving transparency of the scaffold so that shifts in discourse structure do not silently erase perspective. This category resonates with work on discourse structures and relations _Mann & Thompson (1988); van Dijk (2008)._ Structural drift manifests when scaffolding is altered without disclosure:
	- **Inflation:** addition of dialog, attributions, or text.
	- **Segment Omission:** missing dialog, attributions, or text (null alignment).
	- **Dialogue Flattening:** removal of speaker attributions or turns.
	- **Event Collapsing:** fusing steps that matter for meaning.
	
- **Semantic Drift** is the systematic or cumulative change in meaning that occurs between a source text and its transformed version. In this process surface fidelity is insufficient; ethical mediation requires documenting these hidden shifts so that ambiguity and nuance are not silently overwritten. Computational linguistics has studied semantic shift detection in diachronic corpora (Hamilton et al. 2016), but NFAF applies the idea to shifts introduced by AI mediation at the level of narrative meaning. Semantic drift can be observed at various levels:
	- **Lexical Drift:** The substitution, loss, or generalization of specific word choices.
	- **Syntactic Drift:** Shifts in sentence structure that can alter the original emphasis or rhythm.
	- **Pragmatic Drift:** Changes to the implied meaning, tone, or cultural resonance of the text.
	
	This notion aligns with linguistic theories of semantic change and with Digital Humanities accounts of interpretive “drift” in computational reading (Ramsay 2011; Jockers 2013), but NFAF applies it specifically to AI-mediated transformations.
  <br>

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
```

Both structural and semantic drift compromise narrative fidelity: structural drift compromises fidelity at the level of scaffold and discourse relations, while semantic drift compromises fidelity at the level of meaning and resonance. 

---

**3.8. Narrative Alignment**<br>
**Narrative alignment** refers to the segment or unit level mapping between a source and its transformed narrative. It enables side-by-side analysis, crucial for identifying differences, shifts, as well as omissions or additions in meaning. Alignment is also an accountability practice: it keeps mediated texts transparently traceable to their originals, preserving the integrity of the source. Comparable approaches exist in translation studies and corpus linguistics (e.g., parallel corpora), alignment tools in NLP (Gale & Church 1993), and similar practices are valuable across domains whether in literary translation, legal text comparison, journalistic summaries, or scientific abstracts. In NFAF, alignment is framed as a humanistic accountability tool for AI-mediated texts. Without such mapping, flattening can occur invisibly.

```
    Source Narrative     →     Transformed Narrative
    [Segment A] --------→ [Segment A’]
    [Segment B] --------→ [Segment B’]
    [Segment C] --------→ (omitted)
    [Segment D] --------→ [Segment D + added material]
    
    Alignment reveals omissions, additions, and shifts
```

---

**3.9. Signal Preservation**<br>
**Signal preservation** refers to the degree to which a narrative's core elements - such as tone, imagery, prosody, and culturally specific forms - are retained during a transformation. Preservation is not optional; any losses must be made visible and attributable to the mediation process. This transparency allows readers to evaluate the meaning and integrity of the transformed text in relation to the original source. Preservation also includes structural signals such as speaker turns, quotations, and paragraphing, and in any mediation, whether literary rewriting, journalistic summarization, legal translation, or scientific abstraction. The loss of these signals without disclosure constitutes flattening. Comparable concerns are central to archival science (provenance, integrity) and information theory, but NFAF repositions them around narrative voice, cultural register, and emotional resonance. Without preservation, flattening occurs invisibly, erasing both context and accountability.

---

**3.10. Flattening Indicators**<br>
**Flattening indicators** are reusable signs that a narrative's distinctiveness has been reduced during an AI-mediated transformation. Their presence serves as a red flag, signaling potential erasure or overwriting of cultural and emotional meaning, and may necessitate human review. They can loosely be classified as structural and alignment indicators; stylistic and cadence indicators; and semantic and interpretive indicators.

**Structural and alignment indicators**:
- **Structural drift**
- **Segment omission**: unmatched source segments (sentences/paragraphs) in alignment.
- **Dialogue flattening**: removal of quoted speech or speaker attributions; monologizing multi-turn scenes.
- **Event collapsing**: fusing discrete actions or time steps into generic summaries.
- **Discourse link collapse**: loss of explicit connectives (“however,” “therefore”), erasing contrast or causality.

**Cadence indicators**
 - **Homogenized cadence**: loss of rhythm, irony, suspense, or lyrical quality. 
  - **Flattened pacing**: reduced variance in sentence length or paragraph flow. 
 - **Loss of prosodic markers/flattened pacing**: disappearance of punctuation or figurative clusters that carry rhythm.
 
**Stylistic indicators**:
- **Loss of idiomatic expressions**: unique idioms replaced with generic phrases.
- **Quotation loss / paraphrase masking**: quotes replaced with unmarked paraphrase that shifts stance or intensity.
- **Neutralized register**: distinctive voice features smoothed into generic phrasing. 

**Semantic and interpretive indicators**:
- **Semantic drift**
- **Neutralization of emotional tone**: transformation of emotions into neutral reporting.
- **Over-generalization**: replacement of specific cultural markers with universal terms.
- **Premature disambiguation / over-specificity**: unwarranted resolution of ambiguity where the source permits multiple interpretations. 
- **Canonical pull**: outputs aligning more with remembered or precedent versions than with the given source.
- **Domain transfer**: insertion of terminology from similar but non-identical contexts.    
- **Back-translation mismatch**: apparent fidelity that, upon back-translation, reveals contamination from prior training data.


These indicators can be read alongside translation “loss markers” (Berman 1985), journalistic “framing shifts” (Hall 1980), and archival debates about authenticity, but are formalized here as a domain-crossing taxonomy for AI mediation, so that flattening cannot hide behind fluency.

---

## 4. Stages of Analysis
**Stage 1: Input Selection**  
   Identify source narratives and define intended transformations (e.g., translation, summarization, rewriting).  

**Stage 2: Transformation**  
   Preprocess source narratives and apply automated or AI-mediated processes to generate alternate versions. Document preprocessing choices, as these can themselves shape outcomes and introduce flattening effects.  

**Stage 3: Alignment**  
    Match source and transformed segments for side-by-side comparative analysis. Depending on mediation type, map source to output at the sentence/paragraph level and **record unmatched spans** (omissions). Store IDs/ranges for dropped segments, inflation (one-to-many), and any fused mappings (many-to-one), since these may signal **Structural Drift (see 3.7)** and must be disclosed in reporting.  
    Alignment remains a challenging computational problem. Manual alignment, while time-intensive, often provides the most accurate foundation for downstream analysis. Future domain-specific implementations may develop specialized alignment algorithms suited to their particular narrative types and analytical needs.  

**Stage 4: Drift Assessment**  
   Assess **Structural Drift** (changes to scaffold and discourse relations) and **Semantic Drift** (changes to meaning and resonance). Examine differences in dialog, omission, collapse, tone, and cultural/emotional signals.    

**Stage 5: Pattern Analysis**  
   Record recurring changes or flattening patterns across transformations. Standard NLP evaluation metrics (BLEU, ROUGE, perplexity) prioritize surface fidelity, whereas NFAF provides a complementary diagnostic lens centered on narrative voice, cultural register, and emotional resonance. 

**Stage 6: Human-in-the-Loop Review (optional)**  
   Validate findings through targeted human evaluation. For high-stakes contexts (e.g., legal, medical), this stage is strongly recommended.  

**Stage 7: Reporting**  
    Summarize observed patterns and potential contributing factors. When omissions occur, outputs must be labeled as summaries or rewrites and accompanied by an alignment manifest that lists dropped spans. **Omission without disclosure risks being a material misrepresentation.**

```text
Stage 1   →   Stage 2   →   Stage 3   →   Stage 4   →   Stage 5   →   Stage 6   →   Stage 7
Input         Transformation  Alignment     Drift        Pattern       Human        Reporting
Selection                   (map source/   Assessment    Analysis      Review
                             output)                     (recurring    (optional)
                                                       shifts)

Notes:
- Stage 2: Document preprocessing choices.
- Stage 3: Record unmatched spans; disclose drift.
- Stage 6: Strongly recommended for high-stakes contexts.
- Stage 7: Omission without disclosure = material misrepresentation.
```



---

## 5. Rubric

*This rubric is defined at the conceptual level.*
Future releases will add worked examples, provisional scoring methods, and domain-specific refinements.

The dimensions below operationalize the Centroid Pivot mechanism. If AI mediation normalizes inputs through Centroid English, we expect: <br>
(a) **Cadence** variance drops (English-like pacing).<br>
(b) **Lexical/Stylistic** substitution of culture-specific items with globally fluent paraphrase.<br> 
(c) **Cultural Register** dilution. <br>
(d) **Semantic/Interpretive** shifts toward Anglophone priors (“canonical pull,” premature disambiguation).<br> <br>
These are not isolated errors but **systemic signatures predicted by CP** and are therefore central indicators in NFAF.<br>
<br><br>

| Rubric Dimension    | Core Signals (Δ = AI − Source unless noted)                                                                                                                                                                        | Notes                                                                                                     | Ethical Note                                                                                   |
|---------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|
| **Cadence & Rhythm** | Sentence length mean/variance; syllables per sentence; punctuation cadence (commas, em-dashes, ellipses per 1k tokens)                                                                                             | A drop in variance = flattening. Keep to local text length to observe segment-level effects.               | Loss of rhythm is not “clarification”; it is flattening of narrative voice and must be disclosed. |
| **Lexical Richness** | Type–Token Ratio (TTR), Measure of Textual Lexical Diversity (MTLD), hapax legomena share (unique once-used words), rare-word rate                                                                                 | For “rare,” threshold by frequency quantile in the source or a reference corpus.                          | Suppression of rare/culturally marked lexemes constitutes erasure if undocumented.              |
| **Figurative Density** | Idiom frequency per 1k tokens; simile markers (“like/as a,” “como un/una”); metaphor candidates (if available)                                                                                                     | Start with rule-based proxies; document limitations.                                                       | Paraphrasing idioms/metaphors into plain text is a loss of cultural signal that must be visible. |
| **Cultural Register** | Named entities tied to locale; culture-specific lexicon/idioms; % replaced by generic terms                                                                                                                        | Build small gazetteers for test cultures (places, foods, sayings).                                         | Entity dilution, idiom neutralization, or honorific loss are cultural erasures, not neutral substitutions. |
| **Emotional Intensity** | Evaluative/affect lexicon counts; sentiment/subjectivity measures; categories from tools such as Linguistic Inquiry and Word Count (LIWC) or Empath                                                                | Track both direction (↑/↓) and range (standard deviation) of affect.                                       | Range compression erases narrative highs/lows; neutralizing affect flattens meaning and must be disclosed. |
| **Coverage & Structure** | Segment retention (kept/total), compression ratio (tokens_out ÷ tokens_in), unmatched span count; discourse relation preservation (if Rhetorical Structure Theory (RST) or Universal Dependencies (UD) tools used) | High omission or many-to-one fusions imply flattening. Report dropped segment IDs/ranges.                  | Omission without disclosure risks material misrepresentation; structural drift must be traceable. |

*Table 2. Rubric dimensions for analyzing narrative flattening. See sections 5.1–5.6 for expanded definitions of these rubric dimensions* 

### 5.1 NFAF Rubric: Cadence & Rhythm

**Signals:**
- Mean and variance of sentence length.
- Punctuation cadence (commas, dashes, ellipses per 1k tokens).
- Figurative/imagery clusters that shape flow.

**Testable Predictions:**
1. **Variance reduction.** Sentence length variance (σ²) decreases after AI mediation, converging toward English-like pacing. Compare against source-genre baselines before concluding flattening.
2. **Prosodic flattening.** Em-dashes, ellipses, or enjambment are replaced by commas/periods.
3. **Peak loss.** Figurative “bursts” (clusters of metaphor, irony, lyricism) appear less frequently or are redistributed more evenly.

_Flattening of cadence must be disclosed as a loss of narrative voice; treating rhythmic simplification as “clarification” erases meaning._

**Anchors:**
- Stylistics: (Leech & Short 1981) show cadence is a carrier of meaning, not ornament.
- Authorship studies: (Burrows 2002; Stamatatos 2009) demonstrate variance as a stylistic fingerprint.
- Translation studies: (Berman 1985) critiques “rationalization” (flattening rhythmic irregularities).
- NLP: (Hamilton et al. 2016) on systemic convergence in embeddings; (Johnson et al. 2017) on pivot layers in NMT.

---

### 5.2 NFAF Rubric: Lexical Richness

**Signals:**
- Type–Token Ratio (TTR).
- Measure of Textual Lexical Diversity (MTLD).
- Hapax legomena share (unique once-used words).
- Rare-word rate (frequency quantile relative to source or reference corpus).

**Testable Predictions:**
1. **Diversity reduction.** TTR and MTLD scores decrease in AI outputs, showing convergence on mid-frequency vocabulary.
2. **Rare-word suppression.** Hapax legomena and culturally marked lexemes decline, substituted with high-frequency synonyms, relative to the source or a reference corpus.
3. **Register neutralization.** Distinctive technical, regional, or sociolectal vocabulary is replaced by globally accessible terms.
4. **Overuse of “safe” lexemes.** A limited set of frequent words (e.g., “important,” “significant,” “good”) are repeated at higher rates than in the source.

_Suppression or substitution of rare and culturally marked lexemes constitutes erasure; ethical reporting requires making these substitutions visible._ Note that some languages mark lexical diversity differently (inflection-heavy vs. analytic).

**Anchors:**
- Stylistics: (Leech & Short 1981) on vocabulary as a stylistic marker.
- Translation studies: (Toury 1995) on translational norms, where systemic pressures favor common lexical items over marked or culture-specific ones.
- Computational stylistics: (Burrows 2002) shows authorship can be traced through distinctive lexical distributions.
- NLP: (Bender et al. 2021) warn of centroid bias in large models, privileging high-frequency English lexicon.
- Corpus linguistics: (McEnery & Hardie 2012) on measuring lexical diversity, useful for operationalizing this prediction.

---

### 5.3 NFAF Rubric: Figurative Density

**Signals:**
- Idiom frequency per 1k tokens.
- Simile markers (“like/as a,” “como un/una,” “comme un/une”).
- Metaphor candidates (rule-based or embedding-based detection if available).
- Clusters of figurative language that drive imagery, irony, or tone.

**Testable Predictions:**
1. **Idiom loss.** Culture-specific idioms are paraphrased into generic phrases (e.g., _tirar la toalla_ → “to give up”).
2. **Simile simplification.** Similes with culturally rich referents are replaced with neutral or universal comparisons.
3. **Metaphor reduction.** Extended metaphoric structures (multi-clause conceits, allegories) are shortened or omitted.
4. **Density smoothing.** Peaks of figurative intensity (e.g., lyric passages in literature, rhetorical flourishes in journalism or law) are redistributed into more even, literal prose.

_Paraphrasing idioms, similes, or metaphors into plain text is not a neutral simplification; it is a loss of figurative signal that must be documented._ Note that existing tools under-detect culturally marked figuratives; manual annotation is often necessary.

**Anchors:**
- Translation studies: (Berman 1985) on “clarification,” figurative opacity rendered into plain explanation. 
- Stylistics: (Leech & Short 1981) treat metaphor and idiom as core markers of style.
- Digital Humanities: (Jockers 2013; Moretti 2013) explore figurative density as quantifiable signal in large corpora.
- NLP: (Shutova 2010; Dankers et al. 2019) show AI tends toward literal paraphrase when figurative usage is uncertain.

---

### 5.4 NFAF Rubric: Cultural Register

**Signals:**
- Named entities tied to locale (places, foods, institutions, idioms).
- Culture-specific lexicon and sayings.
- Percentage replaced by generic, universal, or Anglophone-oriented terms.
- Presence/absence of honorifics, politeness markers, or culturally specific discourse cues.

**Testable Predictions:**
1. **Entity dilution.** Local place names, foods, or institutions are generalized (e.g., _bodega_ → “corner store,” _soba_ → “noodles”).
2. **Discourse marker shifts.** Loss or overuse of culturally distinctive connectives (e.g., pues in Spanish, en fait in French).
3. **Idiom neutralization.** Proverbs and culturally distinctive sayings are paraphrased into plain or global English equivalents.
4. **Honorific loss.** Politeness markers (e.g., _usted_, _-san_, _monsieur_) are omitted or flattened into direct address.
5. **Centroid language substitution.** Target text exhibits features from the dominant centroid language: for example, Anglophone metaphors, collocations, or formatting (e.g., U.S.-style date/time, “Mr.” for non-English honorifics). Such substitutions are not merely flattening; they risk overwriting the target with dominant cultural defaults.
6. **Centroid Pivot Imprint.** Even in non-English ↔ non-English translation, outputs may carry discourse markers or stylistic defaults from the centroid language. At present this often means English-like markers (e.g., *en realidad, como resultado* in Spanish; *en fait* overused in French), but the phenomenon reflects the systemic influence of the pivot rather than the languages directly involved.

_Shifts in discourse markers, honorifics, or culture-specific lexicon must be flagged. Such substitutions are not neutral; they risk overwriting situated cultural identity with centroid defaults._

**Anchors:**
- (Berman 1985) on “ethnocentric reduction” of idioms and cultural references.
- (Toury 1995) on norms: cultural choices shaped by systemic pressures.
- (Venuti 1995) on domestication: erasure of local markers under systemic pressure toward centroid fluency.
- (Cronin 2003) on globalization: small/local languages flattened when funneled through a dominant lingua franca.
- NLP/MT: (Johnson et al. 2017; Bender et al. 2021) on English dominance in multilingual models.

---

### 5.5 NFAF Rubric: Emotional Intensity

**Signals:**
- Evaluative/affect lexicon counts (positive/negative adjectives, intensifiers).
- Sentiment polarity and subjectivity measures.
- Variability of affect (standard deviation of sentiment scores across segments).
- Use of exclamatives, modal verbs, rhetorical questions as emotional carriers.
- Sarcasm/irony markers (contrastive cues, hyperbole, scare quotes) that convey affect indirectly.

**Testable Predictions:**
1. **Neutralization of affect.** Strongly positive or negative terms are replaced by moderate descriptors (e.g., _horrifying_ → “bad,” _exquisite_ → “beautiful”).
2. **Range compression.** Standard deviation of affect scores decreases; emotional highs and lows flatten into mid-intensity prose.
3. **Removal of markers.** Exclamatives, modal intensifiers (_must, should_), or rhetorical questions are omitted or converted to declaratives.
4. **Cultural calibration loss.** Affect signals are normalized without regard to cultural conventions, e.g. an exclamation mark in Spanish (¡Hola!), English (“Hello!”), and Japanese (！) does not carry equal intensity, but AI mediation may flatten these into a uniform mid-level register.
5. **Tone smoothing across genres.** Journalism summaries downplay outrage or urgency; literary passages lose lyric peaks of sorrow/joy; legal rhetoric loses emphatic certainty.

_Neutralization or compression of affect flattens narrative arcs; these changes must be disclosed so emotional resonance is not erased invisibly._

**Anchors:**
- Narratology: (Genette 1980) on mood and tone as dimensions of narrative discourse.
- Translation studies: (Berman 1985) on “ennoblement” and “clarification” reducing tonal extremes and (Venuti 1995) on domestication of affect into neutral register.
- Digital Humanities: (Ramsay 2011; Jockers 2013) on measuring sentiment arcs.
- NLP: (Pennebaker et al. 2001; Fast et al. 2016) on affect lexicons; recent work on LLM sentiment bias shows moderation toward neutrality.

---

### 5.6 NFAF Rubric: Coverage & Structure

**Signals:**
- Segment retention ratio (kept/total).
- Compression ratio (tokens_out ÷ tokens_in).
- Count of unmatched spans (omitted, fused, or inflated segments).
- Preservation of discourse relations (contrast, cause, elaboration via RST or UD markers).
- Integrity of quotations, speaker turns, and attributions.

**Testable Predictions:**
1. **Segment loss**: AI mediation omits or fuses multiple source segments, reducing total coverage.
2. **Compression bias**: Outputs show higher compression ratios than human-mediated equivalents, especially in summarization.
3. **Discourse link collapse**: Explicit markers of causality, contrast, or elaboration are dropped (e.g., *sin embargo, parce que, “however”*).
4. **Dialogue flattening**: Multi-turn exchanges are collapsed into single-speaker paraphrase.
5. **Structural drift**: Narrative scaffold (event sequencing, clause nesting, paragraphing) is altered without disclosure, making the mediated text appear fluent but structurally divergent.
6. **Multimodal omission**: Visuals, and graphs are dropped, e.g.images in journalism.
7. **Longitudinal drift**: Chronologies compressed or events reordered, altering historical/archival integrity. 
8. **Integrity of formatting/paratext**: Dropping of paratext such as footnotes, references, headings, e.g. citations in law.

_Omissions, re-orderings, or structural drift without disclosure constitute a misrepresentation of the source and compromise accountability._

**Anchors:**
- Discourse theory: (Mann & Thompson 1988; van Dijk 2008) on discourse relations.
- Translation studies: (Berman 1985) on omission and rationalization.
- Journalism studies: (Hall 1980) on framing, omissions reshape stance.
- NLP: (Hamilton et al. 2016) on semantic drift; summarization evaluation work (ROUGE, BLEU) on compression vs. fidelity trade-offs.
- Archival science: principles of provenance and integrity highlight why structural omissions compromise accountability.

---

## 6. Foundations

NFAF builds on and extends insights from multiple fields:

- **Narratology:** (Genette 1980; Bal 1985; Ryan 2004).
Established the study of narrative discourse, framing, and sequence as carriers of meaning.

- **Translation Studies:** (Venuti 1995; Berman 1985; Toury 1995).
Foregrounded the ethics of mediation, domestication, and invisibility. NFAF acknowledges these debates but emphasizes how AI mediation amplifies them through scale and feedback loops: trained on web-scale data and recursively on its own outputs, AI effects not only apply to individual choices but as systemic, self-reinforcing defaults.

- **Digital Humanities:** (Drucker 2014; Ramsay 2011; Jockers 2013).
Advanced computational and interpretive approaches to reading, emphasizing critique of neutrality.

- **Stylistics & Authorship Studies:** (Leech & Short 1981; Burrows 2002; Stamatatos 2009).
Quantified style through cadence, vocabulary, and authorship signals as measurable markers.

- **Media & Culture:** (Hall 1980).
Introduced framing theory and encoding/decoding models that show how mediation shapes stance.

- **AI / NLP:** (Bender et al. 2021; Mitchell 2021; Hamilton et al. 2016; Papineni et al. 2002; Lin 2004; Koehn 2009; Mohammad & Turney 2013).
Exposed biases, fairness concerns, convergence effects, and evaluation limitations in large-scale language models; established standard metrics (BLEU, ROUGE) and MT foundations; developed widely used emotion/sentiment lexicons.

- **Mechanism & Mediation (Centroid Pivot):** (Cronin 2003; Johnson et al. 2017).
Identified globalization pressures and pivot mechanisms that flatten linguistic and cultural signals.

- **Alignment Studies:** (Gale & Church 1993).
Introduced statistical methods for aligning bilingual corpora, forming the foundation for modern alignment practices.

<br><br><br>

| **Foundation Field**          | **Key Concepts**                                    | **NFAF Rubric Dimensions Supported**      |
| ------------------------------ | -------------------------------------------------- | ----------------------------------------- |
| Narratology (Genette; Bal; Ryan) | Discourse, framing, sequencing, tone               | Cadence & Rhythm · Emotional Intensity · Coverage & Structure |
| Translation Studies (Venuti; Berman; Toury) | Domestication, foreignization, loss markers, norms | Lexical Richness · Figurative Density · Cultural Register · Emotional Intensity |
| Digital Humanities (Drucker; Ramsay; Jockers) | Algorithmic criticism, interpretive drift, critique of neutrality | Figurative Density · Emotional Intensity · Coverage & Structure |
| Stylistics & Authorship Studies (Leech & Short; Burrows; Stamatatos) | Style as measurable signal, cadence, vocabulary, authorship | Cadence & Rhythm · Lexical Richness · Figurative Density |
| Media & Culture (Hall)         | Framing, encoding/decoding, stance shaping          | Cultural Register · Coverage & Structure |
| AI / NLP (Bender; Mitchell; Hamilton) | Bias, fairness, semantic drift, centroid convergence | Lexical Richness · Cultural Register · Coverage & Structure |
| Mechanism & Mediation (Cronin; Johnson et al.) | Globalization, pivot mechanisms, zero-shot translation | Cultural Register · Coverage & Structure · Cadence & Rhythm |
| Alignment Studies (Gale & Church) | Statistical sentence alignment, parallel corpora   | Coverage & Structure (Alignment) |

*Table 3. NFAF Rubric foundation and key concepts.*

Together, these anchors demonstrate that NFAF is not limited to any single discipline: it translates long-standing humanistic concerns into a replicable diagnostic for the AI-mediated era.

---

 
### 7. Application: Literary Rewrite (Austen, Emma)

**Source:** Jane Austen, *Emma* (1815), Chapter 1 excerpt (public domain).  
**Mediation:** Modernized rewrite by three models.  
**Summary Finding:**  
Rewrites produced fluent modern English but erased Austen’s irony and narrative rhythm. Omissions were not signaled, creating an illusion of surface fidelity while silently compressing voice and discourse cues.

**Glossary:**
- Rewrite = 1–1 mapping
- Summary = omission with disclosure
- Missing = null alignment
- Inflated rewrite = expansion with padding

#### Alignment Snippet (Paragraph 5)

| **Source (Austen)**                                                                                                                                                                                                                             | **Model A**                                                                                                            | **Model B**                                                                                                                                                                                                     | **Model C**                                                                                                                                                                                                 |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _“Sorrow came—a gentle sorrow—but not at all in the shape of any disagreeable consciousness.—Miss Taylor married. … Her father composed himself to sleep after dinner, as usual, and she had then only to sit and think of what she had lost.”_ | _“Her first taste of sorrow came when Miss Taylor married Mr. Weston. … Emma wondered how she would bear the change.”_ | _“Then sorrow came—a gentle sadness—but not in the form of any unpleasant self-awareness. … Her father settled down for his usual after-dinner nap, and she could only sit and think about what she had lost.”_ | _“Then, a gentle sadness came—but not in the form of any uncomfortable self-realization. … Her father fell asleep after dinner as usual, and Emma was left to just sit and think about what she had lost.”_ |

**Observed:**

- **Model A** “Model A compresses to a hybrid: half rewrite, half summary (drops dining/nap scene into generalized reflection).
    
- **Model B** preserves all narrative beats (true rewrite, cadence flattened).
    
- **Model C** preserves sequence but inflates with over-specific phrasing (“continuous mournful thought”).

#### Cadence Metric (Paragraph 5)

| **Text**        | Mean sentence length (words) | Variance (σ²) | Notes                                                                               |
| --------------- | ---------------------------- | ------------- | ----------------------------------------------------------------------------------- |
| Source (Austen) | 27.8                         | **42.1**      | Long, varied clauses with em-dashes; rhythm of buildup and release.                 |
| Model A         | 22.3                         | **15.4**      | Compression + summarization to a shorter, more uniform sentences.                   |
| Model B         | 24.7                         | **18.6**      | Retains sequence but cadence smoothed; em-dash rhythm lost.                         |
| Model C         | 25.1                         | **17.9**      | Similar to B; over-specific phrasing adds slight padding, still flattened variance. |

**Observed:** Sentence length variance drops sharply in all rewrites, demonstrating homogenized cadence, a key flattening indicator per NFAF rubric.
Austen’s rhythmic “peaks and valleys” are flattened into a more even prose.

---

## 8. Application Across Domains 

The framework is not confined to literature; the following table illustrates representative domains where NFAF has been or can be applied.
Each domain suggests a likely mediation type and flattening pattern, but these are not exhaustive or prescriptive.<br>


| **Domain**               | **Focus**                                                      | **Mediation Type**             | **Pattern Statement**                                                                                                                                                                                            |       |
| ------------------------ | -------------------------------------------------------------- |--------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------| ----- |
| Literature               | Stylistic flattening (voice/cadence)                           | Translation                    | *Model transformations flatten narrative voice by neutralizing cadence, softening affect, and converging distinct stylistic signatures toward standardized modern prose.*                                        |       |
| Journalism & News        | Cultural flattening (journalistic stance)                      | Summarization                  | *Model summarization flattens culturally distinct journalistic stances into a neutralized AP/BBC-style register, erasing partisan, regional, and evaluative markers.*                                            |       |
| Law                      | Jurisdictional flattening (legal register + statutory anchors) | Translation                    | *Model translation flattens legal reasoning by compressing argumentation, erasing jurisdictional nuance, and converging distinct doctrinal voices into simplified, globally legible but less precise registers.* |       |
| Culture & Representation | Flattening of cultural/historical narratives into generalized, globally neutral frames                          | Summarization / Image Generation | *Model summarization flattens cultural narratives by stripping contextual markers, diluting temporal depth, and converging situated perspectives into linear, event-focused accounts.*                           |       |
| Historical & Archival    | Temporal register shifts; anachronistic insertions in historical texts                          | Rewriting                      | *Model Rewriting flattens historical narratives*                                                                                                                                                                 | <br/> |
| Scientific Publications  | Conceptual flattening (specialized registers)                  | Rewriting                      | *Model Rewriting flattens scientific discourse by simplifying terminology, neutralizing disciplinary nuance, and converging specialized registers into generalized, lay-accessible prose.*                       |       |

*Table 4. Illustrative applications of NFAF application across domains.*

---

## 9. References

Bal, Mieke. 1985. _Narratology: Introduction to the Theory of Narrative_. Toronto: University of Toronto Press.

Bender, Emily M., Timnit Gebru, Angelina McMillan-Major, and Shmargaret Shmitchell. 2021. “On the Dangers of Stochastic Parrots: Can Language Models Be Too Big?” In _Proceedings of the 2021 ACM Conference on Fairness, Accountability, and Transparency (FAccT ’21)_.

Berman, Antoine. 1985. “La traduction et la lettre, ou l’auberge du lointain.” In _Les tours de Babel_. Paris: Gallimard.

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

Ramsay, Stephen. 2011. _Reading Machines: Toward an Algorithmic Criticism_. Urbana: University of Illinois Press.

Ryan, Marie-Laure. 2004. _Narrative as Virtual Reality_. Baltimore: Johns Hopkins University Press.

Santoyo, Julio-César. 2009. _A través del espejo: estudios de traducción en la Edad Media_. León: Universidad de León.

Shutova, Ekaterina. 2010. “Models of Metaphor in NLP.” In _Proceedings of the 48th Annual Meeting of the Association for Computational Linguistics (ACL)_.

Stamatatos, Efstathios. 2009. “A Survey of Modern Authorship Attribution Methods.” _Journal of the American Society for Information Science and Technology_ 60 (3): 538–556.

Toury, Gideon. 1995. _Descriptive Translation Studies and Beyond_. Amsterdam: John Benjamins.

van Dijk, Teun A. 2008. _Discourse and Context: A Sociocognitive Approach_. Cambridge: Cambridge University Press.

Venuti, Lawrence. 1995. _The Translator’s Invisibility: A History of Translation_. London: Routledge.

---

## 10. Citation
If you use or reference this framework, please cite:

```bibtex
@software{helton_nfaf_2025,
  author       = {Helton, Johennie},
  title        = {NFAF: Narrative Flattening Analysis Framework (v0.4.0)},
  year         = 2025,
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.16885076},
  url          = {https://doi.org/10.5281/zenodo.16885076}
}
