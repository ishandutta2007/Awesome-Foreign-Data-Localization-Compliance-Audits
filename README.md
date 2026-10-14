# Awesome-Foreign-Data-Localization-Compliance-Audits

## Top Foreign Data Localization Compliance Audits Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Regional Boundary Enforcement, Data Residency Guardrails & Compliance Evidence*  

**Last updated: October 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Foreign Data Localization Compliance Audits**. These tools enable organizations to enforce data residency boundaries, monitor cross-border transfers, and produce audit-ready evidence that processing follows strict regional geographic requirements—GDPR, DPDPA, RBI, KRITIS, and beyond.



**Examples** include Securiti.ai, BigID, OneTrust DataGuidance, InCountry, Ketch, Transcend, Privacera, Skyflow, Immuta, and TrustArc (the category leaders).



**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, policy-as-code enforcement, and sovereign audit trails—ideal for compliance teams, platform engineers, and developers seeking transparent, jurisdiction-aware data governance.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **[Securiti.ai](https://securiti.ai/)**  

  Data privacy and AI governance platform with **regional boundary enforcement**, data discovery, classification, and policy enforcement across cloud environments.



- **[BigID](https://bigid.com/)**  

  Data intelligence platform for privacy, security, and governance. Features data discovery, classification, and **jurisdiction-aware policy enforcement** across structured and unstructured data.



- **[OneTrust DataGuidance](https://www.onetrust.com/)**  

  Enterprise privacy management with **regulatory research across 300+ jurisdictions**, consent management, DSR automation, and data mapping.



- **[InCountry](https://incountry.com/)**  

  Data residency-as-a-service platform. **Stores regulated data in-country** while applications remain global. Features local encryption, key management, and compliance with data localization mandates.



- **[Ketch](https://www.ketch.com/)**  

  Privacy automation platform with consent management, data subject rights, and **cross-border transfer policy enforcement**.



- **[Transcend](https://transcend.io/)**  

  Privacy infrastructure platform with DSR automation, consent management, and **data mapping with residency controls**.



- **[Privacera](https://privacera.com/)**  

  Data security and governance platform with **fine-grained access control, data masking, and policy enforcement** across cloud data platforms.



- **[Skyflow](https://www.skyflow.com/)**  

  Data privacy vault with **regional data residency enforcement**. Stores PII in isolated data vaults per jurisdiction with granular access controls.



- **[Immuta](https://www.immuta.com/)**  

  Data access governance platform with **policy enforcement, data masking, and audit trails** for cloud data platforms.



- **[TrustArc](https://trustarc.com/)**  

  Privacy compliance platform with **regulatory assessment, data mapping, and cross-border transfer management**.



## Open-Source GitHub Projects



- **[rbi-compliance-scanner](https://github.com/swayam-crypto/terraform-rbi-compliance-scanner)**  

  Terraform static analysis tool checking infrastructure code against **RBI cybersecurity guidance and India's DPDPA data protection requirements** (MIT). **The most India-specific open-source compliance scanner available.** Encodes rules like RBI-001: detecting S3 buckets holding sensitive financial data provisioned outside India (e.g., `us-east-1` instead of `ap-south-1`). **5 rules implemented** covering data localization, encryption, audit log retention, network exposure, and IAM least-privilege. Features **inline suppression** with audit-counting (suppressed findings are reported, not silently hidden), parallel scanning with incremental cache for large repos, and **GitHub Actions CI/CD integration**. Actively being developed—5 of planned 8 rules implemented. **Note**: Not yet validated by a compliance professional .



- **[Edge Policy Hub](https://github.com/acailic/edge-policy-hub)**  

  Open-source **ABAC policy engine with data residency guardrails** using OPA/Rego (open-source). **The most comprehensive open-source residency enforcement framework available.** Features **multi-tenant isolation with hard separation**, **HTTP(S) egress proxy with policy enforcement**, **MQTT bridge for IoT telemetry**, **human-readable policy DSL compiled to Rego**, **signed append-only audit store**, and **per-tenant quota tracking**. **Data residency guardrails** are a first-class MVP requirement—policies can enforce rules like `allow read sensor_data if subject.tenant_id == "tenant-eu" and resource.region == "EU" and subject.device_location in ["DE", "FR", "NL"]` . Deployable via Docker Compose, systemd, or click-to-deploy installers for Linux/Windows/macOS. **Offline-first operation** with optional audit log sync.



- **[Admina Residency Enforcer](https://github.com/admina-org/admina/blob/main/admina/domains/data_sovereignty/residency.py)**  

  Open-source Python module for **data residency enforcement** (open-source). **The simplest open-source implementation of zone-based data residency validation.** Features **allowed zones configuration** (default: `["local", "eu"]`), **outbound transfer blocking**, **violation tracking with statistics**, and **dataclass-based violation reporting**. `check()` method validates source and target zones—returns `allowed: False` with reason if transfer violates policy. **Designed to be called on every ingest/query operation** by a `GovernedData` wrapper .



- **[Sentinel Kernel](https://pypi.org/project/sentinel-kernel/)**  

  Sovereign decision records and policy-as-code for LLM/agent systems (Apache-2.0). **The most sovereign-focused open-source AI governance tool available.** Features **in-process OPA/Rego evaluation** (no network, no OPA server), **air-gapped operation** with zero network connectivity, **BSI IT-Grundschutz path**, **EU AI Act Article 12 compliance**, and **quantum-safe signing (ML-DSA-65)**. Critical path—interceptor, policy evaluation, trace emission, storage—**contains no US-owned components**. Explicitly addresses **US CLOUD Act exposure**: "No contract eliminates it. Sentinel's critical path is architectural, not a configuration option." Storage backends: SQLite (local), PostgreSQL (enterprise), Filesystem NDJSON (air-gapped) .



- **[Federated Sovereignty](https://github.com/abhijit-ubale/Federated-Sovereignty)**  

  Open-source **Kubernetes operator for geopolitical data residency enforcement** (open-source). **The most production-grade open-source residency enforcement for Kubernetes.** Uses **OPA Gatekeeper** to validate every Pod creation—**developers cannot bypass geopolitical constraints**. Features **lock data to EU (GDPR)**, enforce US localization, support China restrictions, multi-region support, **policy YAML creation with automatic validation**, **expiry date management**, namespace exemptions, **Streamlit dashboard with Folium geographical maps**, and **comprehensive audit trail**. 7,150+ lines of production-grade code including 4,500+ lines of documentation. Deployment via `deploy.sh` with prerequisite checking and CRD installation .



- **[tibet-audit](https://pypi.org/project/tibet-audit/)**  

  Open-source compliance scanner with **sovereignty checks and jurisdictional crossing** (open-source). **The most jurisdiction-aware open-source audit tool.** Features **120 checks across 17 regulatory frameworks** including **Gulf PDPL data localization** (GULF-001: CRITICAL), GDPR, AI Act, Japan APPI, Singapore PDPA, Australia Privacy Act, Brazil LGPD, and South Korea PIPA. **Checkpoint mode** crosses from one jurisdiction to another (`tibet-audit checkpoint --from eu --to us`) with a full crossing matrix. **Compliance health score 0-100** with severity-weighted deductions. TIBET integration for **cryptographic proof of AI decisions** and immutable audit trails .



- **[SemantixRAG](https://pypi.org/project/semantixrag/)**  

  Open-source RAG platform with **compliance module including PII scanning and GDPR DSAR automation** (open-source). Features **PII detection via Microsoft Presidio** (30+ types), **dynamic masking** with type-specific tokens, **risk level classification** (low/medium/high), **GDPR DSAR automation** (find/delete/export subject data across document, chunk, embedding, and memory indexes), and **OPA policy engine** for access control and masking strategy. Configuration via environment variables (`RAG_PII_SCAN_ENABLED`, `RAG_MASKING_ENABLED`, `RAG_AUDIT_LOG_ENABLED`) .



- **[ProvMap](https://provmap.com)**  

  Open-source dataset mapping **cloud provider compliance and jurisdiction risk** (open-source). **The most comprehensive open-source cloud jurisdiction reference available.** Covers **55 cloud providers** with SOC 2, ISO 27001, GDPR, HIPAA, PCI DSS certification status, **data residency by region**, **US CLOUD Act exposure**, and parent company relationships. **Verified sources for every data point.** Dataset is a git submodule for independent contribution. Stack: TanStack Start, Drizzle ORM, Postgres, Tailwind .



- **[semantic-firewall](https://github.com/hbauzan/semantic-firewall)**  

  Local-first semantic firewall for LLMs and RAG (open-source). Validates 1024D embedding geometry to **enforce data sovereignty and block prompt injections**. Deterministic—does not require live LLM provider. Features **firewall logic** (blocking, piggybacking rejection, noise pre-filter), **DB saturation testing** (LanceDB scaling from 1k to 50k rows), and **load test suite** (3 payload profiles × 3 concurrency levels) .



- **[sovereign-guard-ai](https://github.com/GSS-creator/sovereign-guard-ai)**  

  Enterprise compliance and trust gateway with **Deep Packet Inspection (DPI) engine** (open-source). Features **Lobster Trap DPI** with rule-based traffic inspection, **Cloudflare Workers deployment**, **Hugging Face Docker Space** for the DPI engine, and **KV/D1 storage** for audit logs. Full deployment guide includes UptimeRobot keep-alive configuration for free-tier Spaces .



### Additional Strong Open-Source Options



- **[Data Sovereignty Stack (ossalt)](https://ossalt.com/guides/data-sovereignty-open-source-stack-2026)** — Comprehensive guide to building sovereign infrastructure: Hetzner/OVH/Scaleway for EU-jurisdiction compute, MinIO/Garage/Ceph for object storage, OpenBao/Infisical for secrets, PostgreSQL/Citus/YugabyteDB for databases, Keycloak/Kanidm/authentik for IAM, Prometheus/Grafana/Loki for observability, and Nextcloud/Mattermost for collaboration .

- **[Red Hat Digital Sovereignty Readiness Appraisal](https://github.com/redhat/digital-sovereignty)** — Open-source framework assessing **7 domains and 48 capabilities** including data sovereignty (residency, jurisdiction control, key management), technical sovereignty (portability, open standards), operational sovereignty, assurance sovereignty, and executive oversight. Workshop-based 2-3 hour collaborative assessment .

- **[Tractatus Framework](https://codeberg.org/mysovereignty/tractatus-framework)** — Open-source governance framework (Apache-2.0) for sovereign record architecture. Module-by-module publication strategy for threat model review before release. EUPL-1.2 licensed platform code. "Village Model Licence" under development for community protection clauses .

- Community **n8n** workflows for residency violation alerting and compliance evidence routing.



**Frameworks for building custom systems**: Combine **Edge Policy Hub** for OPA-based residency guardrails with **rbi-compliance-scanner** for IaC-level enforcement, **Federated Sovereignty** for Kubernetes-native geopolitical constraints, **tibet-audit** for multi-jurisdiction compliance scanning, **Sentinel Kernel** for sovereign AI decision records, and **ProvMap** for cloud provider jurisdiction reference—creating a fully self-hosted, enterprise-grade data localization audit platform.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Data localization compliance systems handling regulated data must comply with applicable jurisdictional requirements (GDPR, DPDPA, RBI, KRITIS, PIPL, etc.). **Legal review remains essential**—tools support enforcement, not legal advice.

- **Data residency is not the same as digital sovereignty.** Where data sits is only one dimension. Complete sovereignty also requires **operational control** (who operates infrastructure), **administrative access** (who can view/modify data), **encryption key management** (who holds keys), **support personnel location**, **subcontractor dependencies**, **portability/exit rights**, and **resilience during geopolitical disruption**. US CLOUD Act exposure applies even to data in EU data centers operated by US companies .

- **Open-source localization audits are emerging, not mature.** rbi-compliance-scanner is **not yet validated by a compliance professional** . Federated Sovereignty is production-grade for Kubernetes but requires OPA Gatekeeper expertise . **No single open-source tool provides the end-to-end data mapping, classification, and jurisdiction-aware policy enforcement of Securiti.ai or BigID.** Integration work is required.

- **Policy-as-code is the open-source sweet spot.** Edge Policy Hub's OPA/Rego enforcement with human-readable DSL compilation provides deterministic, testable residency guardrails . Federated Sovereignty's OPA Gatekeeper integration prevents developers from bypassing geopolitical constraints at the Kubernetes admission layer .

- Self-hosted open-source solutions require proper security hardening, policy governance, and ongoing maintenance. Data localization violations can result in regulatory penalties—validation against legal requirements is essential before production deployment.



---



**Made for compliance officers, platform engineers, and developers building transparent data localization audit solutions.**

Let's make Foreign Data Localization Compliance Audits more open, data-driven, and jurisdiction-aware.
