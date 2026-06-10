# SYSTEM_REQUIREMENTS

## 1. Scope

MedBay is a medical platform that integrates existing and future medical devices, software modules and AI decision support into one coordinated system.

The first version is not defined by one specific procedure. It is defined by integration:

- integration of diagnostic devices,
- integration of therapeutic devices,
- integration of workflow control,
- integration of AI,
- integration of safety and human override,
- integration of deployment across hospital and ambulance contexts.

## 2. Operational unit

### 2.1 Patient concurrency

One MedBay unit treats **one patient at one time**.

If more patients are present, they require:

- more MedBay units, or
- a larger multi-unit deployment such as a MedBay bus.

### 2.2 Site of use

The system must be able to run in:

- hospitals,
- ambulances,
- primary care offices,
- specialist outpatient settings,
- emergency incident response vehicles.

A future hospital installation and a future ambulance installation may become functionally equivalent, but the first generations will not be identical.

## 3. First-generation purpose

The first generation should focus on:

- device integration,
- AI integration,
- workflow orchestration,
- safe assistance,
- supervised use,
- future autonomy readiness.

It should not be limited to one narrow specialty unless that is temporarily needed for development.

The practical goal is to make existing medical technology work together as one platform instead of a collection of disconnected machines.

## 4. Procedure strategy

### 4.1 Core principle

The system should be able to decide, based on the available tools and certified capabilities, what it can safely do.

### 4.2 Hospital and ambulance capabilities

In the long term, hospital and ambulance versions should share the same core architecture.

At the beginning, the ambulance version may intentionally exclude certain specialised procedures, such as dental care, unless the mobile unit is explicitly designed for that specialty.

Specialised and rare procedures may initially remain a hospital-only capability.

### 4.3 Future principle

In the long term, the distinction between hospital and ambulance should be mainly about available equipment, power, space and certification, not about arbitrary administrative prohibition.

## 5. AI requirements

### 5.1 AI as the coordination layer

AI is a core requirement, not an optional add-on.

It should be able to:

- guide intake,
- ask questions,
- collect symptoms,
- interpret data,
- suggest likely next steps,
- supervise workflows,
- check safety constraints,
- decide which tools can be used,
- decide when human intervention is required.

### 5.2 Experimental AI physician kiosk

The project should include an experimental low-footprint AI primary-care style module inspired by public AI health kiosk concepts already being deployed in China.

This module should be treated as:

- experimental at first,
- useful for triage and simple consultation,
- compatible with remote human supervision,
- a stepping stone toward broader automation.

### 5.3 Learning model

The system should learn from completed procedures across the network of MedBay installations.

Requirements:

- one installation can improve others,
- learning must preserve safety boundaries,
- shared improvements must be validated before deployment,
- sensitive data must be protected.

## 6. Hardware integration requirements

The platform should integrate existing categories of devices rather than waiting for a single perfect machine.

Supported classes should include:

- monitors,
- imaging,
- lab interfaces,
- infusion and delivery systems,
- robotics,
- telemedicine components,
- emergency stabilization tools,
- clinical input devices,
- user interaction interfaces.

The system should be useful even if the first generation only integrates a subset of these.

## 7. Size and physical form factor

### 7.1 Ambulance compatibility

The baseline engineering target should be a form factor that can fit into an ambulance.

### 7.2 Miniaturization

Extreme sci-fi miniaturization is not required for the first model.

The project should prefer:

- robustness,
- serviceability,
- modularity,
- easy replacement,
- simple operation.

### 7.3 Operating simplicity

The user experience should be as simple as possible.

The system should be operable with minimal training, ideally closer to the simplicity of a printer than a traditional hospital department.

## 8. Staffing model

The first generation may still require a full human team around it, similar to a current robotic surgery setup.

That is acceptable.

The direction of travel is:

- first: humans plus AI plus devices,
- later: fewer human interventions,
- final aim: maximum automation with safe override.

## 9. Patient usability

A non-specialist or even an untrained patient should be able to obtain help in a degraded mode.

This does not mean the system must be fully autonomous from day one.
It means the interface and workflow must not collapse when expert staff are absent.

## 10. Cost requirements

The cost target should be derived from the cost of the devices and modules being integrated.

The project should use a parts-based economic model:

- calculate the cost of the integrated technologies,
- calculate integration and maintenance overhead,
- design toward a total system cost that is materially lower than buying the same capabilities as a loose collection of isolated devices.

The goal is not luxury duplication.
The goal is integrated capability per unit cost.

## 11. Power and resource use

No final power budget is fixed yet.

For now the requirement is:

- simple power management,
- safe shutdown,
- compatibility with mobile operation,
- predictable resource consumption,
- graceful degradation when a subsystem is unavailable.

## 12. Autonomy requirements

### 12.1 Assisted mode

This is the required first operating mode.

### 12.2 Supervised mode

AI may drive limited workflows under human control.

### 12.3 Future autonomous mode

When sufficiently trained and validated, the same platform should be able to act more independently.

The network of MedBay systems should learn from every validated case.

## 13. Exclusions for the first generation

The first generation does not need to solve everything.

Not required at launch:

- full nanomedicine,
- full tissue regeneration,
- full autonomous surgery,
- perfect miniaturization,
- universal specialty coverage,
- one-box replacement for all hospital infrastructure.

These are future capabilities, not launch blockers.

## 14. Primary success criteria

The first version succeeds if it can:

- integrate a meaningful set of real medical devices,
- use AI to coordinate them,
- support one patient safely,
- work in a constrained physical footprint,
- run in a hospital or ambulance context,
- reduce fragmentation of care,
- generate useful data for later versions.

## 15. Open questions for later documents

- Which device categories are in the first hardware set?
- Which procedures are permitted in ambulance mode?
- Which procedures remain hospital-only?
- What is the canonical data schema?
- What standards are required for interoperability?
- What is the minimum safe human staffing model?
- What is the first deployable clinical workflow?
