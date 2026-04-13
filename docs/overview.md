# Project Overview

The VECTORFIELD project is a **traceability-driven enterprise network security architecture study**.  
It demonstrates how a realistic security architecture can be derived from organizational constraints,
stakeholder priorities, and operational limitations.

The project is intentionally structured to illustrate **methodological architecture design** rather
than product comparison or tool-centric security engineering.

The architecture is developed through a structured derivation process that links
organizational needs to verifiable technical controls.

Stakeholder Interview  
→ Single Source of Truth (SSoT)  
→ Derived Requirements  
→ Architectural Controls  
→ Validation Criteria

This methodology ensures that architectural decisions are 
**traceable to organizational priorities, technically testable, and operationally realistic**.

---

## Design Philosophy

The study emphasizes that effective security architecture is not primarily created through the
deployment of security tools, but through **structural design decisions**.

Key design principles include:

- traceability-driven architecture decisions
- strict **default-deny network segmentation**
- containment of compromise through VLAN isolation
- identity-based trust and controlled administrative access
- centralized logging for evidentiary visibility
- architecture designed for **SOC-readiness without requiring a 24/7 SOC**

---

## Architectural Context

The architecture models a **mid-sized enterprise environment** with realistic constraints:

- limited IT staffing
- absence of a dedicated 24/7 SOC
- strict budget constraints
- need for operational maintainability

Security controls are therefore implemented through **structural network design**, controlled
communication paths, and centralized enforcement rather than complex layered tooling.

---

## Key Architectural Elements

The VECTORFIELD architecture integrates several core components:

- VLAN-based network segmentation
- pfSense firewall as the central enforcement point
- certificate-based VPN access with multi-factor authentication (MFA)
- centralized logging and time synchronization
- IDS visibility for anomaly detection
- strict separation of user, server, and management networks

These controls collectively reduce attack surface, limit lateral movement,
and improve detection and investigation capabilities.

---

## Relationship to the Full Study

This repository provides structured documentation of the architecture and its design logic.

The complete architecture study is available in the `pdfs/` directory:

- Full Study  
- Portfolio Version

Both documents provide a detailed description of the architecture design, methodology,
and validation logic.