<div align="center">

# Regit OS

### The Operating System for Investment Products.

One Golden Record per product. One runtime for the lifecycle.<br/>
Documents, filings, lookthrough, distribution: everything reads from the same source.

<p>
  <a href="https://www.regit.io"><img src="https://img.shields.io/badge/Built_in-Luxembourg-000000?style=flat-square" /></a>
  <img src="https://img.shields.io/badge/Core-Rust-CE422B?style=flat-square&logo=rust&logoColor=white" />
  <img src="https://img.shields.io/badge/Regit_OS-Proprietary-1f2937?style=flat-square" />
</p>

<a href="https://www.regit.io"><strong>regit.io</strong></a>
&nbsp;·&nbsp;
<a href="mailto:info@regit.io">info@regit.io</a>

<br/><br/>

<sub>
  <a href="#system">System</a> &nbsp;·&nbsp;
  <a href="#regulation-we-cover">Regulation</a> &nbsp;·&nbsp;
  <a href="#full-lookthrough-up-to-sicav-level">Lookthrough</a> &nbsp;·&nbsp;
  <a href="#coming-end-of-day-calc-engine-via-mcp">MCP</a> &nbsp;·&nbsp;
  <a href="#architecture">Architecture</a> &nbsp;·&nbsp;
  <a href="#the-platform">Platform</a> &nbsp;·&nbsp;
  <a href="#open-source">Open Source</a> &nbsp;·&nbsp;
  <a href="#compliance--standards">Compliance</a> &nbsp;·&nbsp;
  <a href="#engineering-posture">Posture</a> &nbsp;·&nbsp;
  <a href="#engineering-hiring">Hiring</a>
</sub>

</div>

---

## System

Asset Managers run their funds on fragmented vendors, manual labor, and legacy toolchains. **Regit OS** replaces that with a single hardened runtime that embeds the full toolchain for high-precision Asset Management.

> **1,000 compliant regulatory documents. 13 seconds. Single container. No gaps in the audit chain, by construction.**

A recipe change is a filing change. No release train. Your regulator asks where a number came from: one query, full chain.

> *One canonical product fact, many regulator-shaped projections.*

---

## Regulation We Cover

Decimal-deterministic. Audit-replayable. Same input produces byte-equal output by construction. All math is anchored to primary regulator text (EUR-Lex CELEX consolidated, FCA Handbook, ESMA / EIOPA / EBA / BIS Q&A). No vendor whitepapers. No blog summaries.

**EU regimes**

<p>
  <img src="https://img.shields.io/badge/PRIIPs_RTS-Cat_1--4-2563eb?style=flat-square" />
  <img src="https://img.shields.io/badge/SFDR-Art_8_%26_9_+_PAI-2563eb?style=flat-square" />
  <img src="https://img.shields.io/badge/Solvency_II-Pillar_1_%26_3-2563eb?style=flat-square" />
  <img src="https://img.shields.io/badge/UCITS_V-Dir_2009%2F65-2563eb?style=flat-square" />
  <img src="https://img.shields.io/badge/AIFMD_II-Dir_2024%2F927-2563eb?style=flat-square" />
  <img src="https://img.shields.io/badge/MiFID_II-Dir_2014%2F65-2563eb?style=flat-square" />
  <img src="https://img.shields.io/badge/EU_Taxonomy-CDR_2026%2F73-2563eb?style=flat-square" />
  <img src="https://img.shields.io/badge/BCBS_LCR-Reg_2015%2F61-2563eb?style=flat-square" />
  <img src="https://img.shields.io/badge/FinDatEx-EPT_EMT_EET_CEPT-2563eb?style=flat-square" />
</p>

**Cross-jurisdiction**

<p>
  <img src="https://img.shields.io/badge/UK_FCA-DISC_PS25%2F20-1f2937?style=flat-square" />
  <img src="https://img.shields.io/badge/UK_CCI-Live-1f2937?style=flat-square" />
  <img src="https://img.shields.io/badge/Swiss_FinSA-Art_58--63-1f2937?style=flat-square" />
  <img src="https://img.shields.io/badge/Swiss_FinSO-Annex_9-1f2937?style=flat-square" />
  <img src="https://img.shields.io/badge/GIPS-aligned-1f2937?style=flat-square" />
</p>

<sub>*Badges indicate implemented scope. Detailed coverage and versions in the tables below. Not a claim of full-regime coverage.*</sub>

### Document templates shipping

14 live templates across 6 regulatory regimes.

| Regime | Artifacts |
| :--- | :--- |
| **PRIIPs** | KID (Cat 1 Monte Carlo, Cat 2 VEV, Cat 3 daily-NAV bootstrap, Cat 4 IBIP biometric), SRI 7x6, RIY costs, CRM CR1..CR6 |
| **FinDatEx** | EPT V2.1, EMT V4.3, EET V1.1.3, CEPT V2.0 |
| **SFDR** | Article 8, Article 9, PAI Annex I Tables 1, 2, 3 |
| **Solvency II** | TPT V7.0, QRT S.06.02, S.06.03, S.08.01, S.11.01 |
| **UK FCA** | UK CCI (DISC PS25/20, commencement 6 Apr 2026, full go-live 8 Jun 2027) |
| **Swiss FinSA / FinSO** | Basisinformationsblatt (Art 58 to 63, Annex 9) |
| **Commercial** | Factsheet |

### Calculation frameworks (anchored to primary text)

| Framework | What we implement |
| :--- | :--- |
| **Solvency II Pillar 1** | SCR_Mkt 6-submodule aggregation, SCR_conc Art 183 to 187 (post-CDR 2026/269) |
| **EU Taxonomy** | KPI assembly, DNSH, GAR, opt-out Art 7(9), CDR 2026/73 Omnibus |
| **BCBS LCR** | HQLA, 30-day ratio, EU Reg 2015/61, AIFMD II LST per ESMA34-39-897 |
| **Performance (GIPS-aligned)** | TWR, annualised volatility, Sharpe, Sortino, max drawdown, rolling beta and alpha |
| **Audit & Provenance** | Bi-temporal storage. WORM-archived outputs as the regulatory record (S3 Object Lock). |

> *Replay is the load-bearing property. Archived output bytes are the regulatory record.*

### Tested like the regulator is watching

<p>
  <img src="https://img.shields.io/badge/Workspace_tests-1%2C415_passing-22c55e?style=flat-square" />
  <img src="https://img.shields.io/badge/Calculation_modules-17%2F17_verified-22c55e?style=flat-square" />
  <img src="https://img.shields.io/badge/Property_cases-4%2C096_per_release-22c55e?style=flat-square" />
  <img src="https://img.shields.io/badge/Independent_recheck-Decimal--50_precision-22c55e?style=flat-square" />
  <img src="https://img.shields.io/badge/RNG-Seed_pinned-22c55e?style=flat-square" />
</p>

Regulator-anchor gates reproduced byte-deterministically against published worked examples (Hull 15.6, ESMA flow JC 2017 49, ESAs Q&A JC 2023 18, BCBS 238 Annex 1, CIR 2023/894 Annex VI). Self-derived gates are honestly logged with full 50-digit-decimal transcripts. Every Monte Carlo run pins its RNG seed so validators can re-derive the byte stream.

---

## Full Lookthrough, Up to SICAV Level

See-through-the-fund resolution of holdings: SICAV, sub-funds, share classes, instruments. One canonical lookthrough dataset feeds every regulation that needs leaf-level effective exposure: Solvency II Art 84, UCITS V, AIFMD Annex IV, CRR / CRD, SFDR Art 7 to 9, MiFID II, FATCA / CRS.

| Capability | Detail |
| :--- | :--- |
| **Hierarchy** | Umbrella SICAV, sub-fund, share class, instrument. Recursive resolution with cycle and depth-limit policy that fails by default for regulated submissions. |
| **Effective weight** | Multi-path collapse with full path preservation. Forensic reconstruction is always available. |
| **Freshness** | Per-leaf freshness watermark. Bi-temporal valid-time and system-time, every fact, every regulator question. |
| **Deviations** | EU-vs-BCBS liquidity divergence captured as first-class rows (EHQ-CB, DGS-NFC, specialised-CI, Adj30). Pre-known carry-forward gaps catalogued per regulation. |
| **Replay** | Pin the input snapshot and the model version. Byte-equivalent re-run on demand. |

Concentration-by-vehicle, audit reconstruction, leaf-level effective exposure: same source, same answer.

---

## Coming End of Day: Calc Engine via MCP

The full Rust calc engine, exposed as a **Model Context Protocol** server. **Two weeks free** so your validators can hit it with anchor inputs and compare to our Decimal-50 transcripts.

<p>
  <img src="https://img.shields.io/badge/Distribution-StreamableHTTP_on_Cloudflare_Workers-2563eb?style=flat-square" />
  <img src="https://img.shields.io/badge/Trial-2_weeks_free-22c55e?style=flat-square" />
  <img src="https://img.shields.io/badge/I%2FO-JSON_Schema_typed-1f2937?style=flat-square" />
  <img src="https://img.shields.io/badge/Diagnostics-Replay--ready_envelope-1f2937?style=flat-square" />
</p>

Tools are organised by regulation, with strongly-typed JSON Schema I/O. Every response carries a diagnostics envelope: input echo, RNG seed, regulation version pin, deferred-features manifest. Regulator-grade replay is one re-call away.

Want early access? **[info@regit.io](mailto:info@regit.io)**.

---

## Architecture

| Layer | Technology | Function |
| :--- | :--- | :--- |
| **Core** | ![Rust](https://img.shields.io/badge/Rust-CE422B?style=flat-square&logo=rust&logoColor=white) | High-precision processing. 12 crates, 17 calculation modules code-complete. |
| **Data** | ![Iceberg](https://img.shields.io/badge/Iceberg-Parquet-2563eb?style=flat-square) | Golden Record. Bi-temporal versioning. Medallion architecture. |
| **Shell** | ![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB) | Unified workspace for Product and Compliance. |
| **Provisioning** | ![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white) | Infrastructure as Code. Sovereign, private, or public cloud. |
| **Runtime** | ![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white) | Serverless workloads on Kubernetes. Distroless images: no shell, no package manager, minimal attack surface. Scales to zero. |
| **Supply Chain** | ![SBOM](https://img.shields.io/badge/SBOM-Permissive_only-1f2937?style=flat-square) | Zero copyleft dependencies. Clean SBOM. Audit-ready for DORA ICT third-party risk (Art 28 to 30). |
| **Identity** | ![OIDC](https://img.shields.io/badge/OIDC-Keycloak-FF6B00?style=flat-square) | RBAC for Portfolio Managers, Compliance, and Auditors. |
| **Audit** | ![WORM](https://img.shields.io/badge/WORM-S3_Object_Lock-1f2937?style=flat-square) | Outputs are immutable. Operational and structural provenance, separately. |
| **Agents** | ![Deterministic](https://img.shields.io/badge/Agents-Deterministic-6e40c9?style=flat-square) | Audited, traceable. LLM-free in regulated calc paths. |

---

## The Platform

One Golden Record. Two modules live.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/platform-dark.svg">
  <img alt="Regit OS platform diagram. Fragmented data flows on the left, through Governance and the Golden Record, into module pillars (Documents, Distribution, Portfolio, Lifecycle, Onboarding), out to regulated assets on the right." src="assets/platform-light.svg" width="100%">
</picture>

| Module | Status |
| :--- | :--- |
| Documents | Live |
| Distribution (regulators, partners, web) | Live |
| Portfolio (holdings, analytics, attribution) | In progress |
| Lifecycle (regulatory watch, lifecycle events) | Planned |
| Onboarding (KYC, subscriptions, redemptions) | Planned |

---

## Open Source

Regit OS itself is proprietary and unpublished. A few of the underlying crates ship under Apache 2.0 so the community can verify the math.

### [regit-blackscholes](https://github.com/org-regit-io/regit-blackscholes)

<p>
  <a href="https://crates.io/crates/regit-blackscholes"><img alt="crates.io" src="https://img.shields.io/crates/v/regit-blackscholes?style=flat-square&color=ff9b3f&logo=rust&logoColor=white" /></a>
  <a href="https://docs.rs/regit-blackscholes"><img alt="docs.rs" src="https://img.shields.io/docsrs/regit-blackscholes?style=flat-square&color=2563eb&logo=docsdotrs&logoColor=white" /></a>
  <a href="https://crates.io/crates/regit-blackscholes"><img alt="Downloads" src="https://img.shields.io/crates/d/regit-blackscholes?style=flat-square&color=1f2937&logo=rust&logoColor=white" /></a>
  <img alt="License" src="https://img.shields.io/badge/license-Apache_2.0-22c55e?style=flat-square" />
</p>

Zero-dependency Black-Scholes options pricing engine in pure Rust. 4 models, 17 analytic Greeks, multi-strategy IV solver. Sub-5ns normal CDF.

```sh
cargo add regit-blackscholes
```

### [regit-covariance](https://github.com/org-regit-io/regit-covariance)

<p>
  <a href="https://crates.io/crates/regit-covariance"><img alt="crates.io" src="https://img.shields.io/crates/v/regit-covariance?style=flat-square&color=ff9b3f&logo=rust&logoColor=white" /></a>
  <a href="https://docs.rs/regit-covariance"><img alt="docs.rs" src="https://img.shields.io/docsrs/regit-covariance?style=flat-square&color=2563eb&logo=docsdotrs&logoColor=white" /></a>
  <a href="https://crates.io/crates/regit-covariance"><img alt="Downloads" src="https://img.shields.io/crates/d/regit-covariance?style=flat-square&color=1f2937&logo=rust&logoColor=white" /></a>
  <img alt="License" src="https://img.shields.io/badge/license-Apache_2.0-22c55e?style=flat-square" />
</p>

Covariance matrix denoising for financial risk validation. Marchenko-Pastur filtering, Ledoit-Wolf shrinkage, detoning. Built to validate PRIIPs risk metrics.

```sh
cargo add regit-covariance
```

### [regit-svi](https://github.com/org-regit-io/regit-svi)

<p>
  <a href="https://crates.io/crates/regit-svi"><img alt="crates.io" src="https://img.shields.io/crates/v/regit-svi?style=flat-square&color=ff9b3f&logo=rust&logoColor=white" /></a>
  <a href="https://docs.rs/regit-svi"><img alt="docs.rs" src="https://img.shields.io/docsrs/regit-svi?style=flat-square&color=2563eb&logo=docsdotrs&logoColor=white" /></a>
  <a href="https://crates.io/crates/regit-svi"><img alt="Downloads" src="https://img.shields.io/crates/d/regit-svi?style=flat-square&color=1f2937&logo=rust&logoColor=white" /></a>
  <img alt="License" src="https://img.shields.io/badge/license-Apache_2.0-22c55e?style=flat-square" />
</p>

Arbitrage-free SVI volatility surfaces in pure Rust. Raw, Jump-Wings and SSVI parametrisations, quasi-explicit and Levenberg-Marquardt calibration, butterfly and calendar-spread arbitrage checks. Zero dependencies.

```sh
cargo add regit-svi
```

### [regit-identifiers](https://github.com/org-regit-io/regit-identifiers)

<p>
  <a href="https://crates.io/crates/regit-identifiers"><img alt="crates.io" src="https://img.shields.io/crates/v/regit-identifiers?style=flat-square&color=ff9b3f&logo=rust&logoColor=white" /></a>
  <a href="https://docs.rs/regit-identifiers"><img alt="docs.rs" src="https://img.shields.io/docsrs/regit-identifiers?style=flat-square&color=2563eb&logo=docsdotrs&logoColor=white" /></a>
  <a href="https://crates.io/crates/regit-identifiers"><img alt="Downloads" src="https://img.shields.io/crates/d/regit-identifiers?style=flat-square&color=1f2937&logo=rust&logoColor=white" /></a>
  <img alt="License" src="https://img.shields.io/badge/license-Apache_2.0-22c55e?style=flat-square" />
</p>

Securities identifier validation in pure Rust — ISIN, CUSIP, SEDOL, LEI, BIC, MIC, FIGI, CFI and national numbers. Check-digit algorithms hand-rolled from each governing standard, ISO 10383 MIC registry embedded. Zero dependencies, `no_std`, no `alloc`.

```sh
cargo add regit-identifiers
```

### [regit-daycount](https://github.com/org-regit-io/regit-daycount)

<p>
  <a href="https://crates.io/crates/regit-daycount"><img alt="crates.io" src="https://img.shields.io/crates/v/regit-daycount?style=flat-square&color=ff9b3f&logo=rust&logoColor=white" /></a>
  <a href="https://docs.rs/regit-daycount"><img alt="docs.rs" src="https://img.shields.io/docsrs/regit-daycount?style=flat-square&color=2563eb&logo=docsdotrs&logoColor=white" /></a>
  <a href="https://crates.io/crates/regit-daycount"><img alt="Downloads" src="https://img.shields.io/crates/d/regit-daycount?style=flat-square&color=1f2937&logo=rust&logoColor=white" /></a>
  <img alt="License" src="https://img.shields.io/badge/license-Apache_2.0-22c55e?style=flat-square" />
</p>

Day-count fractions and business-day calendars in pure Rust — every ISDA 2006 §4.16 convention plus ICMA Rule 251 (Act/360, Act/365F, Act/Act ISDA & ICMA, 30/360 family, Act/365L, NL/365, Bus/252, 1/1), the full date-roll catalogue, and eight holiday calendars (TARGET2 and Luxembourg as rule-based generators; US, UK, Japan, Switzerland, Hong Kong, Singapore as 2020–2040 snapshots cross-verified against primary published sources). Zero dependencies, `no_std`, no `alloc`.

```sh
cargo add regit-daycount
```

---

## Compliance & Standards

Built natively to EU institutional expectations.

**Today**

<p>
  <img src="https://img.shields.io/badge/NIST_800--53v5-Aligned-000000?style=flat-square" />
  <img src="https://img.shields.io/badge/GDPR-Native-2563eb?style=flat-square" />
  <img src="https://img.shields.io/badge/DORA-Aligned-2563eb?style=flat-square" />
  <img src="https://img.shields.io/badge/PRIIPs_RTS-Implemented-2563eb?style=flat-square" />
  <img src="https://img.shields.io/badge/EU_Data_Residency-Available-2563eb?style=flat-square" />
</p>

**Roadmap**

<p>
  <img src="https://img.shields.io/badge/SOC_2_Type_II-Roadmap-6b7280?style=flat-square" />
  <img src="https://img.shields.io/badge/ISO%2FIEC_27001-Roadmap-6b7280?style=flat-square" />
  <img src="https://img.shields.io/badge/ISAE_3402-Roadmap-6b7280?style=flat-square" />
</p>

Deployable on sovereign, private, or public cloud. Data residency available on request.

---

## Engineering Posture

Decisions we took on day one, that most regulated SaaS still hasn't.

- **Pure Rust core.** No GC pauses. No unintended floats. Decimal precision is the default, not the exception.
- **Distroless containers.** No shell, no package manager, no surprise CVE. Minimal attack surface.
- **Zero copyleft dependencies.** Permissive-only SBOM. Audit-ready under DORA Art 28 to 30.
- **Deterministic by construction.** Same input, byte-equal output. RNG seeds travel in the response, not buried in logs.
- **Outputs as the regulatory record.** Bi-temporal storage means "the document we sent on date D" is one query, not a re-derivation.
- **LLM-free in regulated calc paths.** Agents help operators. They never derive a number a regulator will see.

---

## Engineering Hiring

We hire small. We hold a high bar. We pay for output, not hours.

If you are a Rust engineer who would rather solve a regulator-anchor than attend a scrum meeting, we want to read your code. Send your **GitHub** first, **CV** second, to **[info@regit.io](mailto:info@regit.io)**.

The crates above ([regit-blackscholes](https://github.com/org-regit-io/regit-blackscholes), [regit-covariance](https://github.com/org-regit-io/regit-covariance), [regit-svi](https://github.com/org-regit-io/regit-svi), [regit-identifiers](https://github.com/org-regit-io/regit-identifiers), [regit-daycount](https://github.com/org-regit-io/regit-daycount)) are a fair sample of the bar.

---

<div align="center">

**Regit.io.** The Operating System for Investment Products.<br/>
Luxembourg · [regit.io](https://www.regit.io) · [info@regit.io](mailto:info@regit.io)

</div>
