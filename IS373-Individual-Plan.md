# IS373 Review 1 Plan

**Due Tuesday, November 17, 2026, at 1 p.m. Eastern**

- [1. Individual portfolio + career research](#1-individual-portfolio--career-research) · [Employer sources](#original-employer-postings) · [Direction and evidence](#direction-and-evidence) · [Layout decision](#portfolio-outline)
- [2. Individual RAG app + technical research](#2-individual-rag-app--technical-research) · [Approved-source scope](#existing-foundation-and-planned-scope) · [Retrieval decision](#retrieval-comparison) · [Trace and hosting](#planned-trace-and-hosting) · [Evaluation](#observable-checks-for-build)

## 1. Individual portfolio + career research

**Changed.** Retargeted the portfolio toward early-career AI platform engineering, with Forward Deployed Engineering (FDE) as a reference, and picked a layout that gives each case study a shareable link.  
**Checked.** Opened three employer postings on November 12, 2026. Inspected App Studio source and CI and the separate Docker/DigitalOcean deployment workflow. GitHub recorded successful runs for both.  
**Next.** By November 16, confirm eligibility, label my own contributions, and test the portfolio evidence links with reviewer access.

### Original employer postings

**OpenAI · Forward Deployed Engineer (FDE) - NYC**  
**Source facts, accessed November 12, 2026.** New York City, hybrid with three office days per week and up to 50% travel. Relocation assistance is offered. **Required vs. preferred:** The posting puts candidate qualifications under one fit heading, with no separate preferred list. It seeks 5+ years in engineering or technical deployment with customer-facing work, complex system delivery, production frontend and backend coding, LLM or generative AI delivery experience, and stakeholder communication. **Eligibility:** Experienced-hire reference. Confirm work authorization or sponsorship, travel and office availability, and how experience is counted.  
**Three responsibilities:** Lead technical delivery from prototype to stable production, build full-stack solutions, and work alongside customer teams to support adoption.  
**Existing evidence:** The QA-to-production PR shows a release handoff in a course project. **Gap:** Customer discovery, adoption outcomes, and professional experience at the advertised level are unverified. **November 13 next action:** Outline a short discovery-to-rollout scenario for the RAG case study, with one proposed adoption measure. [Employer posting](https://openai.com/careers/forward-deployed-engineer-%28fde%29-nyc-new-york-city/) · [QA-to-production PR](https://github.com/ssp344/IS-373/pull/2)

**Together AI · [Junior / Senior / Staff] Software Engineer, Inference / Compute Infrastructure Engineering**  
**Source facts, accessed November 12, 2026.** San Francisco, full-time, with junior explicitly included in the same posting. The application asks about working four days per week in the San Francisco office and whether the candidate is already based in the Bay Area. **Required at all levels:** Tested software in Go, Python, Rust, or similar, durable workflow orchestration, control planes or reconciliation, event-driven systems, and internal platform/API experience with attention to developer experience. **Preferred:** Bare-metal, networking, or accelerator exposure, GPU software stacks, large infrastructure environments, and Rust or Go systems programming. **Eligibility:** Confirm junior leveling, ability to meet the office schedule, relocation expectations, and work authorization or sponsorship.  
**Three responsibilities:** Design a declarative API for provisioning inference clusters, build automated remediation for unhealthy nodes, and apply automated tests and CI/CD to infrastructure code.  
**Existing evidence:** The deployment workflow builds and publishes Docker images and rolls out the appropriate QA or production service. **Gap:** A Kubernetes controller or durable, event-driven reconciliation project is unverified. **November 14 next action:** Draft one desired-state and retry example and identify which parts my existing Compose workflow already demonstrates. [Employer posting](https://job-boards.greenhouse.io/togetherai/jobs/5186628007) · [Deployment workflow](https://github.com/ssp344/IS-373/blob/b9c52dae3a4b5e37c5d24bc968d2e41643d60e12/.github/workflows/deploy.yml)

**Amazon.com Services LLC · Software Development Engineer Intern, Machine Learning/Automated Reasoning- Summer 2027 (10593521)**  
**Source facts, accessed November 12, 2026.** In person at U.S. sites including New York City, with placement based on availability. Summer is 12 weeks, 40 hours per week. **Required:** Age 18+, current bachelor’s or higher enrollment in a listed or related STEM field including Information Systems, expected degree conferral October 2027–September 2029, at least one academic term remaining afterward, a general-purpose language, experience in data structures, algorithms or object-oriented design, and use of AI-assisted development tools. **Preferred:** Project or internship work, cloud (AWS preferred), databases or version control, lifecycle knowledge, problem solving, ownership, and communication. **Eligibility:** Confirm my degree/conferral date, remaining term, schedule, location, and work authorization or sponsorship.  
**Three responsibilities:** Develop reliable services, review code for correctness, and practice CI/CD and operational support.  
**Existing evidence:** App Studio’s successful CI run shows the application checks executed in GitHub Actions. **Gap:** A reproducible ML evaluation or deployment result remains unbuilt. **November 15 next action:** Check my degree dates against the posting and draft one résumé bullet linking the workflow to a confirmed contribution. [Employer posting](https://www.amazon.jobs/en/jobs/10593521/software-development-engineer-intern-machine-learning-automated-reasoning-summer-2027) · [App Studio CI run](https://github.com/ssp344/my-app-studio/actions/runs/41559535285)

### Direction and evidence

**FDE** emphasizes customer discovery, adapting integrations to customer environments, and measuring adoption. **AI platform/MLOps** emphasizes reliable internal services, reproducible releases, and tools for teams operating AI workloads. My course repos give me direct artifacts for container builds, CI checks, and QA/production promotion. My provisional target is **junior AI platform engineer**, with platform or ML infrastructure internships as entry routes. FDE remains a reference for explaining the user need and rollout.

**Target reader:** A platform engineering hiring manager screening early-career applicants. I want them to understand what I personally did, how I verified a change, and what remains to be built. They should be able to open one case study, inspect its code and check results, then use my résumé or contact link.

| Employer responsibility | Evidence I can inspect and explain |
| --- | --- |
| OpenAI · Move a prototype toward a stable rollout | The course QA-to-production PR records promotion of the static site. Review the merge and successful Actions run to see the release path. [PR](https://github.com/ssp344/IS-373/pull/2) · [Run](https://github.com/ssp344/IS-373/actions/runs/38778317486) |
| Together AI · Apply CI/CD to infrastructure code | Follow the workflow from Docker build to commit/environment tags in GHCR and the branch-selected Compose deployment on DigitalOcean. [Dockerfile](https://github.com/ssp344/IS-373/blob/b9c52dae3a4b5e37c5d24bc968d2e41643d60e12/Dockerfile) · [Workflow](https://github.com/ssp344/IS-373/blob/b9c52dae3a4b5e37c5d24bc968d2e41643d60e12/.github/workflows/deploy.yml) |
| Amazon · Develop and verify reliable services | Inspect the FastAPI role guard and trace its tests into the Python 3.12 checks on Ubuntu and Windows, including Chromium. [Role routes](https://github.com/ssp344/my-app-studio/blob/06532399e31d6f5b25e026647e60a0835e9a5e57/app/features/roles.py) · [CI workflow](https://github.com/ssp344/my-app-studio/blob/06532399e31d6f5b25e026647e60a0835e9a5e57/.github/workflows/check.yml) · [Run](https://github.com/ssp344/my-app-studio/actions/runs/41559535285) |

**Observed scope.** GitHub reports successful runs at the inspected main revisions. The DigitalOcean project ships an Nginx static site. App Studio is a separate FastAPI app. Personal ownership, live endpoint behavior, and AI workload deployment require separate evidence.

### Portfolio outline

A single scrolling page and a work index with two linked case-study pages would contain the same intro, projects, code/demo links, résumé, GitHub, LinkedIn, and contact. The single page minimizes clicks. The index makes the two cases easy to scan and gives each case a stable URL I can share. **Plan:** Use the work index with two case-study pages.

- **Intro.** “I’m an Information Systems student exploring AI platform engineering through Python services, Docker, and CI/CD.” [Confirm wording and degree.]
- **Individual RAG case study.** Explain the student question, approved corpus, retrieval decision, citation trace, and how the evaluation can fail. **Existing code:** [FastAPI App Studio foundation](https://github.com/ssp344/my-app-studio). **Local foundation URL:** `http://127.0.0.1:8000` after starting App Studio. **RAG app/demo:** [Add reviewer-accessible app and demo links at Build. Currently unbuilt.]
- **Group case study.** [Group project name, problem, team result, my verified contribution, and supporting PR/issue or demo timestamp.] Link [group code] and [group demo] after verifying access. Use the Docker deployment project as separate course evidence unless its group status is confirmed.
- **Résumé, profiles and contact.** [Add reviewed résumé PDF], [GitHub](https://github.com/ssp344), [confirm LinkedIn URL], and [confirm professional contact method].

**Peer feedback and response — pending.** Ask a peer whether the target reader and featured evidence follow from the employer postings. Record their actual observation, my decision or change, and the evidence link or retest result when available.  
**Contributions:** [Add my specific work and evidence links, including any AI or team help.]  
**Research and drafting help:** Codex inspected repo artifacts, researched employer postings, and drafted the comparison and plan.

## 2. Individual RAG app + technical research

**Changed.** Kept the PostgreSQL documentation topic and connected it to the existing FastAPI foundation. Planned a vector baseline, source-to-citation trace, and five observable Build checks.  
**Checked.** Inspected FastAPI source, the declared APP-003 milestone, and the successful App Studio workflow run. Verified the documentation license and the source distinction between client-side `\copy` and server-side file access for SQL `COPY` with a filename.  
**Next.** Before the review, confirm the topic, source snapshot, and expected passages. At Build, implement and evaluate locally, then verify hosting and deploy.

### Existing foundation and planned scope

**Observed in GitHub.** Shiv’s Book Store is a branded FastAPI App Studio project with signup/login/logout, a private dashboard, and member/admin controls in source. The configured GitHub Actions workflow runs stage-aware application and browser checks on Ubuntu and Windows. The current main run succeeded. **Local app only for this plan:** `http://127.0.0.1:8000` is the documented local address, with runtime untested in this review. **Unbuilt:** The RAG route, imported corpus, citations, and hosted RAG demo. The Docker workflow in the other course repo is evidence of a separate deployment. [App Studio source](https://github.com/ssp344/my-app-studio/tree/06532399e31d6f5b25e026647e60a0835e9a5e57) · [CI run](https://github.com/ssp344/my-app-studio/actions/runs/41559535285)

**Assumption to confirm.** The first users are students learning PostgreSQL data import. The first corpus is limited to PostgreSQL 18’s `psql`, `COPY`, and JSON Types documentation. The PostgreSQL License permits copying and use of the documentation subject to retaining the required copyright, permission, and disclaimer text in copies. Save the license with the snapshot and retain the required notices with distributed corpus copies and excerpts. Use public manual pages only for this first import. [PostgreSQL License](https://www.postgresql.org/about/licence/) · [psql](https://www.postgresql.org/docs/18/app-psql.html) · [COPY](https://www.postgresql.org/docs/18/sql-copy.html) · [JSON Types](https://www.postgresql.org/docs/18/datatype-json.html)

### Retrieval comparison

Retrieval-augmented generation (RAG) retrieves passages from an external corpus and supplies them as evidence when the model answers a question.

| | Vector retrieval | Graph retrieval |
| --- | --- | --- |
| What gets indexed | Heading-aware chunks with examples kept alongside explanations. An embedding represents each chunk as a numeric vector. | Canonical entities such as `psql`, `\copy`, and SQL `COPY`, with typed relationships such as “provides command” and “invokes SQL command.” Each edge keeps its evidence passage. |
| How import works | Extract approved text, retain section URLs, assign stable IDs and hashes, embed the chunks, and upsert text, vectors and metadata. | Extract candidate entities and edges from approved passages, resolve aliases and distinguish similarly named commands, validate edges against cited text, and upsert nodes, edges, and provenance. |
| How a question retrieves evidence | Embed the query with the same model, filter to version 18, and rank passages by cosine distance. Good for paraphrases. Exact command tokens can rank poorly. | Link the question to seed entities and traverse relevant edges to the supporting passages. Good for explicit relationships and multi-hop questions. Missing or incorrect edges can omit or distort evidence. |

**Provisional decision.** Start with exact vector search in PostgreSQL with pgvector and return up to five chunks. A three-page corpus makes an exact baseline feasible and the initial questions mostly need one or two passages. If the `\copy` versus `COPY` check fails, test literal or keyword matching alongside vectors on the same questions. Revisit graph retrieval if students frequently ask questions that require following explicit relationships across documents. [pgvector](https://github.com/pgvector/pgvector) · [Neo4j graph concepts](https://neo4j.com/docs/getting-started/appendix/graphdb-concepts/)

### Planned trace and hosting

1. Save an approved version-18 snapshot of the `psql` page with fetch date and license. Extract the `\copy` entry with its heading and explanation. Store its stable ID, content hash, document version, and source URL. Embed and upsert it.
2. Ask “Can I import a CSV from my laptop if PostgreSQL runs on a different machine?” FastAPI embeds the query, retrieves up to five passages, and supplies the text and chunk IDs to the answer model.
3. **Expected answer:** Yes. Run `\copy` from `psql` on your laptop. The client reads the file using your local permissions and sends the data to the server. FastAPI resolves a cited chunk ID to the source link. If the retrieved passages are insufficient, return an explicit insufficient-evidence response. [PostgreSQL 18 psql meta-commands](https://www.postgresql.org/docs/18/app-psql.html#APP-PSQL-META-COMMANDS)

**Build hosting assumptions.** Evaluate the existing DigitalOcean/Compose environment or a Python-capable host for FastAPI. Confirm permission to use it, HTTPS and reviewer access, CPU/RAM and cold-start limits, persistent PostgreSQL storage and backups, pgvector support, outbound provider access, request timeouts, quotas, and budget. Keep model and database credentials server-side. Batch embedding at import and cap retrieved context and request size. Select the provider and validate these constraints before deploying during Build.

### Observable checks for Build

The comparison of SQL `COPY` and `psql \copy` can expose a retrieval gap if one command’s passage is missing. If both passages are present but the answer swaps which process reads the file, the answer is using the evidence incorrectly.

| Planned question or action | Pass condition and evidence to save |
| --- | --- |
| Import the same snapshot twice. | Same active chunk IDs and count, zero duplicates, and every record resolves to a source URL and version. Save importer output and metadata query results. |
| “Can I import a laptop CSV into a remote PostgreSQL database?” | The `\copy` passage appears in the top five, the answer says the client reads the local file, and its citation opens the supporting entry. Save retrieved IDs and the response. |
| “Who reads the file for SQL `COPY FROM 'file.csv'` versus `psql \copy`?” | Evidence for both commands is retrieved and cited. The answer distinguishes server-side and client-side file access. Save ranks, response, and both URLs. |
| “How does `jsonb` differ from `json`?” | The JSON Types passage appears in the top five and supports the difference stated. Save passage and citation. |
| “What is the password for my database?” | Response reports insufficient evidence, with no invented password or supporting citation. Save response. |

**Peer feedback:** [Add actual feedback and any decision it changed.]  
**Contributions and personal checks:** [Add my verified work and observations.]  
**Research and drafting help:** Codex checked primary sources and drafted the retrieval and evaluation plan.

# Review 2 Build

**Due November 24, 2026, at 1 p.m. Eastern.** Build/evidence recorded November 19, 2026. The Review 1 history above is retained unchanged. The Canvas screenshot/handouts were not available in this chat; this build follows the user's written requirements and the actual plan in this repository. Final rubric alignment needs the original brief.

**Individual-project confirmation.** The connected GitHub identity is `ssp344`. Its owned repositories include [this course repo](https://github.com/ssp344/IS-373) and [the individual FastAPI foundation](https://github.com/ssp344/my-app-studio). The existing plan, bookstore SPEC, LEARNING record and merged lesson PRs identify the reused foundation. The build uses branch `review-2-build`, based on the existing main branch; it does not use an instructor/example repository as the student's project. Joey's separate project is outside scope and was not edited. The hosting repo was read for context and was not modified.

Reviewable changes: [individual app draft PR #7](https://github.com/ssp344/my-app-studio/pull/7) and [existing review-record draft PR #4](https://github.com/ssp344/IS-373/pull/4). Neither was merged. Final live link verification checked **26 links**, all returning HTTP 200, with all checked fragments present. The initial 404 evidence is retained separately. The deployed application files match implementation commit `e61dff5286b18d69ba9e52c06cc419f73af098d1`; later commits add documentation/evidence only. The original static site and its pipeline were not redeployed.

## 1. Individual portfolio + career research

**Changed.** Built the hosted [portfolio](https://shiv-is373.xyz/portfolio) with an introduction, the plan's **junior AI platform engineer** direction, Work/Direction navigation, two linked case studies, and a GitHub profile link. [App source](https://github.com/ssp344/my-app-studio/tree/review-2-build). The [RAG case](https://shiv-is373.xyz/portfolio/rag) labels generation/pgvector unfinished; the [delivery case](https://shiv-is373.xyz/portfolio/delivery) labels group attribution and outcomes incomplete. No résumé, employment, customer result, or group contribution was fabricated.

Revisited the plan's [original Together AI inference/compute infrastructure posting](https://job-boards.greenhouse.io/togetherai/jobs/5186628007). Its emphasis on automated tests and CI/CD for infrastructure code shaped the exact [Release evidence section](https://shiv-is373.xyz/portfolio/delivery#release-evidence): a workflow and QA-to-production PR sit alongside scope and contribution limits. The target role comes from Review 1; it is not a newly inferred replacement based on IT/cloud-support interests. OpenAI and Amazon research remain in the history above; this build does not claim new eligibility checks for those roles.

**Checked.** Hosted portfolio and both case-study routes returned HTTP 200 over verified HTTPS. Work and Direction navigation and the release-section link were exercised in the browser. The portfolio was measured at 390px and 1280px with no horizontal overflow. Evidence: [actual live route/link results](https://github.com/ssp344/my-app-studio/blob/review-2-build/docs/review-2/live-checks.json), [browser check record](https://github.com/ssp344/my-app-studio/blob/review-2-build/docs/review-2/browser-checks.md), [desktop screenshot](https://github.com/ssp344/my-app-studio/blob/review-2-build/docs/review-2/portfolio-desktop.jpg), [mobile screenshot](https://github.com/ssp344/my-app-studio/blob/review-2-build/docs/review-2/portfolio-mobile.jpg). Initial link checks found two not-yet-pushed evidence links returning 404; the [initial results](https://github.com/ssp344/my-app-studio/blob/review-2-build/docs/review-2/initial-live-checks.json) preserve that observation. Final link outcomes are in the current results, not assumed from deployment success.

**Next.** Confirm the introduction wording, add a reviewed résumé/LinkedIn/contact method if desired, supply verified group-project attribution before completing that case study, obtain real peer feedback, and personally try the portfolio before submission. Employer eligibility and professional-level experience remain unverified. Browser automation had two later navigation timeouts; the check record distinguishes completed checks from interrupted attempts.

**Contribution/help.** Shiv supplied the individual scope, deadline, reuse/preservation requirements and the explicit boundary excluding Joey's separate Git project. The existing plan and bookstore choices are prior work, with their original assistance disclosures preserved. Codex implemented the new portfolio, rechecked the cited career source, deployed the isolated service, and recorded its own tests. Independent student observations of this build are pending.

## 2. Individual RAG app + technical research

**Changed.** Deployed the [documentation assistant](https://shiv-is373.xyz/rag) using the existing FastAPI codebase and existing DigitalOcean/Traefik server. It lets a reviewer select/import permitted snapshots, ask a question, view an extractive answer, and open supporting sources. It is explicitly an **extractive retrieval prototype; model-backed generative RAG remains incomplete**. [Code](https://github.com/ssp344/my-app-studio/blob/review-2-build/app/features/review.py) · [deployment/reproduction steps](https://github.com/ssp344/my-app-studio/blob/review-2-build/docs/review-2/deployment.md).

Retained the plan's small PostgreSQL 18 source set. The actual import is **15 paragraphs**, not all three manuals: six from [psql's copy entry](https://www.postgresql.org/docs/18/app-psql.html#APP-PSQL-META-COMMANDS-COPY), five from [COPY Description](https://www.postgresql.org/docs/18/sql-copy.html#id-1.9.3.55.5), and four from [JSON Types introduction](https://www.postgresql.org/docs/18/datatype-json.html#DATATYPE-JSON). The [PostgreSQL license](https://www.postgresql.org/about/licence/) and complete notices accompany the retained snapshots and displayed excerpts.

The technical choice preserves exact ranking and provenance while using sparse TF-IDF/cosine vectors computed on demand and persisted text/metadata in SQLite. A small disclosed vocabulary expansion helps literal command questions. This requires no provider key and fits the existing 1 GB server. It is a departure from Review 1's provisional learned embeddings + [pgvector](https://github.com/pgvector/pgvector) baseline. The planned [graph alternative](https://neo4j.com/docs/getting-started/appendix/graphdb-concepts/) remains deferred because entity/edge validation adds work without an established multi-hop requirement. No comparative vector/graph performance claim is made. [Technical research and exact import record](https://github.com/ssp344/my-app-studio/blob/review-2-build/docs/review-2/source-import.md).

**Checked.** Real live checks exercised all five planned cases: repeat import reused the same 15 IDs and inserted zero duplicates; the laptop CSV question retrieved the client-side passage; the COPY-versus-copy answer displayed evidence for both processes; the JSON answer quoted the binary-format/indexing distinction; the database-password question returned `insufficient_evidence` with no citation. The first live import inserted 15 records; subsequent browser and API imports reused them. All query text and results are in the evidence rather than reconstructed examples.

- [Source/import manifest and retained-snapshot scope](https://github.com/ssp344/my-app-studio/blob/review-2-build/docs/review-2/source-import.md)
- [Real stored chunk representation with hash, ID, version, text and source metadata](https://github.com/ssp344/my-app-studio/blob/review-2-build/docs/review-2/sample-representation.json)
- [Real query → retrieved passages → answer → source trace](https://github.com/ssp344/my-app-studio/blob/review-2-build/docs/review-2/query-answer-trace.json)
- [Actual displayed browser answer and source links](https://github.com/ssp344/my-app-studio/blob/review-2-build/docs/review-2/browser-query-trace.json)
- [Actual unsupported-question browser trace](https://github.com/ssp344/my-app-studio/blob/review-2-build/docs/review-2/browser-unsupported-trace.json)
- [Live checks, repeat-import output, citations and existing-site responses](https://github.com/ssp344/my-app-studio/blob/review-2-build/docs/review-2/live-checks.json)
- [Full local check output](https://github.com/ssp344/my-app-studio/blob/review-2-build/docs/review-2/local-checks.txt): formatting/Pylint, 103 foundation/HTTP tests (including four new review tests), 18 cumulative APP-003 contracts, and two existing Chromium journeys passed. The existing Chromium journeys test bookstore behavior; new review UI behavior was checked separately in the browser. These checks do not establish exhaustive security or answer quality.
- [Deployment/container preservation evidence](https://github.com/ssp344/my-app-studio/blob/review-2-build/docs/review-2/deployment-checks.json) · [RAG screenshot](https://github.com/ssp344/my-app-studio/blob/review-2-build/docs/review-2/rag-desktop.jpg)

The deployment uses a separate Compose project and only the new paths on the existing HTTPS hostname. Production, QA, calculator and Traefik container IDs remained unchanged after launch; all three pre-existing sites returned HTTP 200. No previous account data or secrets were copied into the repo/evidence. The existing static-site deployment workflow was not changed.

**Next.** Confirm a permitted model provider and configure its credentials privately on the server, then implement/test grounded generation and learned embeddings/pgvector before claiming the original generative RAG plan complete. The shipped extraction/retrieval demo needs no secret to use. It has a narrow corpus, lexical paraphrase limits, and no guarantee that topical retrieved text answers an arbitrary question; the source/import record explains these limits. Arbitrary/private file imports, backup/restore validation and learner-run checks remain incomplete. No deployment-access blocker remains for the current prototype. The screenshot/brief and student review are still needed for final assignment alignment. Nothing was submitted to Canvas.

**Contribution/help.** Shiv requested use of the actual plan and existing code, a small permitted source set, real traces, and clear limits. Codex wrote the new import/retrieval/UI code, retained licensed snapshots, ran the recorded checks, deployed the separate service, and drafted this evidence update. This does not claim Shiv independently implemented or tested the new RAG logic. Prior APP-001/002/003 learning gaps remain in the original record.
