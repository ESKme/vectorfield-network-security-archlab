# Architecture Summary

This document provides a condensed overview of the enterprise network
security architecture designed in the VECTORFIELD study.

The architecture focuses on **structural security controls** that reduce
attack surface and limit lateral movement while remaining operationally
maintainable for a mid-sized organization.

The design is derived from stakeholder requirements and follows a
traceability-driven architecture methodology.

---

## Network Segmentation Model

The network architecture is organized into **security zones implemented through VLAN segmentation**.

Each VLAN represents a trust boundary with explicitly controlled communication paths.

Typical zones include:

- Corporate user network
- Server network
- Guest network
- Management network
- Infrastructure services

Communication between zones follows a **strict default-deny policy**.

Only explicitly defined service flows are allowed.

---

## Central Enforcement

The primary enforcement point is a **pfSense firewall** positioned between network segments.

The firewall enforces:

- inter-zone access control
- controlled inbound services
- DNS access restrictions
- logging and monitoring visibility

Firewall rules are implemented using a **pin-hole access model**, meaning that
only narrowly defined service ports are allowed between zones.

---

## Remote Access Architecture

Remote access is implemented through a **VPN-based access model**.

Key characteristics:

- certificate-bound authentication
- multi-factor authentication
- restricted access paths
- centralized logging

Direct exposure of internal services to the internet is avoided.

---

## Logging and Monitoring

The architecture includes centralized logging capabilities designed to support
incident investigation and SOC-readiness.

Key elements include:

- centralized log collection and aggregation
- NTP-based time synchronization
- IDS deployment in alert-only mode
- log retention for incident analysis

Monitoring is designed to provide **evidence-oriented visibility** rather than
real-time SOC operations.

---

## Security Objectives

The architecture aims to achieve the following goals:

- reduction of attack surface
- limitation of lateral movement
- containment of compromised hosts
- traceability of security-relevant events
- operationally maintainable security controls