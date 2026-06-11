# MEDBAY MINIMUM VIABLE PRODUCT

## Purpose

This document defines the first real MedBay prototype.

The goal of the MVP is not to solve all medicine.
The goal is to prove that existing medical devices, software and AI can be integrated into a single controlled clinical workflow.

## MVP Definition

The first MedBay unit should be able to:

- receive a patient,
- create a session,
- collect and normalize data,
- perform AI-assisted triage,
- decide whether the case is routine, urgent or critical,
- route the case into the correct workflow,
- support one selected clinical pathway end-to-end,
- document the result,
- learn from the case.

## What the MVP Is Not

The first MedBay is not required to:

- cure all diseases,
- perform every specialty procedure,
- solve nanomedicine,
- replace all human clinicians,
- achieve full general autonomy,
- fit every possible deployment profile at once.

The MVP should be narrow enough to build, but broad enough to prove the platform idea.

## Recommended First Capabilities

### 1. Intake

The system should capture:

- patient identity,
- symptoms,
- basic history,
- urgency clues,
- available context from staff or rescue teams.

### 2. Triage

The system should classify the case as:

- routine,
- urgent,
- life-threatening.

### 3. Monitoring

The first unit should support integration with basic monitoring tools such as:

- heart rate,
- blood pressure,
- oxygen saturation,
- temperature,
- respiration.

### 4. Documentation

The system should create a structured patient record and a procedural log.

### 5. Clinical Guidance

The AI should propose next steps and explain why.

### 6. Emergency Pathway

The system should be able to switch into emergency handling when the patient cannot consent or when delay is dangerous.

### 7. Consent and Refusal Handling

The system should support:

- normal consent,
- refusal,
- reversal or termination of the procedure where appropriate,
- emergency override where legally and clinically justified.

## MVP Device Set

The first prototype should prefer devices that already exist and can be integrated through data or control interfaces.

Suggested initial classes:

- monitoring devices,
- imaging interfaces,
- basic lab interfaces,
- communication systems,
- documentation tools,
- one or more therapy delivery modules,
- one or more robotic or semi-robotic modules where appropriate.

## MVP Workflow

```text
Patient arrival
    ↓
AI intake
    ↓
Triage
    ↓
Data capture
    ↓
Risk assessment
    ↓
Consent or emergency rule
    ↓
Procedure selection
    ↓
Execution or escalation
    ↓
Outcome check
    ↓
Documentation and learning
```

## MVP Success Criteria

The MVP succeeds if it can demonstrate that:

- the same platform can handle a real patient session,
- the AI can coordinate devices and workflow,
- the system can operate safely under human supervision,
- the system can support a bounded urgent workflow,
- the result is traceable and auditable.

## Version One Strategy

Version one should focus on the strongest existing medical use cases where integration creates immediate value.

Examples:

- triage and intake,
- monitoring and alerting,
- assisted diagnostics,
- structured documentation,
- common procedures supported by existing devices,
- emergency stabilization workflows.

## Suggested Deployment Order

### Step 1
Software-only simulation.

### Step 2
Single patient, single workflow prototype.

### Step 3
Basic device integration in a controlled environment.

### Step 4
Supervised clinical pilot.

### Step 5
Limited real-world deployment.

## Key Design Rule

The first MedBay should be able to do one useful patient journey very well.

That is more valuable than pretending to do everything at once.

## Open Questions

- Which single workflow should be first?
- Which devices are easiest to integrate first?
- Which site type should receive the first prototype?
- Which safety gates are mandatory from day one?
- Which output must be human-reviewed in the MVP?
