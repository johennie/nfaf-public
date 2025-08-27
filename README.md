# NFAF: Narrative Flattening Analysis Framework

**Author:** Johennie Helton  
**Status:** Public Specification (v0.2.0)  


## Citation & Authorship

If you use or reference this framework, please cite:

Helton, J. (2025). *NFAF: Narrative Flattening Analysis Framework (v0.2.0)*. Zenodo.  
[https://doi.org/10.5281/zenodo.16885077](https://doi.org/10.5281/zenodo.16885077)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.16885077.svg)](https://doi.org/10.5281/zenodo.16885077)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0003--2175--3239-green?logo=orcid)](https://orcid.org/0009-0003-2175-3239)

---

## Abstract
**The Narrative Flattening Analysis Framework (NFAF)** is a methodology for detecting and analyzing the loss or convergence of distinct cultural, emotional, and stylistic features in narratives as they pass through automated processes such as machine translation, summarization, rewriting, or other AI-mediated transformations.

Narrative is defined here in its broadest sense. NFAF is adaptable to a wide range of use cases and modalities. It outlines modular stages for alignment, semantic drift detection, and qualitative-quantitative analysis, enabling reviewers to identify meaning loss or homogenization including subtle or accumulative cultural, political, or semantic transformation. Designed to balance rigor with flexibility, NFAF provides a replicable structure for future research while remaining open to domain-specific refinement.

**Current focus:** Applying NFAF to *narrative voice in literary text*, with emphasis on preserving cultural and emotional signals in AI-mediated transformation.

Note: NFAF is published as pre-existing intellectual property of Johennie Helton. This specification is provided for research and citation purposes only. No rights to implement, commercialize, or assume co-ownership of the framework are granted or implied.

---

## Definitions

- **Narrative** In this framework, *narrative* is defined broadly as any structured account: linguistic, visual, or multimodal, that conveys meaning through sequence, framing, or voice. Narrative encompasses not only literary texts but also journalistic reporting, scientific writing, legal argument, and cultural expression. Narratives may be linear or nonlinear, explicit or implicit, but they are always shaped by choices of form, style, and emphasis that reflect particular contexts and perspectives.  
      
    
- **Flattening**: is the systematic **reduction of distinctiveness** that occurs when a narrative is mediated by AI. Flattening can manifest in two directions:  
    **Erosion**: the loss or weakening of semantic nuance, stylistic rhythm, cultural reference, or affective tone.  
    **Inflation**: the insertion or exaggeration of generic features not present in the original. Though opposite in form, both processes converge on the same outcome: outputs that are more standardized, less contextually situated, and less distinctive.  
      
    
- **Narrative flattening**: refers to the erosion or inflation of signals that constitute **narrative distinctiveness**, including voice, style, cultural reference, and domain-specific markers of meaning. In literary contexts, this may appear as homogenized rhythm, reduced figurative density, or neutralized emotional tone. In other domains, it may appear as genericized news summaries, culturally inaccurate image generation, biomedical writing that converges on formulaic phrasing, or legally imprecise translations. Narrative flattening thus captures the tendency of AI-mediated processes to prioritize fluency, generality, and efficiency over depth, specificity, and contextual nuance.
    
- **Semantic drift**: Systematic or cumulative change in meaning between source and transformed text.  
      
    
- **Alignment**: Segment-level mapping between source and transformed narratives to enable side-by-side analysis.  
      
    
- **Signal preservation**: Degree to which tone, imagery, prosody, and culturally loaded forms are retained.

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

*This rubric is defined at the conceptual level. Future minor releases (v0.2.x) may introduce provisional categorical scoring (e.g., low / medium / high).*

| **Rubric dimension**    | **Core signals (Δ = AI − Source unless noted)**                                                                 | **Notes**                                                                     |
| ----------------------- | --------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| **Lexical Richness**    | TTR, MTLD, hapax share, rare-word rate                                                                          | For “rare,” threshold by freq quantile in the source or a reference corpus.   |
| **Rhythm & Cadence**    | Sentence length mean/variance; syllables/sentence; punctuation cadence (commas/emdashes/ellipses per 1k tokens) | A drop in variance = flattening. Keep to length of chat to see local effects. |
| **Figurative Density**  | Idiom hits per 1k tokens; simile markers (“like/as a”, “como un/una”); metaphor candidates (if available)       | Start with rule-based proxies; document limitations.                          |
| **Cultural Register**   | Named entities tied to locale; culture-specific lexicon/idioms; % replaced by generic terms                     | Build small gazetteers for test cultures (places, foods, sayings).            |
| **Emotional Intensity** | Evaluative/affect lexicon counts; sentiment/subjectivity; LIWC/Empath categories (if used)                      | Track both direction (↑/↓) and range (std dev) of affect.                     |


---

## Scope  
- Framework description and methodological scaffolding.  
- Definitions and rubric dimensions for discussing flattening effects across domains.  
- Work in progress (WIP): examples, provisional scoring methods, and domain-specific refinements will be added in minor releases (v0.2.x).  


---

## Citation
If you use or reference this framework, please cite:

```bibtex
@software{helton_nfaf_2025,
  author       = {Helton, Johennie},
  title        = {NFAF: Narrative Flattening Analysis Framework (v0.1.0)},
  year         = 2025,
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.16885077},
  url          = {https://github.com/johennie/nfaf-public}
}
