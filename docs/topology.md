# Site Connectivity – Topology Models

## 1. Purpose of This Document

This document describes the **logical topology models**
supported by the Site Connectivity architecture.

Rather than focusing on physical network diagrams,
it defines **structural patterns** that can be reused
across different environments, scales, and industries.

These topology models represent **design intent**,
not implementation constraints.

---

## 2. Fundamental Abstractions

Before discussing topology, several abstractions must be defined.

### 2.1 Site

A *site* represents a bounded network domain, such as:

- A physical location (facility, branch, station)
- A logical environment (cloud VPC, private segment)
- An operational boundary with independent administration

A site may contain:
- One or more LAN segments
- Devices that cannot be modified or instrumented
- Local operational constraints

---

### 2.2 Site Gateway

Each site is anchored by a **site gateway** that:

- Represents the site in the connectivity fabric
- Acts as the routing and policy enforcement point
- Separates local network concerns from inter-site concerns

The gateway abstracts internal complexity
and presents a stable interface to other sites.

---

### 2.3 Overlay Connectivity Fabric

Sites are interconnected through an overlay fabric
that provides:

- Address reachability between sites
- Logical separation from the underlying transport
- Policy-driven connectivity relationships

The fabric does not require direct physical adjacency
between sites.

---

## 3. Topology Design Principles

All supported topologies follow these principles:

1. **Site-level connectivity, not device-level**
2. **Explicit relationships between sites**
3. **Minimal assumptions about physical layout**
4. **Topology evolution without service disruption**

---

## 4. Core Topology Models

### 4.1 Point-to-Point (Two-Site Model)

#### Description

The simplest topology connects two sites directly.

Typical use cases include:
- Interconnection between two facilities
- Primary–backup site relationships
- Isolated environments requiring private linkage

#### Characteristics

- One logical connection
- Symmetric trust relationship
- Minimal routing complexity

#### Design Notes

This model establishes the baseline
for all more complex topologies.

---

### 4.2 Hub-and-Spoke Model

#### Description

A central site (hub) connects to multiple remote sites (spokes).

The hub typically hosts:
- Shared services
- Management systems
- Aggregation functions

Remote sites do not directly communicate with each other
unless explicitly allowed.

#### Characteristics

- Centralized control
- Predictable traffic flow
- Simplified policy enforcement

#### Design Notes

This model is well-suited for:
- Early-stage deployments
- Environments with strict central governance
- Gradual onboarding of new sites

---

### 4.3 Partial Mesh Model

#### Description

Selected sites are interconnected based on
functional or operational requirements.

Not all sites have equal connectivity.

#### Characteristics

- Flexible communication patterns
- Reduced central bottlenecks
- Targeted trust relationships

#### Design Notes

Partial mesh topologies balance
operational efficiency and complexity.
They require explicit design intent
to avoid unintended coupling.

---

### 4.4 Full Mesh Model

#### Description

All sites are interconnected with each other.

This model is typically used in:
- Small-scale deployments
- High-availability environments
- Collaborative research or operations

#### Characteristics

- Maximum connectivity
- High routing complexity
- Increased policy surface

#### Design Notes

Full mesh topologies scale poorly
without strong abstraction and automation.
They should be used selectively.

---

## 5. Site-to-Cloud as a Topology Variant

### 5.1 Conceptual Treatment

In Site Connectivity, a cloud environment
is treated as a **logical site**.

It follows the same rules as physical sites:
- Gateway-anchored identity
- Explicit connectivity relationships
- Controlled exposure of services

---

### 5.2 Topological Implications

Cloud sites often act as:
- Hubs in hub-and-spoke models
- Service aggregation points
- Control-plane coordination centers

This allows physical and virtual sites
to coexist within a unified topology.

---

## 6. Topology Evolution and Scaling

### 6.1 Incremental Expansion

Topologies can evolve through:
- Addition of new sites
- Reclassification of site roles
- Gradual introduction of mesh relationships

Existing sites do not require reconfiguration
when new sites are introduced.

---

### 6.2 Role Reassignment

A site may change roles over time:
- Spoke → Hub
- Peripheral → Core
- Temporary → Permanent

The topology model supports these transitions
without architectural redesign.

---

## 7. Topology and Operational Boundaries

Topology design also defines:

- Fault domains
- Security boundaries
- Operational ownership
- Responsibility separation

Explicit topology modeling helps prevent
accidental coupling between unrelated sites.

---

## 8. Summary

Site Connectivity topology models
provide a structured way to reason about
distributed network relationships.

By treating sites as first-class entities
and gateways as stable anchors,
complex interconnections can be designed,
evolved, and operated with clarity
across heterogeneous environments.
