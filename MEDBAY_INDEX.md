# MEDBAY INDEX

## Purpose

This file is the navigation layer of the MedBay repository.
It defines how to enter, understand, and traverse the system documentation.

MedBay is not a collection of documents.
It is a structured system with multiple entry points.

---

# ENTRY POINTS (HOW TO READ THIS REPOSITORY)

## 1. System Overview (Start Here)

ARCHITECTURE.md
- Defines overall system structure
- Core concepts of MedBay
- System boundaries and principles

---

## 2. Product Definition

MEDBAY_PRODUCT_ARCHITECTURE.md
- Defines MedBay as a physical + software product
- Modular all-in-one medical system
- Ambulance / hospital / mobile variants

---

## 3. Hardware Structure

MEDBAY_HARDWARE_ARCHITECTURE.md
- Sensors, modules, device architecture
- Safety systems
- Physical deployment models

---

## 4. Clinical Behavior (Real Use)

MEDBAY_SCENARIO_CHEST_PAIN_AMBULANCE.md
- End-to-end emergency workflow
- Real-time decision logic
- Interaction between AI, hardware, and humans

---

## 5. Ecosystem Mapping

GitHubMedicalCommunityLinks.md
- Open-source medical ecosystem overview
- Potential modules and dependencies
- AI / imaging / robotics / hospital systems

---

# SYSTEM STRUCTURE OVERVIEW

MEDBAY consists of five interacting layers:

1. Clinical Layer
   - patient workflows
   - triage
   - emergency protocols

2. AI Decision Layer
   - analysis
   - recommendations
   - risk scoring

3. Device Layer
   - sensors
   - imaging
   - therapeutic modules

4. Product Layer
   - hospital unit
   - ambulance unit
   - mobile unit

5. Ecosystem Layer
   - external open-source modules
   - standards (DICOM, HL7, FHIR)

---

# LANGUAGE STRUCTURE

- .md = English technical version
- .cs.md = Czech communication version

English is the engineering source of truth.
Czech is the communication layer.

---

# DESIGN PRINCIPLES

- Modular by design
- Internal-first architecture
- External systems are optional extensions
- Safety overrides autonomy
- AI supports, does not blindly replace clinical responsibility (Gen 1)

---

# MISSING / FUTURE DOCUMENTS

Planned additions:

- MEDBAY_CLINICAL_WORKFLOW_LIBRARY.md
- MEDBAY_DATA_MODEL.md
- MEDBAY_AI_ARCHITECTURE.md
- MEDBAY_DEVICE_INTEGRATION.md
- MEDBAY_SAFETY_MODEL.md

---

# NAVIGATION RULE

If you are lost in the repository:

Return to this file.
Then choose a domain:
- system
- product
- hardware
- clinical scenario
- ecosystem

MedBay is intentionally structured as a layered system, not a flat documentation set.
