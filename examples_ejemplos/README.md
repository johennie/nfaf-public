# NFAF Examples / Ejemplos

This directory contains worked examples of **Narrative Flattening (NFAF)** across multiple domains.  
Each example demonstrates how to apply the framework: selecting source texts, running AI-mediated transformations, and analyzing the resulting shifts.  

---

## Directory Structure

- **EX##_Domain_Dominio/**  
  Each numbered folder corresponds to a domain-specific example.  
  - `text_texto/`
  Source texts (original human-authored material).  
  
  - `llm_outputs/`
  Outputs from AI-mediated transformations (translations, summaries, rewrites, backtranslations

The following directories contain worked examples of narrative flattening across domains. Each includes source texts (text_texto), AI-mediated outputs (llm_summaries), and brief analysis (analysis.en.md / analysis.es.md).

| **ID** | **Directory**                | **Domain**              | **Description**                                                                             |
| ------ | ---------------------------- | ----------------------- | ------------------------------------------------------------------------------------------- |
| EX01   | `EX01_Literature_Literatura` | Literature / Literatura | Literary narratives. Focus on voice, cadence, and figurative density.                       |
| EX02   | `EX02_Journalism_Periodismo` | Journalism / Periodismo | News articles and summaries. Shows how headlines and reports lose local framing and nuance. |
| EX03   | `EX03_Law_Legal`             | Law / Legal             | Legal and copyright texts. Tracks loss of precision in key terms and translation drift.     |

---

## File Naming Conventions

Inside `llm_summaries/`, filenames follow this pattern: EX##shorttitle_ModelX##_operation.direction.md

Where:

- **EX##**
Example number (e.g., EX01 for Literature).  

- **shorttitle**
Abbreviated text title (`emma_austen`, `fortunata_perezgaldos`, `usa_news`).  

- **ModelX**
Model label (A, B, C…).  

- **##**
Step number:  

  - `01`
  First transformation (usually MT = machine translation, or summary).  
  
  - `02`
  Back-translation (BT) or secondary operation.  
  
- **operation**
`mt` (machine translation), `bt` (back translation), `sum` (summary), `rw` (rewrite).  

- **direction**
Language flow (`en_to_es`, `es_to_en`, etc.).  

- **.md**
All files are Markdown with YAML-style metadata headers.

Example:  
`EX01_emma_austen_Model_A_01_mt.en_to_es.md`
Emma, Model A, machine translation, English → Spanish.

---

## Index

| **ID** | **Domain / Dominio**    | **Description**                                                                                                   |
| ------ | ----------------------- | ----------------------------------------------------------------------------------------------------------------- |
| EX01   | Literature / Literatura | Jane Austen, *Emma* (1815)                                                                                        |
| EX02   | Journalism / Periodismo | Guardian, Fox, El País, BBC, AP, Reuters news reports re: 'Alligator Alcatraz' appeals court ruling               |
| EX03   | Law / Legal             | Legal/copyright text translations (EN ↔ ES) re: Court of Justice of the EU, Case T-612/17 (*Google v Commission*) |

---

© Johennie Helton. All rights reserved.  
This material is published for research and citation purposes only. No rights to implement, commercialize, or assume co-ownership are granted or implied.
