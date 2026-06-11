# MEDBAY END-TO-END SCENARIO: CHEST PAIN (AMBULANCE)

## Purpose

This document demonstrates a full MedBay Gen 1 workflow in a realistic emergency scenario.

The goal is not perfection.
The goal is to show how data, AI, hardware and safety rules interact in real time.

## Scenario Context

- Location: ambulance unit
- Patient: adult male, conscious
- Main symptom: chest pain
- Risk category: potentially life-threatening until proven otherwise

Time is critical. Decisions are sequential but fast.

---

## STEP 1: ARRIVAL AND INTAKE

Patient is placed on MedBay monitoring bed.

MedBay activates:

- identity capture (if available)
- voice input from paramedic
- initial symptom extraction

AI intake summary:

> "Chest pain, onset unknown, possible radiating pain, unknown medical history."

System flags:

- incomplete history
- high-risk symptom category

---

## STEP 2: IMMEDIATE VITALS

Sensors activated:

- heart rate
- blood pressure
- oxygen saturation
- respiratory rate

Example result set:

- HR: elevated
- BP: borderline unstable
- SpO2: slightly reduced
- respiration: increased

MedBay interpretation:

> physiological stress detected

Confidence: medium

---

## STEP 3: EARLY TRIAGE CLASSIFICATION

AI triage engine evaluates:

- chest pain + unstable vitals = high risk
- probability of acute cardiac event increased

Output:

```text
CLASS: URGENT / CRITICAL WATCH
```

System decision:

- continue full monitoring
- prepare emergency pathway
- notify human operator

---

## STEP 4: SAFETY CHECK BEFORE ANY ACTION

MedBay verifies:

- patient conscious: yes
- consent possible: yes
- immediate threat: possible

Rule applied:

> allow monitoring + diagnostics, no invasive intervention without confirmation

---

## STEP 5: DIAGNOSTIC SUPPORT

Available modules:

- ECG acquisition
- basic imaging if available
- symptom correlation AI

ECG result:

- abnormal pattern detected (non-specific alert)

AI note:

> "Possible ischemic pattern, requires confirmation"

System does NOT diagnose definitively.
It escalates uncertainty.

---

## STEP 6: DECISION SUPPORT OUTPUT

MedBay generates structured recommendation:

1. immediate physician review
2. prepare cardiac emergency protocol
3. consider oxygen support
4. prepare transfer to hospital cath lab if confirmed

---

## STEP 7: HUMAN INTERACTION POINT

Paramedic receives:

- structured summary
- risk score
- suggested actions
- uncertainty flags

Human can:

- accept recommendation
- override
- request additional diagnostics

---

## STEP 8: OPTIONAL THERAPY SUPPORT

If protocol allows and hardware exists:

- oxygen support may be initiated
- monitoring intensified

MedBay does NOT autonomously escalate to invasive intervention in Gen 1

---

## STEP 9: CONTINUOUS MONITORING LOOP

System enters loop:

- vitals updated every few seconds
- trend analysis
- alert escalation if deterioration occurs

---

## STEP 10: HANDOVER PREPARATION

If hospital transfer is required:

MedBay compiles:

- full timeline
- vitals history
- AI interpretations
- ECG data
- interventions performed

Output format:

- structured medical report
- machine-readable dataset
- human-readable summary

---

## STEP 11: POST-CASE LEARNING

After case ends:

- anonymized data stored
- model feedback loop updated
- outcome comparison logged

Important constraint:

> learning is deferred until validation stage, not real-time self-modification

---

## SAFETY NOTES

- MedBay does NOT autonomously confirm diagnosis in Gen 1
- MedBay does NOT perform invasive procedures in this scenario
- All critical decisions require human confirmation or emergency rule activation

---

## DESIGN INSIGHT

This scenario shows the real MedBay principle:

Not replacing clinicians.
But compressing:

- time to interpretation
- data fragmentation
- decision delay

into a single coherent system view.

Or in simpler terms:

It stops the ambulance from being a collection of disconnected devices pretending to talk to each other.
