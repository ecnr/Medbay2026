# WORKFLOW_ARCHITECTURE

## Purpose

This document defines how MedBay processes a patient from first contact through outcome logging.

It focuses on the order of operations, the decision points, the consent model, and the difference between routine care and urgent care.

## Core Workflow Principle

MedBay should behave like a clinical state machine.

Each patient episode is a bounded session with clear start, decision, action, and closure states.

The workflow must be understandable both to clinicians and to the AI system itself.

## High-Level Flow

```text
Arrival / Request for care
        ↓
Triage and urgency assessment
        ↓
Patient identification and session creation
        ↓
Data capture and normalization
        ↓
AI interpretation and risk assessment
        ↓
Consent logic or emergency override
        ↓
Procedure selection
        ↓
Tool and module orchestration
        ↓
Execution / supervision / escalation
        ↓
Outcome verification
        ↓
Documentation and learning
```

## Session Model

Each case should be represented as one session.

A session contains:

- one patient,
- one event timeline,
- one or more procedures,
- one set of safety checks,
- one outcome record.

If multiple patients are present, they require separate sessions or separate MedBay units.

## Workflow Stages

### 1. Arrival / Request for Care

The system receives a patient, a referral, a rescue event, or a self-presentation.

Possible entry modes:

- walk-in,
- ambulance arrival,
- telemedicine intake,
- kiosk intake,
- staff referral,
- emergency incident intake.

### 2. Triage and Urgency Assessment

The first question is not what device to use.
It is whether the case is urgent, stable, or routine.

The AI should classify the situation into at least three operational states:

- **routine**,
- **urgent**,
- **critical / life-threatening**.

### 3. Patient Identification and Session Creation

The system creates a patient session and binds all future data to it.

Required actions:

- identify the patient,
- establish or locate record,
- create a case timeline,
- assign provenance to all data.

### 4. Data Capture and Normalization

The system collects what it can from available devices and interaction channels.

Examples:

- symptoms,
- vitals,
- imaging,
- laboratory data,
- operator notes,
- device telemetry,
- incident context.

The AI must normalize the data before making a decision.

### 5. AI Interpretation and Risk Assessment

The AI evaluates:

- what is wrong,
- how serious it is,
- what tools are available,
- what can be done safely,
- whether action must be immediate.

The AI should always know its own uncertainty.

### 6. Consent Logic or Emergency Override

This is one of the most important points in the workflow.

There are three major branches:

#### A. Patient can consent normally

The patient receives information, the planned procedure is explained, and the patient agrees.

#### B. Patient refuses

The patient may refuse the procedure.
The system records refusal and, where appropriate, a formal refusal record or reversal of consent.

The system may then close the current procedure, complete safe termination steps, and route the patient to alternative care.

#### C. Patient is unconscious or in immediate life-threatening danger

In this case the system may proceed under emergency rules.

The AI may decide directly when:

- the patient cannot consent,
- delay would create serious harm,
- the situation is clearly within a certified emergency workflow,
- the system has sufficient confidence and available tools.

This is not general autonomy.
This is emergency authority inside a narrow and explicit boundary.

### 7. Procedure Selection

After consent or emergency authorization, the system chooses the procedure.

The choice is based on:

- patient state,
- available modules,
- certified capabilities,
- site type,
- risk level,
- human availability,
- time constraints.

### 8. Tool and Module Orchestration

The AI assigns each task to the correct module.

Examples:

- monitoring,
- imaging,
- lab analysis,
- infusion support,
- robotics,
- communication,
- documentation.

The orchestration layer should behave like a conductor, not like a random collection of buttons.

### 9. Execution / Supervision / Escalation

The system may operate in one of several modes:

- **manual**: humans do the work, AI supports,
- **assisted**: AI suggests and guides,
- **supervised**: AI executes under human oversight,
- **emergency autonomous**: AI acts within a certified urgent workflow,
- **full workflow autonomous**: future mode for validated procedures.

If the system loses confidence, it should escalate or stop.

### 10. Outcome Verification

After the procedure, the system checks whether the intended outcome was achieved.

Examples:

- symptoms improved,
- bleeding controlled,
- obstruction resolved,
- imaging confirmed effect,
- patient stabilized,
- transfer arranged if needed.

### 11. Documentation and Learning

The final stage is always documentation.

The system must record:

- what happened,
- what was decided,
- why it was decided,
- who approved it,
- what devices were used,
- what result occurred,
- what should be learned.

## Consent and Refusal Logic

### Normal consent

The patient agrees to the procedure after being informed.

### Refusal / reversal

The patient may decline.
The workflow must allow the system to end the current intervention safely.

### Emergency exception

If the patient cannot consent and delay would be dangerous, the system may proceed inside a certified emergency envelope.

## Autonomy Boundaries

Autonomy is not a single switch.
It is a set of rules tied to procedure type and risk.

The system should be autonomous only when all of the following are true:

- the workflow is certified,
- the device set is known,
- the risk is bounded,
- the patient state fits the validated envelope,
- the system has sufficient confidence,
- fallback behaviour is available.

Outside that envelope, the AI must ask for human review or stop.

## Example Workflow Classes

### Class 1: Low-risk routine workflow

Examples:

- intake,
- triage,
- vitals,
- documentation,
- referral.

### Class 2: Supervised clinical workflow

Examples:

- guided imaging,
- guided lab work,
- monitored intervention support,
- standard assisted procedures.

### Class 3: Emergency workflow

Examples:

- unconscious patient,
- major trauma,
- airway danger,
- active bleeding,
- immediate threat to life.

### Class 4: Specialized workflow

Examples:

- specialty-only procedures,
- hospital-only procedures,
- rare interventions,
- multi-device combinations.

## Workflow State Machine

Suggested states:

- idle,
- intake,
- triage,
- identify,
- collect data,
- assess,
- consent,
- plan,
- execute,
- verify,
- close,
- learn,
- escalate,
- abort.

## Failure Handling

The system must handle:

- missing data,
- device failure,
- contradictory outputs,
- patient refusal,
- insufficient confidence,
- emergency deterioration,
- communication loss,
- power loss.

When failure occurs, the system should degrade safely rather than continue blindly.

## Human Role

Humans remain important for:

- legal consent where required,
- complex escalation,
- social judgment,
- supervision of uncertified workflows,
- procedure review,
- edge cases.

The goal is not to remove humans from medicine.
The goal is to stop human limitation from being the bottleneck where a machine can safely do the work.

## Open Questions

- Which workflows are certified for emergency autonomy?
- Which workflows are always human-approved?
- What refusal record format should be used?
- What is the minimum data set for safe triage?
- Which procedures are hospital-only in version one?
- Which workflows are ambulance-safe in version one?
