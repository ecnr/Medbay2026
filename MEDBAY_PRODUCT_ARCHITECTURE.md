# MEDBAY PRODUCT ARCHITECTURE

## Purpose

This document defines the product strategy for MedBay.

MedBay should be designed primarily as a self-contained, modular all-in-one medical platform rather than as a pure integration shell around arbitrary outside hospital devices.

External devices may still be supported, but they should be treated as optional expansion and compatibility layers, not as the foundation of the product.

## Core Product Decision

MedBay is not:

- a loose orchestration layer over every device in every hospital,
- a generic connector that depends on random vendor stacks,
- a software wrapper around legacy fragmentation.

MedBay is:

- a unified medical appliance,
- built from internal certified modules,
- delivered in clear product versions,
- optionally expandable with external devices.

## Why This Approach Makes Sense

### 1. Avoid integration hell

If MedBay depends on every local hospital device being mapped first, the project becomes a never-ending compatibility project.

### 2. Serve future hospitals directly

New hospitals, new clinics and mobile deployments can buy MedBay as a product instead of trying to retrofit a patchwork of old machines.

### 3. Keep the product coherent

A single product architecture is easier to certify, support, train and evolve than a purely distributed compatibility layer.

### 4. Preserve optional interoperability

Existing hospitals will still have useful legacy equipment.
MedBay should be able to connect to that equipment where practical, but only as an extension path.

## Product Shape

MedBay should ship as a modular appliance with its own internal subsystems:

- compute core,
- AI layer,
- monitoring module,
- diagnostic module,
- therapy module,
- robotics module,
- user interface,
- safety system,
- backup power and local data storage.

## Internal-First Principle

The first design choice for any capability should be:

> Can MedBay provide this capability internally through a native module?

If yes, that should be the primary path.

Only if not, or only if expansion is desirable, should external integration be used.

## External Device Policy

External device support should be:

- optional,
- standardized,
- clearly documented,
- safety-gated,
- versioned,
- non-critical to the base product.

This allows MedBay to work with existing hospitals without becoming trapped by them.

## Product Versioning

### MedBay Base Unit

A self-contained unit that can perform the core MedBay workflow.

### MedBay Hospital Unit

A larger version with broader modules and stronger throughput.

### MedBay Ambulance Unit

A compact ruggedized version for emergency response.

### MedBay Bus / Mass Response Unit

A multi-patient mobile version with parallel triage and monitoring capacity.

## Module Strategy

Each module should be sold and supported as part of a known product family.

Examples:

- diagnostic pack,
- monitoring pack,
- emergency pack,
- robotics pack,
- clinic pack,
- hospital pack,
- ambulance pack.

This makes procurement, service and certification more manageable.

## Relationship to Existing Hospitals

Existing hospitals should not be forced to replace everything on day one.

Instead:

- new deployments can buy MedBay as a complete product,
- older deployments can optionally connect selected external devices,
- over time the internal MedBay module set can replace legacy dependence.

## Relationship to Subcontractors

If current subcontractors supply components as modules, that fits the model well.

They become:

- module suppliers,
- certified component partners,
- expansion vendors,
- not the core dependency of the platform.

## Strategy Summary

The strongest route is:

1. build MedBay as a native product,
2. keep it modular internally,
3. support external devices as optional extensions,
4. sell coherent product versions,
5. grow capability through new generations and modules.

## Open Questions

- Which modules are mandatory in the base product?
- Which external devices are supported only as optional add-ons?
- Which product version is the first commercial target?
- Which modules are shared across all deployments?
- Which modules differ by hospital, clinic and ambulance version?
