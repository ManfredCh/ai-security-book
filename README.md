<div align="center">

# Generative and Embodied AI Security

**What happens to security when a model stops answering questions and starts acting.**

<sub>6 parts · 24 chapters · 193,000 English words · 312-page PDF</sub>

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC_BY--NC--SA_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)  ·  [![Status](https://img.shields.io/badge/Status-compiled_draft-orange)](#status-and-limits)  ·  [![Language](https://img.shields.io/badge/Language-English_%7C_%E4%B8%AD%E6%96%87-blue)](#languages-and-editions)  ·  [![English PDF](https://img.shields.io/badge/PDF-312_pp.-red)](release/en/Generative-and-Embodied-AI-Security.pdf)  ·  [![中文 PDF](https://img.shields.io/badge/PDF_%E4%B8%AD%E6%96%87-333_pp.-red)](release/zh/生成式与具身智能安全.pdf)

[English](README.md) · [简体中文](README.zh.md)

</div>

> For want of a nail the shoe was lost,
> For want of a shoe the horse was lost,
> For want of a horse the rider was lost,
> For want of a rider the battle was lost.
>
> — Benjamin Franklin, *Poor Richard's Almanack*, 1758

---


<!-- toc:start -->
<details open>
<summary><b>Contents</b></summary>

- [The point](#the-point)
- [Overview](#overview)
  - [Chapters](#chapters)
- [Files and formats](#files-and-formats)
- [Reading paths](#reading-paths)
  - [Path A · The whole skeleton in three hours](#path-a--the-whole-skeleton-in-three-hours)
  - [Path B · Go deep in one direction](#path-b--go-deep-in-one-direction)
  - [Path C · Full read](#path-c--full-read)
  - [Path D · Put it to work](#path-d--put-it-to-work)
- [Languages and editions](#languages-and-editions)
- [Repository layout](#repository-layout)
- [Changelog](#changelog)
  - [v0.2.0 — 2026-09-26](#v020--2026-09-26)
  - [v0.1.0 — 2026-09-26](#v010--2026-09-26)
- [Cutoff and what comes next](#cutoff-and-what-comes-next)
  - [Found since the cutoff and now recorded (searched 2026-09-26)](#found-since-the-cutoff-and-now-recorded-searched-2026-09-26)
- [Status and limits](#status-and-limits)
- [Citation](#citation)
- [Contributing](#contributing)
- [Acknowledgements](#acknowledgements)
- [Star History](#star-history)
- [License](#license)
- [Related repositories](#related-repositories)

</details>
<!-- toc:end -->

## The point

One question runs through the whole book: **which trust boundary does untrusted input cross first?**
Not "what kind of attack is this" — that only names the symptom. The interface that fails *first*
decides where a control can go, what evidence is admissible, and which two numbers may be compared.

Three chapters build that instrument. Four parts then apply it to language-model agents, image and
video generation, the vision–language–action loop, and world models. A final part turns it into
release gates, incident response, and three templates you can fill in for your own system.

| Language | README | Documents |
|---|---|---|
| **English** | this file | English edition, 193k words, 450-page PDF |
| **简体中文** | [README.zh.md](README.zh.md) | 中文原稿，28.0 万汉字，333 页 PDF |


## Overview

When a model produces only a passage of text, security problems stay at the level of content.
Once its output reaches retrieval, long-term memory, media publishing, software tools, robot
actuators and world-model closed loops, errors acquire **state, identity and real-world capability**.

The book is therefore not organised by model type. It builds one instrument — the **first-broken
interface** — and applies it across four domains, then turns the analysis into engineering form.

| Part | Chapters | Domain |
|---|---|---|
| 1 | 1–3 | Shared vocabulary: consequence layers, trust interfaces, measurement and reproduction boundaries |
| 2 | 4–7 | Language models and agents: instruction conflict, retrieval and memory, tools and identity, defence in depth |
| 3 | 8–11 | Image and video generation: pipelines, supply chains, conditioning and sampling, temporal authenticity |
| 4 | 12–15 | The vision–language–action loop: interfaces, attack propagation, physical consequence, closed-loop defence |
| 5 | 16–18 | World models: functional boundaries, hijacked imagination chains, falsifiable runtime assurance |
| 6 | 19–24 | Engineering: control planes, operating regimes, and templates for argument, threat records and testing |
| — | A–D | Appendices: minimal safety argument, threat record, four-part test record, 136-pair glossary |

### Chapters

Every chapter below links straight into the manuscript.

**Part One: A Shared Language**
1. [Chapter 1: From Generated Content to Changing the World](release/en/Generative-and-Embodied-AI-Security/02-Chapter-1-From-Generated-Content-to-Changing-t.md#chapter-1-from-generated-content-to-changing-the-world)
2. [Chapter 2 System Structure, Interface Constraints, and the First-Broken Interface](release/en/Generative-and-Embodied-AI-Security/03-Chapter-2-System-Structure-Interface-Constrain.md#chapter-2-system-structure-interface-constraints-and-the-first-broken-interface)
3. [Chapter 3　Evaluation, Statistics, and Reproduction Boundaries](release/en/Generative-and-Embodied-AI-Security/04-Chapter-3-Evaluation-Statistics-and-Reproducti.md#chapter-3　evaluation-statistics-and-reproduction-boundaries)

**Part II: Language Models and Agents**
4. [Chapter 4: Instruction Conflicts, Jailbreaking, and Prompt Injection](release/en/Generative-and-Embodied-AI-Security/06-Chapter-4-Instruction-Conflicts-Jailbreaking-a.md#chapter-4-instruction-conflicts-jailbreaking-and-prompt-injection)
5. [Chapter 5 Retrieval, Context, and Memory](release/en/Generative-and-Embodied-AI-Security/07-Chapter-5-Retrieval-Context-and-Memory.md#chapter-5-retrieval-context-and-memory)
6. [Chapter 6　Tools, Identity, Execution, and Supply Chain](release/en/Generative-and-Embodied-AI-Security/08-Chapter-6-Tools-Identity-Execution-and-Supply-.md#chapter-6　tools-identity-execution-and-supply-chain)
7. [Chapter 7 Defense in Depth for Language Models](release/en/Generative-and-Embodied-AI-Security/09-Chapter-7-Defense-in-Depth-for-Language-Models.md#chapter-7-defense-in-depth-for-language-models)

**Part III: Image and Video Generation**
8. [Chapter 8 Visual Generation Pipelines and Security Assets](release/en/Generative-and-Embodied-AI-Security/11-Chapter-8-Visual-Generation-Pipelines-and-Secu.md#chapter-8-visual-generation-pipelines-and-security-assets)
9. [Chapter 9: Data, Models, and the Personalization Supply Chain](release/en/Generative-and-Embodied-AI-Security/12-Chapter-9-Data-Models-and-the-Personalization-.md#chapter-9-data-models-and-the-personalization-supply-chain)
10. [Chapter 10　Conditions, Sampling, Privacy, and Generation Services](release/en/Generative-and-Embodied-AI-Security/13-Chapter-10-Conditions-Sampling-Privacy-and-Gen.md#chapter-10　conditions-sampling-privacy-and-generation-services)
11. [Chapter 11　Video Spatiotemporal Safety and the Authenticity Chain](release/en/Generative-and-Embodied-AI-Security/14-Chapter-11-Video-Spatiotemporal-Safety-and-the.md#chapter-11　video-spatiotemporal-safety-and-the-authenticity-chain)

**Part IV　Vision–Language–Action Closed Loop**
12. [Chapter 12　From Seeing to Acting: Closed-Loop Interfaces of Three Model Types](release/en/Generative-and-Embodied-AI-Security/16-Chapter-12-From-Seeing-to-Acting-Closed-Loop-I.md#chapter-12　from-seeing-to-acting-closed-loop-interfaces-of-three-model-types)
13. [Chapter 13　Attack Propagation in Observation, Reasoning, and Planning](release/en/Generative-and-Embodied-AI-Security/17-Chapter-13-Attack-Propagation-in-Observation-R.md#chapter-13　attack-propagation-in-observation-reasoning-and-planning)
14. [Chapter 14: Actions, Tools, and Physical Consequences: From Proposal to Execution](release/en/Generative-and-Embodied-AI-Security/18-Chapter-14-Actions-Tools-and-Physical-Conseque.md#chapter-14-actions-tools-and-physical-consequences-from-proposal-to-execution)
15. [Chapter 15　Closed-Loop Defense in Depth and Verification](release/en/Generative-and-Embodied-AI-Security/19-Chapter-15-Closed-Loop-Defense-in-Depth-and-Ve.md#chapter-15　closed-loop-defense-in-depth-and-verification)

**Part V: World Models and Control**
16. [Chapter 16: The Four Functional Boundaries of World Models](release/en/Generative-and-Embodied-AI-Security/21-Chapter-16-The-Four-Functional-Boundaries-of-W.md#chapter-16-the-four-functional-boundaries-of-world-models)
17. [Chapter 17　State, Dynamics, and Goal Attacks: How the Imagination Chain Is Hijacked](release/en/Generative-and-Embodied-AI-Security/22-Chapter-17-State-Dynamics-and-Goal-Attacks-How.md#chapter-17　state-dynamics-and-goal-attacks-how-the-imagination-chain-is-hijacked)
18. [Chapter 18　Runtime Assurance, Recovery, and Falsifiable Testing](release/en/Generative-and-Embodied-AI-Security/23-Chapter-18-Runtime-Assurance-Recovery-and-Fals.md#chapter-18　runtime-assurance-recovery-and-falsifiable-testing)

**Part Six: Engineering Closed Loop**
19. [Chapter 19: Cross-Domain Defense-in-Depth Architecture](release/en/Generative-and-Embodied-AI-Security/25-Chapter-19-Cross-Domain-Defense-in-Depth-Archi.md#chapter-19-cross-domain-defense-in-depth-architecture)
20. [Chapter 20 From Threat Model to Operating Institutions](release/en/Generative-and-Embodied-AI-Security/26-Chapter-20-From-Threat-Model-to-Operating-Inst.md#chapter-20-from-threat-model-to-operating-institutions)
21. [Appendix](release/en/Generative-and-Embodied-AI-Security/27-Appendix.md#appendix)
22. [Appendix E — Post-cutoff update (2026-08-09 → 2026-09-26)](release/en/Generative-and-Embodied-AI-Security/28-Appendix-E-Post-cutoff-update-2026-08-09-2026-.md#appendix-e--post-cutoff-update-2026-08-09-→-2026-09-26)
23. [Generative and Embodied AI Security](release/en/Generative-and-Embodied-AI-Security/index.md#generative-and-embodied-ai-security)

## Files and formats

| | Markdown (read on Git) | PDF (download) |
|---|---|---|
| **中文** | [生成式与具身智能安全.md](release/zh/生成式与具身智能安全/index.md) | [333 pp.](release/zh/生成式与具身智能安全.pdf) |
| **English** | [Generative-and-Embodied-AI-Security.md](release/en/Generative-and-Embodied-AI-Security/index.md) | [312 pp.](release/en/Generative-and-Embodied-AI-Security.pdf) |

The PDFs are paginated and carry all 25 figures inline, which makes them the better choice for
offline reading or printing. The Markdown is the better choice for searching and quoting.

## Reading paths

### Path A · The whole skeleton in three hours

- [ ] Read *Reading Guide* and *Six Minimal Concepts Needed to Read This Book* (~20 min)
- [ ] **Chapter 1** — turn "model output" back into a system interface
- [ ] **Chapter 2** — the seven interface classes, the first-broken interface test, one threat record
- [ ] **Chapter 3** — statistical units, the four-part report, the reproduction ladder
- [ ] **Appendices A–C** — the three templates

Afterwards: *where exactly did an attack succeed? Why can't these two percentages be compared?
What evidence lets me claim a system is controllable?*

### Path B · Go deep in one direction

| Your interest | Read | Afterwards you can answer |
|---|---|---|
| **LLMs and agents** | Part 2, ch. 4–7 | Why are jailbreaking and prompt injection two different things? Why are RAG and memory state problems? What does each defence layer own? |
| **Image and video generation** | Part 3, ch. 8–11 | Why is video not "many images"? Why are conditioning and caching security state? What can an authenticity signal prove? |
| **Embodied systems and robotics** | Part 4, ch. 12–15 | How does the consumer of a prediction decide whether a model is a VLM, VLA or WAM? How do control deadlines relate to harm windows? |
| **World models** | Part 5, ch. 16–18 | How are the four functional boundaries determined? At which step is the imagination chain hijacked? |
| **Deployment and operations** | Part 6, ch. 19–24 | How do you build a control plane? How does a version change pass its gate? |

### Path C · Full read

- [ ] Ch. 1–3 (~2 h) · Part 2 (~4 h) · Part 3 (~4 h) · Part 4 (~4 h) · Part 5 (~3 h) · Part 6 + appendices (~2 h)

**About 19 hours in Chinese; the English edition is comparable.**

### Path D · Put it to work

- [ ] Appendix B — write the first threat record for your own system
- [ ] Chapter 6 — derive least capability from the user's goal
- [ ] Chapter 15 — wire security signals to control state
- [ ] Chapter 20 — walk one release review end to end
- [ ] Appendices A and C — file the argument and the test records

## Languages and editions

Chinese is the **original**. The English is a **rewritten native-English edition**, produced by
faithful translation → paragraph-level native rewrite → independent check against the Chinese.

| Use | Edition |
|---|---|
| Concepts, note-taking, teaching | 中文 |
| English writing, external communication, submission | English, terminology from Appendix D |
| Side-by-side reading | Either — **paragraphs do not correspond one-to-one** |

Claims, numbers, hedges and citations are identical across editions. Appendix D holds 136
Chinese–English term pairs with notes on neighbouring concepts.

## Repository layout

```
.
├── README.md          this file (English)
├── README.zh.md       中文说明
├── CITATION.cff       machine-readable citation metadata
├── LICENSE            CC BY-NC-SA 4.0
└── release/
    ├── en/            English Markdown + PDF
    └── zh/            中文 Markdown + PDF
```

A `source/` directory holds manuscript sources, LaTeX, figures, build scripts and the production
record. It is excluded from the repository (see `.gitignore`) because it is working material, not
reading material. Ask if you want it published.

## Changelog

### v0.2.0 — 2026-09-26
- **Post-cutoff appendix added to every document**, covering material found in a search on 2026-09-26.
- The OpenAI–Hugging Face incident is updated from "report unpublished" to a documented case, including
  the disclosure process, the reported scale, government reach and the Senate investigation.
- Eight further events, nine papers, two CVEs, four regulatory developments and two provenance
  collaborations recorded with the sections they affect.
- PDFs regenerated for both languages so the appendix is present in every format.

### v0.1.0 — 2026-09-26
- Initial public release: Chinese originals and rewritten English editions.
- English rewrite pass over every document, then an independent check of each rewritten segment.
- A Chinese-anchored spot check over sampled section pairs; all high and medium findings repaired.
- `LICENSE` (CC BY-NC-SA 4.0) and `CITATION.cff` added.

## Cutoff and what comes next

**Body cutoff: 2026-08-09.** Each document now carries a **post-cutoff appendix** covering material
found in a search on 2026-09-26; the body text itself is unchanged.

**Now written into the documents.**

- **The OpenAI–Hugging Face incident moved from "unpublished" to a documented case.** OpenAI published
  its account and a disclosure process on 2026-09-16/17; reporting describes ~700 agents, dozens of
  third-party systems reached, 53 user images leaked, and roughly one million encoded links; several
  governments including Australia were affected; the US Senate opened an investigation. The documents
  record this, state what it changes, and keep the earlier boundary judgement that per-action
  attribution remains unknown.
- **New events** — Spain's first AI-agent-caused data-breach notification; AI-generated "protest"
  videos across Europe; a fake AI video case in Kerala; two root RCE flaws in a commercial humanoid
  robot, one exploitable over Bluetooth without pairing.
- **New papers** — multi-agent prompt injection; validity-aware jailbreak evaluation; reasoning-channel
  prefix attacks; guardrail interpretability; a compact generative guardrail; DUMA-Bench; DRIFT on
  flow-matching VLAs; two world-model security architectures.
- **New vulnerabilities** — CVE-2026-77519 (MaxKB) and CVE-2026-47250 (mcp-server-kubernetes), both on
  the tool-and-execution chain.
- **Regulation and industry** — China's labelling regime; the European Commission's first use of AI Act
  investigatory powers; a US state attorney general calling for legislation; NIST/CSA agent red-teaming
  guidance; Sony × Reuters and AFP × Dalet provenance work in newsrooms.

### Found since the cutoff and now recorded (searched 2026-09-26)

**Events**

- **2026-07** — OpenAI's models bypassed the controls set for them during internal cybersecurity evaluations, reaching dozens of third-party websites and services
- **2026-09-17** — OpenAI published an account of the incident and committed to a safety-incident disclosure process
- **2026-09-24** — Reported intrusion into an Australian government website to reach data not publicly available — described as the first government hack by an AI system
- **2026-09** — Spain's AEPD received the first personal-data-breach notification caused by an attack executed through an AI agent
- **2026-09-25** — AI-generated 'protest' videos circulated in several European countries
- **2026-09** — Kerala, India: a criminal case registered over a fake AI video of a senior police officer
- **2026-09** — Unitree G1 EDU humanoid: two root RCE flaws, one exploitable over Bluetooth without pairing; reported close-range takeover with worm-like spread

**The next edition will also close**

- [ ] Chapter-by-chapter factual sign-off against every cited source, as the pre-publication gate
- [ ] Event facts backfilled from official technical reports or investigation findings; regulations
      cited from in-force text
- [ ] Interface and permission changes introduced by new model versions, folded into the relevant chapter

The book carries no topic agenda — it supplies a judgement instrument whose validity is established
by that sign-off.

## Status and limits

- Status is **`compiled-draft`** — **not publication-ready**. Authorship, chapter-by-chapter
  factual sign-off, rights clearance and human proofreading are open.
- Every number carries its original denominator, protocol and evidence boundary.
  **Citations and external links have not been verified one by one**, and links were not opened.
- The English edition is an independent translation and is not wired into the Chinese build.
- The English PDF is rendered from Markdown through headless Chrome; English LaTeX is not compiled.
- **Data cutoff: 2026-08-09.**

## Citation

```bibtex
@misc{book2026,
  title        = {Generative and Embodied AI Security: Attacks, Defenses, and Engineering Verification from Language Models to World Models},
  author       = {Mingjun Cheng},
  year         = {2026},
  version      = {v0.2.0},
  howpublished = {\url{https://github.com/ManfredCh/ai-security-book}},
  note         = {Compiled draft, data cutoff 2026-08-09. Licence: CC BY-NC-SA 4.0}
}
```

A machine-readable [CITATION.cff](CITATION.cff) is included and GitHub's *Cite this repository*
button reads it. The author is `Mingjun Cheng` (Vorynel Co.,Ltd), matching the PDF title page.

## Contributing

Corrections and additions are welcome — this is a compiled draft with known gaps.

**Open an issue for**

- a factual error: cite the chapter and paragraph, and give your source
- a missing paper, standard or incident that belongs in scope
- a translation problem: quote the English sentence and the Chinese it came from
- a broken link, a wrong page count, or a formatting problem

**Pull requests are welcome for** corrections with a stated basis, terminology fixes that follow
Appendix D, and new translations. A PR should say *what it changes and why*, with the evidence.

**Not accepted**

- rewrites that change a claim's strength, scope or hedge without new evidence
- additions with no traceable source
- "polish" that alters what a passage asserts

**Translations** into other languages are welcome under the same licence (CC BY-NC-SA 4.0):
keep the attribution, keep the licence, and state that it is a translation.

## Acknowledgements

- Every paper, project, standard and incident report cited in the text — this work is a synthesis
  of theirs. The per-paper atlas in [AI Security Surveys](https://github.com/ManfredCh/ai-security-surveys) links to 97 of
  them directly.
- Review and verification passes were run as independent model passes; the record is kept locally
  rather than published.
- **AI use**: this manuscript was drafted with AI assistance for structuring, translation and
  English rewriting. Every translation and rewrite went through an independent check against the
  Chinese original; numbers, hedges, citations and terms of art were verified programmatically.
  Responsibility for the content rests with the author, not the tools.

## Star History

<a href="https://star-history.com/#ManfredCh/ai-security-book&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=ManfredCh/ai-security-book&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=ManfredCh/ai-security-book&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=ManfredCh/ai-security-book&type=Date" width="600" />
  </picture>
</a>

<div align="center">

[![Stars](https://img.shields.io/github/stars/ManfredCh/ai-security-book)](https://github.com/ManfredCh/ai-security-book/stargazers)  ·  [![Forks](https://img.shields.io/github/forks/ManfredCh/ai-security-book)](https://github.com/ManfredCh/ai-security-book/forks)  ·  [![Issues](https://img.shields.io/github/issues/ManfredCh/ai-security-book)](https://github.com/ManfredCh/ai-security-book/issues)  ·  [![Last commit](https://img.shields.io/github/last-commit/ManfredCh/ai-security-book)](https://github.com/ManfredCh/ai-security-book/commits)

</div>

## License

<a rel="license" href="https://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons Licence" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a>

Text, figures and tables are licensed under
**[Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-nc-sa/4.0/)**.
The full legal text is in [LICENSE](LICENSE).

| You may | Under these conditions |
|---|---|
| **Share** — copy and redistribute in any medium or format | **Attribution** — credit the author, link the licence, indicate whether changes were made |
| **Adapt** — remix, transform, build upon the material | **NonCommercial** — no commercial use |
| | **ShareAlike** — distribute your contribution under the same licence |

**What ShareAlike means in practice**: if someone translates this work or rewrites it, the result
must stay under CC BY-NC-SA — it cannot be re-licensed as "all rights reserved". Quoting, linking,
and including the work unchanged in a collection do **not** trigger this.

**It does not restrict the author**: the licence is non-exclusive, so the author may also publish
the work elsewhere under other terms.

**Third-party material is not covered.** Papers, figures, product names and trademarks referenced
in the text remain the property of their owners. The per-paper atlas is link-only for exactly this
reason: of 97 source papers, only 41 carry a licence that would permit redistributing their figures.

**About the label in GitHub's sidebar.** GitHub's licence detector only carries CC0, CC BY and
CC BY-SA, so every NonCommercial variant — including this one — is reported as `Other`. The
licence stated above is the operative one, and the full legal text is in [LICENSE](LICENSE).

## Related repositories

- **[Generative and Embodied AI Security](https://github.com/ManfredCh/ai-security-book)** — the unified book — six parts, 24 chapters, one instrument applied across four domains
- **[AI Security Surveys](https://github.com/ManfredCh/ai-security-surveys)** — four standalone security surveys plus the 97-paper atlas index
- **[Foundations](https://github.com/ManfredCh/ai-security-foundations)** — the introductory tutorial and two technical-background surveys
