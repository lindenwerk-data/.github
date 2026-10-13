# Lindenwerk Data

Small, low-cost [Apify](https://apify.com) Actors for public business data (tenders, websites) and for turning documents
into clean Markdown for RAG. Pay per result, no subscriptions.

All Actors are on Apify Store under [apify.com/lindenwerk](https://apify.com/lindenwerk). Their source code is not
published here; this page is an index.

## Actors

| Actor | What it does | Price (pay per event) | Store |
|---|---|---|---|
| **Website Technology & Tech Stack Detector: BuiltWith Alternative** | Bulk website technology lookup: CMS, shop system, analytics, consent manager, CDN, frameworks, plus email provider and SaaS from DNS, GDPR signals and security headers. One row per site, weekly change monitor. | USD 0.01 per analysed site; USD 0.002 for a blocked site with DNS/header results; sites with nothing detected are free | https://apify.com/lindenwerk/tech-stack-detector |
| **SEO Audit Crawler: Broken Links, llms.txt & AI Bot Check** | Crawls whole sites and audits every page: titles, descriptions, headings, canonical, noindex, hreflang, structured data, broken links, duplicates. Site row with an AI-crawler robots.txt matrix, llms.txt, sitemap and HTTPS check. | USD 0.008 per audited page; USD 0.01 per site summary | https://apify.com/lindenwerk/seo-audit-crawler |
| **PDF to Markdown & RAG Chunks: Document Parser (DOCX/PPTX/XLSX)** | Converts PDF, Word (DOCX), PowerPoint (PPTX) and Excel (XLSX) to clean Markdown with tables inline as Markdown tables, plus optional heading-aware chunks with page numbers for citations. Scanned pages are flagged (no OCR yet). | USD 0.002 per converted document plus USD 0.0005 per page with text; failed, empty and scanned-only files are free | https://apify.com/lindenwerk/pdf-to-markdown-rag |
| **German & EU Tenders: Public Procurement Monitor** | German public tenders from oeffentlichevergabe.de (including below-threshold notices) plus TED, deduplicated and scored to your CPV codes, keywords, regions and value, with match reasons and deadlines. Daily alerts, 31-day scan, awards. | USD 0.01 per scored match; USD 0.003 per unscored notice | https://apify.com/lindenwerk/german-eu-tender-matcher |
| **France Tenders & Procurement: BOAMP, TED, Marchés Publics** | French public tenders (marchés publics) from BOAMP and TED in one deduplicated list, scored to your CPV codes, keywords, départements and regions. | USD 0.01 per scored match; USD 0.003 per unscored notice | https://apify.com/lindenwerk/france-tender-matcher |
| **UK Tenders Monitor: Government Contracts & Find a Tender Alerts** | UK public sector tenders from Find a Tender (Procurement Act 2023), scored to your CPV codes, keywords, regions and value, with SME/VCSE flags. | USD 0.008 per scored match; USD 0.003 per unscored notice | https://apify.com/lindenwerk/uk-tender-matcher |
| **SAM.gov Government Contract Opportunities Monitor** | US federal contract opportunities from the official SAM.gov public extract, amendments merged into one row per solicitation, scored to your NAICS, PSC, keywords and set-asides. No API key. | USD 0.003 per scored match; USD 0.0015 per unscored opportunity | https://apify.com/lindenwerk/sam-gov-contract-matcher |

Every Actor also carries Apify's minimum start event (USD 0.00005 per run). Rows that are filtered out, below your
score threshold or duplicates are never charged, and neither are documents that fail or have no text layer.

## Client examples

Copy-paste runners (Python, JavaScript, curl), sample inputs and recipes live in the public repo
[lindenwerk-data/apify-actor-examples](https://github.com/lindenwerk-data/apify-actor-examples) (MIT). The Actors themselves stay on Apify Store; that repo only calls them.


## How we build

- **Public sources or your own files.** Official open-data exports and APIs for tenders; robots.txt honoured for
  websites and document links; your own documents are read only from the storages you pick. No logins, no proxies,
  no captcha solving, no bot-protection workarounds.
- **No personal data.** The tender and website Actors strip contact names, personal e-mails and phone numbers,
  including from free text. The document converter never extracts names, e-mails or phone numbers as fields and drops
  author metadata.
- **Explainable output.** Scores come with plain-English `matchReasons`; detections come with confidence and evidence;
  document chunks carry page numbers and a heading path.
- **Agent-ready.** Explicit input and dataset schemas, bounded cost by default, callable as tools through the
  [Apify MCP server](https://docs.apify.com/platform/integrations/mcp), e.g.
  `https://mcp.apify.com?tools=actors,lindenwerk/tech-stack-detector`.

## Feedback

Found a bug or need a field? Open an issue on the Actor's page in Apify Store (Issues tab).

<sub>Tech Stack Detector is an alternative to tools such as Wappalyzer and BuiltWith; Lindenwerk Data is not affiliated
with, endorsed by or sponsored by them, and its fingerprint database is original work. Apify, TED, BOAMP, Find a Tender
and SAM.gov are named only to describe the platform and the data sources; no affiliation is implied.</sub>
