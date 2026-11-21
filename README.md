<div align="center">

# awesome-ad-fraud

**A curated, link-verified collection of open-source tools, datasets, standards, and primary research for detecting, measuring, and eliminating ad fraud and invalid traffic (IVT) in the digital advertising supply chain.**

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](#contributing)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0--1.0-lightgrey.svg)](LICENSE)

</div>

---

> **Scope note:** Open-source software and primary sources (specifications, datasets, peer-reviewed research, official enforcement actions) are prioritized. Commercial vendors appear only where they are the authoritative public source — e.g., standards-setting bodies and landmark industry studies. Every link in this list was opened and verified in November 2026; if you find a dead link, please [open an issue](../../issues).

## Table of Contents

1. [Supply Chain Transparency (ads.txt, app-ads.txt, sellers.json)](#supply-chain-transparency-adstxt-app-adstxt-sellersjson)
2. [Bot Detection & Fingerprinting (Open Source)](#bot-detection--fingerprinting-open-source)
3. [IVT, Click Fraud & MFA (Made for Advertising) Research](#ivt-click-fraud--mfa-made-for-advertising-research)
4. [Standards & Specifications](#standards--specifications)
5. [Datasets & Benchmarks](#datasets--benchmarks)
6. [Browser Extensions & Inspection Tools](#browser-extensions--inspection-tools)
7. [Books, Talks & Blogs](#books-talks--blogs)

- [Contributing](#contributing)
- [License](#license)

---

## Supply Chain Transparency (ads.txt, app-ads.txt, sellers.json)

*Parsers, validators, and crawlers for the three IAB transparency files that let buyers verify who is authorized to sell which inventory. Spec authors: ads.txt / app-ads.txt 1.1 live in the [Supply-Chain-Validation](https://github.com/InteractiveAdvertisingBureau/Supply-Chain-Validation) repo; see [Standards & Specifications](#standards--specifications).*

### Reference implementations

- [IAB Tech Lab ads.txt Crawler](https://github.com/InteractiveAdvertisingBureau/adstxtcrawler) - Official Python reference crawler that discovers publishers' ads.txt files and stores them in SQLite for modest production use.
- [IAB Tech Lab ads.txt Parser](https://github.com/InteractiveAdvertisingBureau/ads.txt-parser) - Official reference implementation for ads.txt parsing and app-ads.txt app-store metadata canonicalization.

### Libraries & validators

- [ads.txt](https://github.com/perry-mitchell/ads.txt) - TypeScript ads.txt parser and generator, published on npm as `ads.txt`.
- [sellers.json](https://github.com/perry-mitchell/sellers.json) - TypeScript sellers.json generator and parser, published on npm as `sellers.json`.
- [adstxt-validator](https://www.npmjs.com/package/adstxt-validator) - TypeScript library for validating ads.txt / app-ads.txt files and sellers.json against the IAB Tech Lab specifications.
- [go-adstxt](https://github.com/suzuken/go-adstxt) - Minimal, dependency-light ads.txt parser written in Go.
- [AppGoblin adscrawler](https://github.com/appgoblin-dev/adscrawler) - Crawler that discovers ads.txt files across the Google and Apple app stores, SDKs, and app-ads.txt endpoints.

### Publisher-side management

- [Ads.txt Manager (10up)](https://github.com/10up/ads-txt) - WordPress plugin for creating and maintaining ads.txt and app-ads.txt files from the admin dashboard.

---

## Bot Detection & Fingerprinting (Open Source)

*Libraries and public resources for detecting automated traffic — and for understanding how sophisticated headless browsers evade detection.*

### Detection libraries

- [BotD](https://github.com/fingerprintjs/BotD) - Free, open-source client-side bot detection from the FingerprintJS team; flags automation tools and headless browsers in the browser.
- [FingerprintJS](https://github.com/fingerprintjs/fingerprintjs) - The open-source (MIT) browser fingerprinting library for identifying devices and detecting fingerprint inconsistencies.
- [CreepJS](https://github.com/abrahamjuliot/creepjs) - Open research project mapping fingerprinting entropy signals and stealth evasions — the reference for what a fingerprinter can actually observe.
- [Matomo Device Detector](https://github.com/matomo-org/device-detector) - Universal device/browser/OS detection with a community-maintained regex database; widely used for bot and device classification.

### User-Agent parsing

- [UAParser.js](https://github.com/faisalman/ua-parser-js) - The de-facto JavaScript user-agent parser (browser, engine, OS, device, CPU).
- [uap-core](https://github.com/ua-parser/uap-core) - Canonical YAML regex database powering every ua-parser port across Java, Python, Ruby, Go and more.
- [uap-python](https://github.com/ua-parser/uap-python) - Python port of ua-parser built directly on uap-core.
- [Bowser](https://github.com/bowser-js/bowser) - Lightweight, maintained JavaScript browser/OS/platform detector; a compact alternative to UAParser.js.

### Evasion research (what detection must catch)

- [puppeteer-extra](https://github.com/berstend/puppeteer-extra) - Plugin framework for Puppeteer shipping the stealth evasions that make headless Chrome look human — the exact playbook bot detectors must defeat.
- [fingerprint-suite](https://github.com/apify/fingerprint-suite) - Open-source fingerprint generation and anonymization toolkit from Apify; useful for red-teaming your own detection logic.

### Public bot registries

- [IAB Tech Lab Spiders & Bots list](https://iabtechlab.com/standards/measurement/) - Maintained registry of known automated traffic (search crawlers, monitors, and malicious bots) used to exclude non-human hits from billable counts; see the Measurement pillar.

---

## IVT, Click Fraud & MFA (Made for Advertising) Research

*Landmark papers, enforcement actions, and investigative work on invalid traffic, click fraud, and Made-for-Advertising inventory.*

### Landmark studies & whitepapers

- [Detecting Click Fraud in Online Advertising: A Data Mining Approach (JMLR, 2014)](https://www.jmlr.org/papers/v15/oentaryo14a.html) - Oentaryo et al.'s analysis of the FDMA 2012 (BuzzCity) mobile click-fraud competition — the canonical academic reference for publisher-side click fraud.
- [MCCF: Multimodal and Contrastive Learning for Click Fraud Detection (WWW '21 DeMaL)](https://arxiv.org/abs/2105.03567) - Li & Zhong et al.'s contrastive-learning model trained on Alibaba-scale advertising traffic (arXiv:2105.03567).
- [ANA Programmatic Media Supply Chain Transparency Study (2023)](https://www.ana.net/content/show/id/pr-2023-06-programmaticstudy) - Log-level audit of 21 advertisers ($123M spend, 35.5B impressions): ~23% open-web waste, with MFA sites taking 21% of impressions and 15% of spend.
- [Adalytics](https://adalytics.io/) - Research outfit behind the 2023 Google Video Partners investigation showing large shares of TrueView spend ran as muted or out-stream placements on ineligible sites and apps.

### Law enforcement & regulatory

- [U.S. DOJ EDNY — Methbot / 3ve indictment (November 2018)](https://www.justice.gov/usao-edny/pr/two-international-cybercriminal-rings-dismantled-and-eight-defendants-indicted-causing) - Indictment of eight defendants across two schemes totalling tens of millions in losses — the definitive public record on Methbot and 3ve.

### Investigative journalism & watchdogs

- [Krebs on Security — "$3-5M in Ad Fraud Daily from Methbot" (2016)](https://krebsonsecurity.com/2016/12/report-3-5m-in-ad-fraud-daily-from-methbot/) - Brian Krebs's reporting that took the WhiteOps Methbot investigation public.
- [HUMAN Security](https://www.humansecurity.com/) - Formerly White Ops (now HUMAN Security); publisher of the Methbot, Hyphbot, 3ve and BADBOX research that shaped modern IVT detection.
- [Check My Ads Institute](https://checkmyads.org/) - Publisher-side watchdog documenting MFA arbitrage and ad-tech waste, with evidence filed in regulatory proceedings.
- [Digiday — "WTF are made-for-advertising sites?"](https://digiday.com/marketing/wtf-are-made-for-advertising-sites-mfas/) - A concise, data-grounded explainer on MFA inventory and why it passes verification stacks.

---

## Standards & Specifications

*The IAB Tech Lab specifications that anti-fraud work is built on — read these before writing any detection logic.*

### Supply chain transparency

- [ads.txt / app-ads.txt (IAB Tech Lab)](https://iabtechlab.com/ads-txt/) - Authorized Digital Sellers standard (ads.txt 1.1, August 2022, adding OWNERDOMAIN/MANAGERDOMAIN) for declaring who may sell web and app inventory.
- [Supply-Chain-Validation](https://github.com/InteractiveAdvertisingBureau/Supply-Chain-Validation) - The canonical markdown spec sources for ads.txt, app-ads.txt, and sellers.json — the single source of truth for the spec text.
- [sellers.json](https://iabtechlab.com/sellers-json/) - Machine-readable file SSPs and exchanges host at the domain root so buyers can verify every seller and intermediary (final spec, July 2019).
- [SupplyChain Object (schain)](https://github.com/InteractiveAdvertisingBureau/openrtb/blob/master/supplychainobject.md) - OpenRTB extension listing every party selling or reselling an impression; each node cross-checks against sellers.json via ASI/PID/RID.
- [Buyers.json & DemandChain Object](https://iabtechlab.com/buyers-json-demand-chain/) - The buy-side mirror of sellers.json / schain — declares demand-side buyers to help publishers identify malvertising sources.

### Measurement & integrity

- [Open Measurement SDK (OM SDK)](https://iabtechlab.com/standards/open-measurement-sdk/) - Standardized third-party viewability and verification signals for web, in-app, and CTV via the OMID APIs (JS, Android, iOS, tvOS).
- [Open-Measurement-JSClients](https://github.com/InteractiveAdvertisingBureau/Open-Measurement-JSClients) - IAB Tech Lab's JavaScript OMID client implementations — the interop target for verification providers.
- [ads.cert 2.0](https://iabtechlab.com/standards/ads-cert/) - Protocol suite (Call Signs, Authenticated Connections) that cryptographically signs programmatic requests using DNS-published keys; aimed at SSAI and CTV fraud.
- [adscert (reference implementation)](https://github.com/IABTechLab/adscert) - IAB Tech Lab proof-of-concept Go implementation of the Authenticated Connections protocol (explicitly not for production).

### Transaction standards

- [OpenRTB 3.0](https://github.com/InteractiveAdvertisingBureau/openrtb) - Real-time bidding protocol 3.0 (with AdCOM); schain moved into the source object here.
- [OpenRTB 2.x](https://github.com/InteractiveAdvertisingBureau/openrtb2.x) - Maintained 2.x specification line (2.6.x) — where most in-market schain traffic lives today.
- [VAST](https://github.com/InteractiveAdvertisingBureau/VAST) - Video Ad Serving Template — required context for interpreting video IVT and quartile metrics.
- [TAG Certified Against Fraud](https://www.tagtoday.net/certifications) - Trustworthy Accountability Group certification for IVT controls; its 2019 benchmark found Certified channels at ~1.41% IVT, an ~88% reduction vs. the industry average.

---

## Datasets & Benchmarks

*Public data you can use to train, evaluate, or sanity-check fraud-detection models. Public labeled click-fraud data is scarce — know your limitations before publishing results.*

- [TalkingData AdTracking Fraud Detection Challenge (Kaggle, 2018)](https://www.kaggle.com/competitions/talkingdata-adtracking-fraud-detection/overview) - ~200M labeled mobile ad clicks over 4 days — the de-facto public benchmark for click-fraud models.
- [ad-inventory-fraud-measurement](https://github.com/Yash-Vekaria/ad-inventory-fraud-measurement) - Code and measurement pipeline from a published study of ads.txt/sellers.json misrepresentation and "dark pooling" in programmatic supply; a solid template for your own audits.
- [OpenSincera](https://www.thetradedesk.com/resources/what-is-opensincera) - Free API and open dataset of ad-experience metrics across 400k+ publishers (ads in view, ads-to-content ratio, refresh rate, page weight) built from Sincera's synthetic-user crawling.
- [opensincera-cli](https://github.com/miyaichi/opensincera-cli) - Command-line client for querying OpenSincera's publisher transparency metrics; handy for bulk quality audits.
- [Fraud Detection Dataset (Kaggle)](https://www.kaggle.com/datasets/ziya07/fraud-detection-dataset) - Small synthetic CPA click-fraud dataset (~5k rows); suitable only for smoke-testing pipelines, not for credible evaluation.

*Note: the MCCF (Alibaba) and FDMA 2012 (BuzzCity) datasets are referenced in the papers above but are no longer broadly distributed; TalkingData remains the standard public benchmark.*

---

## Browser Extensions & Inspection Tools

*Tools for inspecting ad calls, redirects, tracking tech, and viewability on live pages.*

### Network & proxy analysis

- [mitmproxy](https://github.com/mitmproxy/mitmproxy) - Interactive, TLS-capable intercepting proxy with scriptable Python hooks — the Swiss-army knife for tracing ad call chains and redirects.
- [Wireshark](https://github.com/wireshark/wireshark) - Packet-level protocol analyzer for verifying what actually left the device versus what ad SDKs claim to send.
- [WebPageTest](https://github.com/catchpoint/WebPageTest) - Open-source waterfall testing (hosted or self-hosted) capturing every request on a page, including ad calls, with request maps and filmstrips.
- [Chrome DevTools — Network panel](https://developer.chrome.com/docs/devtools/network/) - Built-in request log with timing waterfall; use `Initiator` and domain filters to isolate ad-serving endpoints.

### Browser extensions

- [Tag Assistant (by Google)](https://chromewebstore.google.com/detail/tag-assistant/kejbdjndbnbjgmefkgdddjlbokphdefk) - Official Chrome extension; pairs with tagassistant.google.com to verify which Google tags (Analytics, Ads, GTM) actually fire on a page.
- [Meta Ads Data Advisor](https://developers.facebook.com/docs/meta-pixel/support/pixel-helper/) - Meta's official diagnostic extension (formerly Facebook Pixel Helper) for auditing Pixel and Conversions API events on live pages.
- [uBlock Origin](https://github.com/gorhill/uBlock) - Network request blocker with request logging and element picking — useful for isolating ad calls and diffing page behavior.

### Ad-tech scanners

- [The Markup's Blacklight](https://themarkup.org/blacklight/) - Real-time site inspector revealing ad trackers, session recorders, keyloggers, and other third-party ad tech on any URL.
- [blacklight-collector](https://github.com/the-markup/blacklight-collector) - The open-source Node.js engine behind Blacklight; self-host it to scan sites at scale in CI.
- [blacklight-query](https://github.com/the-markup/blacklight-query) - Open-source CLI for running Blacklight scans across large site lists and producing aggregate reports.
- [AdBlock Detection Scripts](https://github.com/InteractiveAdvertisingBureau/AdBlockDetection) - IAB Tech Lab's reference scripts for detecting ad-blocker usage — handy when reconciling delivery vs. analytics deltas.

---

## Books, Talks & Blogs

*High-signal reading on why ad fraud exists and how to think about it.*

### Book

- [Subprime Attention Crisis: Advertising and the Time Bomb at the Heart of the Internet — Tim Hwang (FSG, 2020)](https://books.google.com/books/about/Subprime_Attention_Crisis.html?id=iyPQDwAAQBAJ) - The case that programmatic attention markets are mispriced and structurally unstable — essential framing for anyone researching ad fraud.

### Talk

- [Black Hat USA 2013 — "Million Browser Botnet" (Jeremiah Grossman & Matt Johansen)](https://www.securityweek.com/researchers-demonstrate-million-browser-botnet-concept-built-legitimate-ad-networks/) - WhiteHat Security demonstrated building million-browser botnets by renting ad space for ~$500 — still the clearest argument for supply-side validation.

### Blogs & newsrooms

- [FouAnalytics](https://fouanalytics.com/) - Dr. Augustine Fou's research blog: bot-vs-human analytics teardowns, MFA supply analysis, and long-form breakdowns of programmatic waste.
- [The Markup](https://themarkup.org/) - Nonprofit newsroom whose Blacklight investigations quantify ad-tech tracking and its harms across the web.
- [IAB Tech Lab — De-mystifying app-ads.txt](https://iabtechlab.com/blog/demystifying-app-ads-txt/) - Official Buyers' guide to enforcing app-ads.txt authorization in purchasing workflows.
- [AdExchanger](https://www.adexchanger.com/) - Trade newsroom with deep, ongoing coverage of ad fraud, MFA economics, and enforcement actions.
- [PPC Land](https://ppc.land/) - Industry news desk tracking ad-fraud estimates, platform IVT changes, and regulatory developments.
- [Inside Google Ads — Fighting invalid traffic](https://blog.google/products/ads-commerce/using-ai-to-fight-invalid-ad-traffic/) - Google's public engineering/product posts on detecting invalid traffic at scale (e.g., LLM-based placement review).

---

## Contributing

Contributions are welcome — especially corrections, dead links, and additions of open-source tooling.

**Ground rules:**

- One resource per entry, formatted exactly as: `- [Resource Name](https://url) - Concise, factual one-sentence description.`
- Every link must be live and canonical (no trackers, no "wayback machine" links when the original lives).
- Prefer open source. Commercial tools or reports belong here only when they are the primary public source for a topic (e.g., a standard, a landmark study, or original reporting).
- Descriptions must be factual and neutral — no marketing language, no superlatives, no unverified claims.
- No affiliate links, referral codes, or paid placements. Disclose conflicts of interest in your PR.
- Keep alphabetical order within a subsection when adding entries.

**How to submit:**

1. Fork the repository and create a branch.
2. Add your entry in `README.md`.
3. Open a pull request using the checklist in the PR template — if no template exists, confirm in the description that (a) the link resolves, (b) the description is one factual sentence, and (c) the entry is open-source or a primary source.

For larger proposals (new categories, restructuring), please [open an issue](../../issues) first to discuss.

---

## License

This work is dedicated to the public domain under the [CC0 1.0 Universal](LICENSE) license. You may use, adapt, and redistribute it without restriction or attribution (though attribution is appreciated).

---

<div align="center">
<sub>Maintained by the community. If this list saved you a fraud headache, consider <a href="https://github.com/adops-tool/awesome-ad-fraud">starring the repo</a> and opening a PR with your favorite resource.</sub>
</div>
