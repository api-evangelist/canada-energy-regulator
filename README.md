# Canada Energy Regulator (canada-energy-regulator)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

The Canada Energy Regulator (CER / Régie de l'énergie du Canada) is Canada's federal energy regulator, created by the Canadian Energy Regulator Act in 2019 to replace the National Energy Board. Its remit is the interprovincial and international layer of the energy system: pipelines and power lines that cross a provincial or national border, imports and exports of oil, natural gas, NGLs, LNG and electricity, oil and gas activity on frontier and offshore lands, and offshore renewable energy projects. It does not regulate the distribution utilities that meter and bill Canadian households — electricity and gas distribution is provincial, which is why the only consumer energy data mandate in the country, Ontario's Green Button regulation O. Reg. 633/21, is administered by the Ontario Energy Board and not by the CER. The CER's API posture is the cleanest possible statement of that split: it is genuinely open on market and system data and entirely absent on consumer data. It publishes 83 datasets and 944 resources on the Government of Canada Open Government Portal, every one of them under the Open Government Licence – Canada, 894 of them CSV files served anonymously from its own www.cer-rec.gc.ca/open/ tree, all of it queryable without a key through the portal's CKAN Action API. It operates its own ArcGIS Online organization whose 23 hosted feature services — pipeline systems, incidents, provincial pipeline status, resource areas, refineries — answered anonymous ArcGIS REST queries on 2026-07-27, and it publishes an Environmental and Socio-economic Assessments layer through the Federal Geospatial Platform as both an Esri ArcGIS REST MapServer and an OGC WMS 1.3.0 service. It also open-sources the front ends for its own visualizations on GitHub. What it does not have is a developer portal, an OpenAPI definition, an API key, a rate-limit policy, or a single machine-readable path to an individual customer's usage or billing data. No mandate obliges it to have one. Home market Canada.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/canada-energy-regulator/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/canada-energy-regulator/refs/heads/main/apis.yml)

## Tags

- Energy
- Canada
- Regulation
- Government
- Pipelines
- Electricity
- Natural Gas
- Crude Oil
- Energy Markets
- Open Data
- Geospatial

## Timestamps

- **Created:** 2026-07-27
- **Modified:** 2026-07-27

## APIs

### CER ArcGIS Online Feature Services

The Canada Energy Regulator operates its own ArcGIS Online organization (portal neb-gis.maps.arcgis.com, organization id vNzamREXvX2WcX6d) and hosts 23 public feature services on it. This is the one genuinely CER-operated machine-readable API surface found in this review. The services directory, every FeatureServer descriptor and the /query operation all answered anonymous HTTPS requests on 2026-07-27 with no key, no signup and no terms click-through. Layers include CER_Pipeline_Systems_WGS84_view, Incident_Data_English_20191007_View (1,899 features confirmed by a returnCountOnly query), Prov_Pipe_Status (43 features), Prov_Pipe_Type, Oil_and_Gas_Resource_Area, Refinery, Western_Canada_Sedimentary_Basin, Pipelines_Profile_Links_EN_view and both English and French incident layers. The contract is Esri's ArcGIS REST API, not OpenAPI; no OpenAPI, Swagger or /api-docs document is published for it. This service backs the public CER Interactive Pipeline Map.

- **Human URL:** [https://www.cer-rec.gc.ca/en/safety-environment/industry-performance/interactive-pipeline/index.html](https://www.cer-rec.gc.ca/en/safety-environment/industry-performance/interactive-pipeline/index.html)
- **Base URL:** `https://services5.arcgis.com/vNzamREXvX2WcX6d/arcgis/rest/services`

#### Tags

- Geospatial
- Pipelines
- Incidents
- Open Data
- ArcGIS

#### Properties

- [API Reference](https://services5.arcgis.com/vNzamREXvX2WcX6d/arcgis/rest/services?f=json)
- [Documentation](https://www.cer-rec.gc.ca/en/safety-environment/industry-performance/interactive-pipeline/index.html)
- [Documentation](https://neb-gis.maps.arcgis.com/apps/webappviewer/index.html?id=2d11fd4e6a7a4f4ba7fe6bdf51ae52de)
- [Website](https://neb-gis.maps.arcgis.com/)

### CER Assessments Map Service (Federal Geospatial Platform)

The CER's Environmental and Socio-economic Assessments (ESA) layer, published through the Government of Canada's Federal Geospatial Platform at maps-cartes.services.geo.ca under the NRCan folder and served in English and French. Two protocols are exposed for the same data and both answered anonymously on 2026-07-27: an Esri ArcGIS REST MapServer (?f=json returned a service description naming the CER as the data owner) and an OGC WMS 1.3.0 endpoint whose GetCapabilities document parsed as valid XML. This is CER data on federal shared infrastructure rather than a CER-operated host, and it is the only place in this review where an open, vendor-neutral international standard (OGC WMS) is used.

- **Human URL:** [https://open.canada.ca/data/en/dataset/039fbd92-43c2-4805-b210-d65703712e37](https://open.canada.ca/data/en/dataset/039fbd92-43c2-4805-b210-d65703712e37)
- **Base URL:** `https://maps-cartes.services.geo.ca/server_serveur/rest/services/NRCan/CER_Assessments_EN/MapServer`

#### Tags

- Geospatial
- Assessments
- WMS
- OGC
- Open Data

#### Properties

- [API Reference](https://maps-cartes.services.geo.ca/server_serveur/rest/services/NRCan/CER_Assessments_EN/MapServer?f=json)
- [Documentation](https://maps-cartes.services.geo.ca/server_serveur/services/NRCan/CER_Assessments_EN/MapServer/WMSServer?request=GetCapabilities&service=WMS&version=1.3.0)
- [Documentation](https://open.canada.ca/data/en/dataset/039fbd92-43c2-4805-b210-d65703712e37)

### CER Open Data via the Open Government Portal CKAN API

The Canada Energy Regulator publishes no API of its own for tabular data, but all of its open data is machine-readable through the Government of Canada Open Government Portal's CKAN Action API, which is operated by the Treasury Board of Canada Secretariat and not by the CER. Filtering that API to the CER's organization id A3EE9522-882F-47B0-BA7D-83420DC8577C returned 83 datasets carrying 944 resources on 2026-07-27 — 894 CSV, 36 HTML, 8 PDF, 2 XLSX, 2 Esri REST and 2 WMS — every one licensed under the Open Government Licence – Canada. Coverage is the CER's regulatory and market record: crude oil, natural gas, NGL, LNG and electricity imports and exports, pipeline throughput, capacity and tolls, pipeline financial information, incidents, conditions, compliance and enforcement, the regulated company list, frontier production statistics and the Canada's Energy Future projection series. Only one of the 944 resources is loaded into the CKAN datastore, so datastore_search row-level querying is effectively unavailable; the real access pattern is metadata over the API and then bulk CSV download from https://www.cer-rec.gc.ca/open/, which was confirmed serving a 10,110-byte LNG exports file anonymously.

- **Human URL:** [https://open.canada.ca/data/en/organization/cer-rec](https://open.canada.ca/data/en/organization/cer-rec)
- **Base URL:** `https://open.canada.ca/data/api/3/action`

#### Tags

- Open Data
- CKAN
- Energy Markets
- Imports and Exports
- Statistics

#### Properties

- [API Reference](https://open.canada.ca/data/api/3/action/help_show?name=package_search)
- [Documentation](https://open.canada.ca/data/en/organization/cer-rec)
- [Documentation](https://www.cer-rec.gc.ca/en/about/open-government/)
- [Documentation](https://www.cer-rec.gc.ca/en/data-analysis/)

## Common Properties

- [Website](https://www.cer-rec.gc.ca/en/)
- [Documentation](https://www.cer-rec.gc.ca/en/data-analysis/)
- [Documentation](https://www.cer-rec.gc.ca/en/about/open-government/)
- [Documentation](https://www.cer-rec.gc.ca/en/data-visualization/)
- [API Reference](https://open.canada.ca/data/api/3/action/help_show?name=package_search)
- [GitHub Organization](https://github.com/CER-REC)
- [GitHub Repository](https://github.com/CER-REC/pipeline-profiles)
- [GitHub Repository](https://github.com/CER-REC/conditions)
- [GitHub Repository](https://github.com/CER-REC/incidents-pipeliniers_pipeline-incidents)
- [Terms of Service](https://www.cer-rec.gc.ca/en/terms-conditions.html)
- [Support](https://www.cer-rec.gc.ca/en/about/contact/index.html)

## Mandate and Access Posture

| Question | Finding |
| --- | --- |
| Mandate regime | `none` — no CDR, no Green Button obligation, no smart-meter data right applies to the CER |
| Mandate status | `not-applicable` — the CER does not regulate distribution utilities, so no consumer data mandate can attach to it |
| Data standard | No energy-sector standard. OGL-Canada licensing, CKAN Action API metadata, CSV data, Esri ArcGIS REST and OGC WMS 1.3.0 geospatial |
| Consumer data API | No — structurally absent, not merely missing |
| Market data open | Yes — 83 datasets, 944 resources, 23 anonymous feature services, all keyless |
| Access gate | `self-serve` — no signup, no key, no application, no licence to sign |
| Auth model | None. Anonymous HTTPS throughout. No OIDC discovery document is served |
| Developer portal | None. Every candidate path and subdomain soft-404s or fails to resolve |
| OpenAPI harvested | No — the CER publishes no OpenAPI, Swagger, AsyncAPI or GraphQL schema |

Canada's only energy consumer data mandate is Ontario's O. Reg. 633/21, requiring rate-regulated Ontario electricity and natural gas utilities to offer Green Button (NAESB REQ.21 ESPI) by 1 November 2023, administered by the Ontario Energy Board. The Canada Energy Regulator has no role in it. Full evidence, probe log and HTTP statuses are in [`review.yml`](review.yml).

## Maintainers

- Kin Lane — kin@apievangelist.com
