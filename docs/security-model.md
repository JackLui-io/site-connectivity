# Site Connectivity – Security Model

## 1. Security as an Architectural Property

In distributed environments, security cannot be treated
as a collection of isolated controls or configurations.

In the Site Connectivity model, security is considered
an **architectural property** that emerges from:

- Explicit trust boundaries
- Clear responsibility separation
- Minimal exposure by design
- Predictable connectivity relationships

This document describes the security principles
and governance model underpinning Site Connectivity.

---

## 2. Redefining the Security Boundary

### 2.1 From Perimeter to Site Boundary

Traditional network security models often rely on
a single perimeter concept:

- Inside is trusted
- Outside is untrusted

In distributed systems, this model no longer holds.

Site Connectivity replaces the perimeter with
**site-level security boundaries**.

Each site represents:
- A distinct trust domain
- An operational responsibility unit
- A security enforcement scope

---

### 2.2 The Role of the Site Gateway

The site gateway is the **sole security enforcement point**
between a site and the connectivity fabric.

Its responsibilities include:

- Traffic admission and routing control
- Policy enforcement at site granularity
- Isolation of internal LAN devices
- Exposure mediation for site services

By consolidating enforcement at the gateway,
security responsibilities become explicit and auditable.

---

## 3. Principle of Least Exposure

### 3.1 Default Non-Exposure

In the Site Connectivity model:

- No service is exposed by default
- No inbound access is assumed
- No public addressability is required

Connectivity must be explicitly declared
between sites or services.

This eliminates large classes of accidental exposure.

---

### 3.2 Overlay-Only Reachability

Services and devices are reachable only through
the connectivity fabric.

They are not:
- Directly addressable from the public internet
- Discoverable by external scanning
- Dependent on static firewall exceptions

This significantly reduces the attack surface
without increasing operational burden.

---

## 4. Trust Relationships and Policy Scope

### 4.1 Site-to-Site Trust

Trust is established **between sites**, not between devices.

This enables:
- Coarse-grained but explicit trust declarations
- Simplified policy reasoning
- Reduced policy sprawl

Trust relationships are intentional,
documented, and revocable.

---

### 4.2 Scoped Access Control

Access policies can be defined at multiple levels:

- Site-to-site reachability
- Service-level exposure
- Directional access (ingress / egress)

Policies are scoped to the minimum required
for operational needs.

---

## 5. Governance and Responsibility Separation

### 5.1 Clear Ownership Boundaries

Each site retains autonomy over:

- Internal addressing
- Local device management
- Operational procedures

Connectivity governance is limited to:
- Inter-site routing intent
- Exposure policies
- Trust relationships

This separation avoids centralized overreach
and aligns with organizational boundaries.

---

### 5.2 Auditability and Change Control

Because connectivity is defined at the site level:

- Policy changes are fewer and more visible
- Impact analysis is simpler
- Responsibility attribution is clearer

This improves audit readiness
and reduces operational risk.

---

## 6. Failure Isolation and Blast Radius Control

### 6.1 Containment by Design

Security incidents or misconfigurations
are naturally contained within a site boundary.

A compromised site does not imply:
- Automatic lateral movement
- Global trust collapse
- System-wide exposure

This limits blast radius
and simplifies incident response.

---

### 6.2 Controlled Degradation

Connectivity relationships can be:
- Suspended
- Limited
- Reconfigured

Without affecting internal site operations.

This supports resilient operations
under partial failure or active defense scenarios.

---

## 7. Alignment with Modern Security Thinking

While Site Connectivity is not a product
and does not mandate specific technologies,
its security model aligns with modern principles such as:

- Zero implicit trust
- Explicit access declaration
- Identity at architectural boundaries
- Separation of control and execution

The model focuses on **structural security**,
not reactive controls.

---

## 8. Scope and Non-Goals

This security model does **not** attempt to:

- Replace endpoint security solutions
- Define cryptographic primitives
- Enforce a single security product or framework

It provides a **governance-oriented security foundation**
upon which multiple technologies can coexist.

---

## 9. Summary

Site Connectivity embeds security into
the structure of distributed systems.

By elevating sites to first-class security domains
and consolidating enforcement at clear boundaries,
it enables scalable, auditable, and resilient
connectivity without relying on pervasive endpoint control.
