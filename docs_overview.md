# Project Overview

VECTORFIELD is an enterprise network security architecture study that demonstrates how enterprise security 
can be derived methodically from stakeholder requirements rather than from isolated tool selection.

The project starts with a structured stakeholder interview under realistic organizational tension: 
business pressure, audit findings, limited budget, lean IT staffing, and no 24/7 SOC. 
This interview serves as the Single Source of Truth (SSoT) that drives the entire architecture process.

From that foundation, the study derives testable requirements, defines a framework-aligned security logic, 
and translates both into a coherent architecture with the following characteristics:

- VLAN-based segmentation
- central pfSense enforcement
- strict default-deny between zones
- dedicated management isolation
- controlled VPN-based remote access
- certificate-bound authentication and MFA
- centralized logging and IDS-supported evidence capability

The project is not a product showcase. It is a methodological design study 
focused on traceability, auditability, and operational realism.

---

## What This Repository Demonstrates

This study illustrates how a security architecture can be developed through a 
structured design process rather than through ad-hoc tool selection.

Key aspects demonstrated in the project include:

- stakeholder-driven requirement derivation
- traceability from requirements to architectural controls
- zone-based network segmentation
- default-deny enforcement across security zones
- operationally realistic monitoring and logging design
- architecture validation through defined acceptance goals

---

## Repository Orientation

The repository is organized to expose the architectural logic and supporting documentation in a clear structure:

- VIDEO_WALKTHROUGH.md — guided video explanation of the architecture
- `docs/architecture-summary.md` — condensed explanation of the network architecture model
- `docs/requirements-traceability.md` — traceability logic from stakeholder input to architectural controls
- `docs/soc-readiness.md` — monitoring design and SOC-readiness concept
- `pdfs/` — full study and portfolio versions of the project