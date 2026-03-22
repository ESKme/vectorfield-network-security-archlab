# Architecture Decisions

This document records key design decisions made during the development
of the VECTORFIELD enterprise network security architecture.

The purpose of this document is to provide transparency regarding
architectural trade-offs and the rationale behind major design choices.

---

## Architectural Context

The VECTORFIELD architecture models a mid-sized enterprise environment
with constrained operational resources.

Key constraints influencing architectural decisions include:

- limited IT staffing
- absence of a dedicated 24/7 SOC
- moderate infrastructure budget
- requirement for operational maintainability

These constraints intentionally shape the architectural decisions
documented in this section.

---

## AD-01 — Zone-Based Trust Architecture

Decision:

Structure the network architecture around clearly defined trust zones
with controlled communication paths between them.

Rationale:

The architecture primarily relies on zone-based trust boundaries
at the network level while complementing this model with 
identity-based authentication for privileged access paths.

Different system groups operate under different trust levels and operational
roles. Separating these groups into security zones enables more precise
access control and reduces implicit trust relationships.

Consequences:

- clearer separation of trust boundaries
- improved containment of compromised systems
- more structured firewall policy design

---

## AD-02 — VLAN-Based Network Segmentation

Decision:

Implement network segmentation using VLANs to enforce security zones.

Rationale:

VLAN segmentation provides a practical implementation mechanism
for trust zone separation within enterprise networks.

Consequences:

- improved containment of compromised systems
- reduced attack surface
- simplified policy enforcement through firewall rules

---

## AD-03 — Default-Deny Communication Model

Decision:

Apply a strict default-deny policy for all inter-zone communication.

Rationale:

Explicitly allowing only required service flows reduces
unintended exposure of internal systems.

Consequences:

- minimized service exposure
- controlled communication paths
- stronger containment of potential compromises

---

## AD-04 — Pin-Hole Rule Design

Decision:

Implement inter-zone access through narrowly defined pin-hole firewall rules.

Rationale:

Service communication should be restricted to explicitly required ports,
protocols, and source-destination paths.

Consequences:

- minimized service exposure
- reduced lateral movement opportunities
- improved auditability of firewall policy

---

## AD-05 — Central Firewall Enforcement

Decision:

Use a pfSense-based firewall platform as the central enforcement point.

Rationale:

Centralized enforcement provides a single control point for
network access policies and monitoring.

Consequences:

- consistent access control enforcement
- simplified security policy management
- centralized logging of network activity

---

## AD-06 — Dedicated Management Network

Decision:

Isolate administrative systems and privileged management access
in a dedicated management network.

Rationale:

Administrative interfaces and privileged systems represent
high-value targets and should not share the same trust boundary
as user devices.

Consequences:

- reduced exposure of administrative access paths
- lower risk of privilege escalation from user networks
- improved separation of operational and privileged traffic

---

## AD-07 — Segmented DNS Access Policy

Decision:

Restrict DNS communication according to zone-specific policy rules.

Rationale:

DNS access can reveal internal infrastructure and should be controlled
according to trust level and operational need.

Consequences:

- reduced information exposure across zones
- clearer separation between internal and external name resolution
- improved policy enforcement for guest and untrusted networks

---

## AD-08 — VPN-Based Remote Access

Decision:

Provide remote administrative access exclusively through a VPN
connection.

Rationale:

Direct exposure of administrative services to the internet increases
attack surface and credential theft risk.

Consequences:

- reduced attack surface
- controlled administrative access paths
- centralized monitoring of remote sessions

---

## AD-09 — Certificate-Bound Remote Access Identity

Decision:

Bind remote administrative access to identity-based authentication
using certificate-bound device identity combined with multi-factor authentication.

Rationale:

Strong remote access security should rely not only on credentials,
but also on device-bound identity assurance.

Consequences:

- stronger assurance for remote administrative sessions
- reduced risk of unauthorized access through credential theft alone
- closer alignment with zero-trust-oriented access principles

---

## AD-10 — IDS in Alert-Only Mode

Decision:

Deploy IDS monitoring in alert-only mode.

Rationale:

Blocking traffic automatically can introduce operational risk
due to false positives.

The alert-only approach represents a deliberate architectural
trade-off between visibility and operational stability.

Consequences:

- improved visibility into suspicious activity
- reduced operational disruption
- support for investigation-driven incident response

---

## AD-11 — Centralized Logging

Decision:

Implement centralized logging with synchronized system time (NTP).

Rationale:

Incident investigation requires reliable event correlation
across multiple systems.

Consequences:

- improved incident reconstruction
- enhanced auditability
- support for SOC-readiness

---

## AD-12 — Evidence-Oriented Monitoring Model

Decision:

Design monitoring for evidentiary visibility and investigation support
rather than for full real-time SOC operations.

Rationale:

The modeled organization does not operate a dedicated 24/7 SOC and must
prioritize sustainable monitoring capabilities over continuous manual response.

Consequences:

- monitoring aligned with operational reality
- improved incident reconstruction capability
- support for SOC-readiness without assuming full SOC staffing

---

## AD-13 — Operational Simplicity Over Tool Density

Decision:

Prefer a smaller number of structurally effective controls over a large
set of operationally complex security tools.

Rationale:

Security architecture must remain maintainable within staffing and budget
constraints to remain effective over time.

Consequences:

- improved maintainability
- reduced configuration complexity
- better long-term operational sustainability