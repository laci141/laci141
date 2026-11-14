# Hi, I'm Laci 👋

CNC operator by trade, Go developer by choice. I build **open-data research tools for science, medicine and funding** — every result links back to its public source, nothing is a black-box score.

📍 Oradea, Romania

---

## 🔭 Pubvera — eight open-data research apps

**[🌐 pubvera.com →](https://pubvera.com/)**

| App | What it does | Open data behind it | Source |
|---|---|---|---|
| [Corpova](https://corpova.pubvera.com/) | Evidence consensus analysis — claim-level verdicts computed from the scientific literature | OpenAlex | [repo](https://github.com/laci141/pubvera-corpova) |
| [Bibliovera](https://bibliovera.pubvera.com/) | Journal bibliometrics — institution growth, author rankings and topic trends | OpenAlex (The Lancet corpus) | [repo](https://github.com/laci141/pubvera-bibliovera) |
| [Praxvera](https://praxvera.pubvera.com/) | Clinical literature search with full abstracts | OpenAlex | [repo](https://github.com/laci141/pubvera-praxvera) |
| [Trialvera](https://trialvera.pubvera.com/) | Clinical trial search and analysis | ClinicalTrials.gov, PubMed, OpenAlex, FAERS | [repo](https://github.com/laci141/pubvera-trialvera) |
| [Devicera](https://devicera.pubvera.com/) | Medical device intelligence — registrations, UDI codes, FDA regulatory status | openFDA, GUDID, MAUDE | [repo](https://github.com/laci141/pubvera-devicera) |
| [Retractis](https://retractis.pubvera.com/) | Retraction and research-integrity checker — is a paper retracted, and what supersedes it? | Crossref, OpenAlex | [repo](https://github.com/laci141/pubvera-retractis) |
| [Recallis](https://recallis.pubvera.com/) | Drug recall and enforcement search | openFDA | [repo](https://github.com/laci141/pubvera-recallis) |
| [Grantvera](https://grantvera.pubvera.com/) | Research grant and funding search | NIH RePORTER, NSF, Grants.gov | [repo](https://github.com/laci141/pubvera-grantvera) |

**How it is built**

- **One pattern, eight times:** a small Go server, a single-page frontend, and a CLI doing the data work — the same CLIs I maintain upstream (below).
- **Security:** per-response nonce Content-Security-Policy (no inline handlers, `connect-src` allow-list), containers run as a non-root user, `govulncheck` and Dependabot in CI, every GitHub Action pinned to a commit SHA.
- **Tested:** 870+ Go test functions and 150+ JavaScript test files across the eight repos; a fix ships only after a deliberate mutation proves the test can fail.
- **Honest output:** charts and tables say what they count, name their sample, and export to CSV / Excel / BibTeX / JSON.

---

## 🛠 Upstream — [printing-press-library](https://github.com/mvanhorn/printing-press-library)

**[61 merged pull requests](https://github.com/mvanhorn/printing-press-library/pulls?q=is%3Apr+author%3Alaci141+is%3Amerged)** (July – November 2026): seven CLIs contributed, then maintained with small, test-backed fixes.

| CLI | First PR | What it does | Powers |
|---|---|---|---|
| scientific-consensus | [#1309](https://github.com/mvanhorn/printing-press-library/pull/1309) | Claim-level evidence scoring: study-design tiers, relevance gate, retraction exclusion | Corpova |
| thelancet | [#1256](https://github.com/mvanhorn/printing-press-library/pull/1256) | Journal metadata explorer: authors, affiliations, citation velocity | Bibliovera |
| nejm | [#1328](https://github.com/mvanhorn/printing-press-library/pull/1328) | Clinical article search over OpenAlex | Praxvera |
| clinical-trials | [#1356](https://github.com/mvanhorn/printing-press-library/pull/1356) | ClinicalTrials.gov search, comparison, risk and phase analysis | Trialvera |
| retraction-checker | [#1438](https://github.com/mvanhorn/printing-press-library/pull/1438) | Retraction and superseding-research checks (Crossref, OpenAlex) | Retractis |
| drug-enforcement | [#1453](https://github.com/mvanhorn/printing-press-library/pull/1453) | FDA drug recall and enforcement data | Recallis |
| grants | [#1443](https://github.com/mvanhorn/printing-press-library/pull/1443) | NIH RePORTER, NSF and Grants.gov funding search | Grantvera |

A few fixes that changed results:

- [#1948](https://github.com/mvanhorn/printing-press-library/pull/1948) — retraction-checker read the wrong Crossref field (`update-by` instead of `updated-by`)
- [#2297](https://github.com/mvanhorn/printing-press-library/pull/2297) — same-title, same-year twins of retracted works no longer count toward a consensus score
- [#1906](https://github.com/mvanhorn/printing-press-library/pull/1906) — the registry's `UNKNOWN` trial status is scored as an unknown state
- [#1689](https://github.com/mvanhorn/printing-press-library/pull/1689) — NIH and NSF keyword searches no longer return off-topic awards
- [#2282](https://github.com/mvanhorn/printing-press-library/pull/2282) — thelancet dedupes works by DOI on upsert

---

## 🌌 Side projects — small, self-contained, no tracking

**Science you can play with**

| Project | What it is |
|---|---|
| [Density Wave](https://galaxy-90m.pages.dev/) · [source](https://github.com/laci141/galaxy) | Interactive spiral galaxy built on density wave theory — one HTML file, Canvas 2D + Web Audio, four languages |
| [Orrery](https://github.com/laci141/orrery) | Keplerian Solar System: shaded planets, twin-tailed comets, procedural sound |
| [Aurora](https://github.com/laci141/aurora) | Aurora borealis simulator: solar storms, magnetosphere physics, dancing curtains |

**How the body works**

| Project | What it is |
|---|---|
| [Respiration](https://respiration.pages.dev/) · [source](https://github.com/laci141/Respiration) | Ten guided breathing techniques and the journey of air through the body in eleven stations |
| [Fasting](https://fastingmap.pages.dev/) · [source](https://github.com/laci141/fasting) | What happens in the body during a fast — mechanism, not rules; every figure carries an evidence badge |
| [Medicinal Seed Atlas](https://medicinal-seed-atlas.pages.dev/) · [source](https://github.com/laci141/medicinal-seed-atlas) | Evidence-rated atlas of 15 edible seeds: flashcards, nutrient table, PubMed-linked research |
| [Clinical Tea Cards](https://github.com/laci141/medicinal-tea-atlas) | Cards for 34 medicinal teas with the clinical studies behind each one |

**Weather and calm**

| Project | What it is |
|---|---|
| [Weather](https://weather-web.pages.dev/) · [source](https://github.com/laci141/weather-web) | Forecast, history back to 1940, climate anomaly and trend panels, bulk export — keyless, on Open-Meteo |
| [Tengermoraj](https://beach-542.pages.dev/) · [source](https://github.com/laci141/Beach) | Ocean ambience: animated seascapes with fully synthesised sound, no audio files |
| [Winter Cabin](https://github.com/laci141/wintercabin) | Animated winter scene with falling snow and a procedural soundtrack |

**From the workshop**

| Project | What it is |
|---|---|
| [CNC M-code dashboard](https://github.com/laci141/cnc-mcode) · [CLI](https://github.com/laci141/cnc-code) | M-code reference for CNC operators, as a web dashboard and a Go CLI |

---

## 🧰 Stack

`Go` · `SQLite` · `Docker` · `Caddy` · `Cloudflare Pages` · `GitHub Actions` · `JavaScript (no framework)` · `Playwright` · `Kotlin/Compose (Android)`

---

*All tools are for education and research — never medical advice.*
