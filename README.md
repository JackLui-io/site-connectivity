# Site Connectivity

A reference architecture for secure, transparent connectivity
between distributed sites, edge networks, and cloud resources.

---

## What is Site Connectivity?

Site Connectivity is an architectural approach that enables
multiple physical sites, edge networks, and cloud services
to interconnect securely **without modifying existing LAN devices**.

It is designed for environments where:
- End devices cannot install agents
- Public exposure of services is undesired
- Networks are geographically distributed
- Security and operational simplicity are critical

---

## Why This Project Exists

In many real-world deployments (infrastructure, transportation,
industrial IoT, research networks), traditional VPN-based
solutions introduce operational complexity and security risks.

This project documents a **practical, production-oriented
connectivity model** that:

- Treats edge gateways as network identity anchors
- Enables site-to-site and site-to-cloud communication
- Preserves existing LAN addressing and device behavior
- Avoids public IP exposure of internal services

---

## Core Capabilities

- Transparent LAN-to-LAN connectivity
- Edge-to-cloud private access
- Multi-site routing and segmentation
- Centralized control with decentralized execution
- Incremental deployment without service interruption

---

## Typical Scenarios

- Site-to-Site (Branch / Facility Interconnection)
- Site-to-Cloud (Private access to cloud services)
- Multi-Site Aggregation
- Industrial or sensor networks without endpoint agents

See [docs/scenarios.md](docs/scenarios.md)

---

## Architectural Overview

This repository focuses on **architecture and system design**,
not on vendor-specific configuration steps.

See:
- [docs/overview.md](docs/overview.md)
- [docs/topology.md](docs/topology.md)

---

## Implementation Notes

OpenWrt-based gateways are used as a common reference
implementation due to their flexibility and edge suitability.

See:
- [openwrt/design.md](openwrt/design.md)

---

## Status

This project is under active exploration and documentation.
It reflects real-world deployments and iterative refinement.

---

## License

MIT
