# NFAF: Narrative Flattening Analysis Framework

**Author:** Johennie Helton  
**Status:** Public Specification (v0.3.0)  


## Citation & Authorship

If you use or reference this framework, please cite:

Helton, J. (2025). *NFAF: Narrative Flattening Analysis Framework (v0.3.0)*. Zenodo.  
[https://doi.org/10.5281/zenodo.16885076](https://doi.org/10.5281/zenodo.16885076)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.16885076.svg)](https://doi.org/10.5281/zenodo.16885076)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0003--2175--3239-green?logo=orcid)](https://orcid.org/0009-0003-2175-3239)

---

## Abstract
**The Narrative Flattening Analysis Framework (NFAF)** is a methodology for detecting and analyzing the loss or convergence of distinct cultural, emotional, and stylistic features in narratives as they pass through automated processes such as machine translation, summarization, rewriting, or other AI-mediated transformations.

These transformations often reflect algorithmic optimization toward **neutral, generalized, or centroid language** outputs that appear more universally “fluent” but less contextually situated. NFAF provides a framework for testing, documenting, and measuring when and where such tendencies appear.

Narrative is defined here in its broadest sense. NFAF is adaptable to a wide range of use cases and modalities. It outlines modular stages for alignment, semantic drift detection, and qualitative-quantitative analysis, enabling reviewers to identify meaning loss or homogenization including subtle or accumulative cultural, political, or semantic transformation. Designed to balance rigor with flexibility, NFAF provides a replicable structure for future research while remaining open to domain-specific refinement.

**Current focus:** Applying NFAF to *narrative voice in literary text*, with emphasis on preserving cultural and emotional signals in AI-mediated transformation.

Note: NFAF is published as pre-existing intellectual property of Johennie Helton. This specification is provided for research and citation purposes only. No rights to implement, commercialize, or assume co-ownership of the framework are granted or implied.

---

## Definitions

**Narrative**<br>
In this framework, narrative is defined broadly as any structured account: linguistic, visual, or multimodal, that conveys meaning through sequence, framing, or voice. 
<br><br>Narrative encompasses not only literary texts but also journalistic reporting, scientific writing, legal argument, and cultural expression. Narratives may be linear or nonlinear, explicit or implicit, but they are always shaped by choices of form, style, and emphasis that reflect particular contexts and perspectives.  
<br><br>       
**Flattening**<br>
The systematic **reduction of distinctiveness** that occurs when a narrative is mediated by AI. Flattening can manifest in multiple directions:  
    **Erosion**: the loss or weakening of semantic nuance, stylistic rhythm, cultural reference, or affective tone.  
    **Inflation**: the insertion or exaggeration of generic features not present in the original. 
    **Addition/Inference**: Introduction of details absent in the source, often derived from training familiarity with canonical texts, precedent cases, or analogous contexts.
This may resolve ambiguity in ways not warranted by the source, importing details or terminology inferred from training familiarity rather than the given text.
<br><br>Though opposite in form, both processes converge on the same outcome: outputs that are more standardized, less contextually situated, and less distinctive.  
<br><br>
**Narrative flattening**<br>
The erosion or inflation of signals that constitute **narrative distinctiveness**, including voice, style, cultural reference, and domain-specific markers of meaning. 
<br>In literary contexts, this may appear as homogenized rhythm, reduced figurative density, or neutralized emotional tone. 
<br>In other domains, it may appear as genericized news summaries, culturally inaccurate image generation, biomedical writing that converges on formulaic phrasing, or legally imprecise translations. 
<br><br>Narrative flattening thus captures the tendency of AI-mediated processes to prioritize fluency, generality, and efficiency over depth, specificity, and contextual nuance.
<br><br>
**Algorithmic English**<br>Refers to the normalized register that large-scale AI models tend to converge toward, privileging fluency, neutrality, and universality over cultural or stylistic specificity.  
    In technical contexts, this is sometimes described as **Centroid English** highlighting the statistical convergence of outputs toward a “central” linguistic norm.  
    In broader cultural or public contexts, it may be referred to as **Internet English** the globally distributed, flattened form of English shaped by large-scale web data.
<br>
    NFAF provides a framework for testing, documenting, and measuring when and where this tendency appears.
<br><br>
**Semantic drift**<br>
Systematic or cumulative change in meaning between source and transformed text. Drift can be observed at different levels:
<br>
Lexical Drift: Substitution, loss, or generalization of word choice.
<br>
Syntactic Drift: Shifts in sentence structure that alter emphasis or rhythm.
<br>
Pragmatic Drift: Changes in implied meaning, tone, or cultural resonance.
<br><br>
**Voice Cadence Metrics**<br>
Quantitative measures of stylistic rhythm and intensity, used to assess whether narrative “peaks and valleys” are preserved.
Examples include:
<br>
Sentence length variance.
<br>
Figurative density (e.g., frequency of metaphors, imagery).
<br>
Punctuation-driven rhythm (commas, dashes, ellipses).
<br>
Prosodic markers in poetry or dialogue.
<br><br>
**Alignment**<br>
Segment-level mapping between source and transformed narratives to enable side-by-side analysis.  
<br><br>
**Signal preservation**<br> 
Degree to which tone, imagery, prosody, and culturally loaded forms are retained.
<br><br>
**Flattening Indicators**<br>
  Reusable signs that narrative distinctiveness has been reduced:
<br>
  - Loss of idiomatic expressions: translated to generic phrases.<br>
  - Neutralization of emotional tone: anger to neutral reporting.<br>
  - Homogenized cadence: irony, suspense, or lyrical rhythm lost.<br>
  - Over-generalization: specific cultural markers replaced with universal terms.<br>
  - Over-specificity: resolving ambiguity where the source permits multiple interpretations.<br>
  - Canonical pull: outputs aligning with remembered or precedent versions of a text.<br>
  - Domain transfer: insertion of terms from similar but non-identical contexts.<br>
  - Back-translation mismatch: apparent preservation of meaning, but with contamination from prior data.<br>

---
## High-Level Process
1. **Input Selection**  
   Identify source narratives and define intended transformations (e.g., translation, summarization, rewriting).  

2. **Transformation**  
   Apply automated or AI-mediated processes to generate alternate versions.  

3. **Alignment**  
   Match source and transformed segments for side-by-side comparative analysis.  

4. **Semantic Drift Assessment**  
   Examine differences in meaning, tone, and cultural/emotional signals.  

5. **Pattern Analysis**  
   Record recurring changes or flattening patterns across transformations.  

6. **Human-in-the-Loop Review (optional)**  
   Validate findings through targeted human evaluation.  

7. **Reporting**  
   Summarize observed patterns and potential contributing factors.  

---

## Rubric

*This rubric is defined at the conceptual level. Future releases (v0.4.x and beyond) will add worked examples, provisional scoring methods, and domain-specific refinements.*

| **Rubric dimension**    | **Core signals (Δ = AI − Source unless noted)**                                                                                                     | **Notes**                                                                                    |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| **Lexical Richness**    | Type–Token Ratio (TTR), Measure of Textual Lexical Diversity (MTLD), hapax legomena share (unique once-used words), rare-word rate                  | For “rare,” threshold by frequency quantile in the source or a reference corpus.             |
| **Rhythm & Cadence**    | Sentence length mean/variance; syllables per sentence; punctuation cadence (commas, em-dashes, ellipses per 1k tokens)                              | A drop in variance = flattening. Keep to local text length to observe segment-level effects. |
| **Figurative Density**  | Idiom frequency per 1k tokens; simile markers (“like/as a”, “como un/una”); metaphor candidates (if available)                                      | Start with rule-based proxies; document limitations.                                         |
| **Cultural Register**   | Named entities tied to locale; culture-specific lexicon/idioms; % replaced by generic terms                                                         | Build small gazetteers for test cultures (places, foods, sayings).                           |
| **Emotional Intensity** | Evaluative/affect lexicon counts; sentiment/subjectivity measures; categories from tools such as LIWC (Linguistic Inquiry and Word Count) or Empath | Track both direction (↑/↓) and range (standard deviation) of affect.                         |


---

## Scope  
- Framework description and methodological scaffolding.  
- Definitions and rubric dimensions for discussing flattening effects across domains.  
- Work in progress (WIP): examples, provisional scoring methods, and domain-specific refinements will be added in future releases.  


---

## Citation
If you use or reference this framework, please cite:

```bibtex
@software{helton_nfaf_2025,
  author       = {Helton, Johennie},
  title        = {NFAF: Narrative Flattening Analysis Framework (v0.3.0)},
  year         = 2025,
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.16885076},
  url          = {https://github.com/johennie/nfaf-public}
}
