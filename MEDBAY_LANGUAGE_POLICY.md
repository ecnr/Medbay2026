# MEDBAY LANGUAGE POLICY

## Purpose

This document defines how language versions are handled across the MedBay repository.

MedBay is a bilingual system:
- English = engineering and source-of-truth layer
- Czech = communication and presentation layer

---

## Core Principle

Every important document in MedBay follows a structured language model.

There are no ad-hoc translations.
There are no partial exceptions.

---

## Language Roles

### English (.md)

English is the technical source of truth.
It defines:
- system architecture
- product requirements
- module definitions
- AI and device logic
- integration rules

English is used for:
- development
- system design
- external technical integration

---

### Czech (.cs.md)

Czech is the communication layer.
It defines:
- explanation of system concepts
- presentation to non-technical stakeholders
- national / local communication
- simplified interpretation of architecture

Czech is NOT a strict technical mirror.
It may include clarifications and contextual explanations.

---

## File Naming Convention

Each major document SHOULD have two versions:

- DOCUMENT_NAME.md        (English)
- DOCUMENT_NAME.cs.md     (Czech)

Example:
- ARCHITECTURE.md
- ARCHITECTURE.cs.md

---

## Directory Structure (Recommended)

/docs/en/   → English technical documentation
/docs/cs/   → Czech communication documentation

OR parallel files in root for core documents.

---

## Synchronization Rule

- English version is updated first
- Czech version follows after changes
- No orphan translations (Czech without English base is not allowed for core docs)

---

## Translation Guidelines

Czech versions should NOT be literal translations.
They should:
- simplify technical terms when possible
- explain concepts instead of copying structure blindly
- preserve meaning, not syntax

Example:

English:
AI orchestration layer

Czech:
Vrstva, která koordinuje jednotlivé části umělé inteligence v systému

---

## Exceptions

Not all files require translation.

Optional Czech coverage:
- technical deep-dive research files
- internal development notes
- experimental modules

Required Czech coverage:
- INDEX.md
- ARCHITECTURE.md
- PRODUCT ARCHITECTURE
- CORE CLINICAL SCENARIOS

---

## System Rule

MedBay treats language as a system layer, not as duplication.

Language separation exists to:
- improve clarity
- reduce ambiguity
- support multi-audience communication

Not to multiply maintenance burden.
