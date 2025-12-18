# Site Connectivity – Architectural Overview

## 1. Background

Modern infrastructure is increasingly distributed.

Enterprises, research institutions, and industrial systems
are no longer confined to a single network perimeter.
Instead, they operate across:

- Multiple physical sites
- Edge locations with limited resources
- Cloud environments hosting critical services
- Legacy LAN devices that cannot be modified

Traditional connectivity models struggle to adapt to this reality.

---

## 2. The Core Problem

Most existing network interconnection solutions are built
around one of the following assumptions:

1. All endpoints can install agents or clients
2. Public IP exposure is acceptable
3. Network topology is relatively static
4. Security boundaries are defined by physical location

In real-world deployments, these assumptions often fail.

Common challenges include:

- LAN devices (sensors, controllers, embedded systems)
  that cannot install additional software
- Security policies that prohibit exposing internal services
  to the public internet
- Operational complexity of managing site-to-site VPNs
  at scale
- Fragile configurations tightly coupled to specific vendors
  or network layouts

---

## 3. Rethinking Connectivity: From Tunnels to Sites

Site Connectivity introduces a different abstraction:

> **Connectivity is established between sites, not devices.**

Instead of treating each endpoint as a security principal,
the model elevates the **site gateway** to a first-class entity.

A site gateway represents:
- The identity of a physical or logical location
- The routing boundary of a LAN
- The security enforcement point for that site

This shift enables connectivity without altering
the behavior of devices inside the LAN.

---

## 4. Architectural Principles

The Site Connectivity model is built on five core principles:

### 4.1 Gateway-Centric Identity

Each site is anchored by a gateway that:
- Participates in the overlay network
- Represents the site’s trust boundary
- Enforces routing and access policies

Endpoints behind the gateway remain unaware of the overlay.

---

### 4.2 Transparent LAN Integration

LAN devices:
- Keep their original IP addressing
- Do not require software installation
- Are not aware of remote sites or cloud networks

Connectivity is achieved through routing, not tunneling per device.

---

### 4.3 Decoupled Control and Transport

Control-plane decisions (authorization, routing intent)
are separated from the data-plane transport.

This allows:
- Centralized management
- Decentralized execution
- Incremental expansion of sites

---

### 4.4 Least-Exposure Networking

Services are reachable only through the overlay network.

There is no requirement to:
- Expose public IP addresses
- Open inbound firewall ports
- Maintain static NAT mappings

This significantly reduces attack surface.

---

### 4.5 Incremental Adoption

Sites can be added one by one.

Existing networks continue to function during deployment,
allowing gradual rollout without service interruption.

---

## 5. Typical Topologies

The architecture supports multiple deployment patterns,
including but not limited to:

- Site-to-Site connectivity
- Site-to-Cloud private access
- Hub-and-spoke aggregation
- Multi-site partial mesh

These patterns are described in detail in:
- [topology.md](topology.md)
- [scenarios.md](scenarios.md)

---

## 6. Technology-Agnostic Design

While this repository references specific implementations
(e.g. OpenWrt-based gateways),
the architecture itself is **technology-agnostic**.

The principles described here can be implemented using
different overlay technologies, routing mechanisms,
and hardware platforms.

The focus of this project is on **system design**, not tools.

---

## 7. Intended Audience

This project is intended for:

- Network and infrastructure architects
- Platform and systems engineers
- Organizations operating distributed or edge-heavy networks
- Teams exploring secure alternatives to traditional VPN models

---

## 8. Scope and Non-Goals

This repository does **not** aim to:
- Provide step-by-step configuration tutorials
- Compare specific vendors or products
- Replace existing SD-WAN or zero-trust solutions

Instead, it documents a **connectivity model**
that can coexist with, or complement, existing systems.

---

## 9. Summary

Site Connectivity reframes networking from a device-centric
problem to a site-centric architectural model.

By shifting trust, routing, and security enforcement
to the site gateway layer, it enables scalable,
secure, and transparent interconnection of
distributed environments without modifying endpoints.
