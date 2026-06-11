# AI_ARCHITECTURE

## Purpose

This document defines the AI layer of MedBay.

MedBay is not an AI chatbot with a few devices attached.
It is a clinical orchestration platform in which AI coordinates intake, interpretation, workflow control, safety checks and learning across the installed device set.

## Design Goals

1. **Clinical usefulness before autonomy**
   - The first AI versions should reduce burden on clinicians and staff.
   - The AI should assist, not replace, unless a use case is validated for supervised or autonomous execution.

2. **One patient, one session**
   - A single MedBay unit handles one patient at a time.
   - The AI should keep a clear patient-session boundary and never confuse one patient with another.

3. **Network learning**
   - Every MedBay installation should be able to contribute validated learning signals to the wider fleet.
   - Shared learning must be privacy-preserving, auditable and versioned.

4. **Human override**
   - A clinician or operator must be able to stop, correct or overrule the AI at any time.
   - No autonomous action may bypass safety gates.

5. **Deployment flexibility**
   - The same AI architecture should support hospital units, clinic units and ambulance units.
   - The available tools may differ, but the reasoning and workflow structure should remain aligned.

## AI Layer Overview

```text
Patient / Incident
   ↓
Intake AI
   ↓
Data normalization and validation
   ↓
Diagnostic AI
   ↓
Risk and safety checks
   ↓
Workflow orchestration AI
   ↓
Device execution layer
   ↓
Outcome logging
   ↓
Fleet learning
```

The AI layer is best understood as a stack of specialized models rather than a single monolithic model.

## Core Subsystems

### 1. Intake AI

Responsibilities:

- collect symptoms,
- ask follow-up questions,
- gather structured history,
- support voice and text interaction,
- help a non-specialist user navigate the first steps.

This module should also support an experimental kiosk-style intake mode for public or low-footprint deployment.

### 2. Diagnostic AI

Responsibilities:

- interpret device outputs,
- combine imaging, lab and monitoring data,
- identify likely patterns,
- surface uncertainty,
- suggest what should be checked next.

The diagnostic layer should prefer evidence-based outputs and should always expose confidence and source traceability.

### 3. Treatment Planning AI

Responsibilities:

- propose next steps,
- sequence interventions,
- suggest tool usage,
- account for available modules,
- adapt recommendations to site type and certification.

In the early system, this is a recommendation engine.
Later, it may become a supervised executor for validated workflows.

### 4. Safety and Risk AI

Responsibilities:

- detect contradictions,
- check contraindications,
- detect missing data,
- identify unsafe plans,
- block or downgrade risky actions,
- trigger human review when uncertainty is high.

This is a mandatory layer, not an optional add-on.

### 5. Workflow Orchestration AI

Responsibilities:

- choose the next system action,
- coordinate devices and software modules,
- manage state transitions,
- maintain a procedure timeline,
- enforce the difference between suggestion and execution.

### 6. Learning AI

Responsibilities:

- learn from validated outcomes,
- update models and rules,
- compare predicted versus actual results,
- detect drift,
- support fleet-level improvement.

No learning update should be applied to production without validation.

### 7. Interaction AI

Responsibilities:

- talk to clinicians,
- talk to technicians,
- talk to patients,
- explain what the system is doing,
- display warnings and next steps in plain language.

## Model Types

The platform should use different model classes for different jobs.

### Structured reasoning models
Used for triage, planning and workflow decisions.

### Multimodal models
Used for imaging, sensors, lab data and other heterogeneous inputs.

### Language models
Used for dialogue, summarization, documentation and explanation.

### Policy and rule engines
Used for safety constraints, permissions and procedural boundaries.

### Simulation models
Used for digital twins, scenario testing and training.

## Data Flow

### Input sources

- medical history,
- patient-reported symptoms,
- vitals,
- laboratory outputs,
- imaging,
- device telemetry,
- operator commands,
- external referral data.

### Processing steps

1. ingest data,
2. validate it,
3. normalize it,
4. tag it with provenance,
5. run inference,
6. compute uncertainty,
7. compare against safety rules,
8. generate next-step suggestions,
9. route actions to the orchestration layer,
10. log all results.

## Autonomy Levels

### Level 0: Manual
Humans do everything. AI is only an observer or documentation helper.

### Level 1: Assisted
AI suggests, summarizes and highlights risk. Humans decide.

### Level 2: Supervised execution
AI can execute narrow workflows when a clinician authorizes it.

### Level 3: Conditional autonomy
AI can complete validated low-risk workflows on its own within tightly defined boundaries.

### Level 4: Fleet-learned autonomy
The network of MedBay systems can improve from validated cases and safely propagate improvements.

## Safety Model

The AI must never be allowed to act as if confidence were certainty.

Required safeguards:

- explicit uncertainty reporting,
- human approval for critical actions,
- emergency stop,
- immutable audit log,
- rollback capability,
- model version tracking,
- access control,
- secure update pipeline,
- offline fallback mode.

Any action with meaningful clinical risk must remain gated until the system is certified for that workflow.

## Deployment-Specific Behaviour

### Hospital mode

- broader device set,
- broader specialty support,
- more complex workflows,
- more integration with laboratory and imaging infrastructure.

### Clinic mode

- simpler intake,
- fast triage,
- documentation,
- referral support,
- limited device set.

### Ambulance mode

- rapid stabilization,
- minimal delay,
- robust offline operation,
- fewer specialties,
- strong focus on life-saving workflows.

The AI should not pretend every environment is equivalent. It should know the difference between a hospital and a moving vehicle, which is apparently revolutionary only to organizations that sell forms.

## Experimental Public Intake Mode

A compact public-facing intake booth or kiosk can be treated as a small MedBay front-end.

It should support:

- symptom intake,
- basic vitals,
- guided questionnaire,
- digital summary for the clinician,
- referral to a larger MedBay installation when needed.

This mode is experimental and should be treated as a stepping stone toward broader access.

## Learning and Validation Pipeline

1. Collect outcome data.
2. Remove or protect sensitive identifiers.
3. Validate the case context.
4. Compare AI suggestion against actual outcome.
5. Update only approved models or rule sets.
6. Deploy through a controlled release process.
7. Re-monitor after deployment.

## Recommended First AI Deliverables

- symptom intake assistant,
- triage assistant,
- patient summary generator,
- device orchestration prototype,
- safety gate engine,
- clinician-facing explanation panel,
- logging and audit module.

## Open Questions

- Which clinical workflows should be first-class targets?
- Which outputs are advisory only?
- Which modules may execute under supervision?
- Which models are local, and which are networked?
- Which data leaves the unit, and under what privacy rules?
- Which validations are required before autonomy increases?
