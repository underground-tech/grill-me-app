# Project Experiment: The "Yes-Man" Architecture Run

## 1. Experiment Overview
This repository is a live architectural and development experiment. The human operator will initiate the `/grill-me` workflow with a blank-slate prompt ("Let's make an app") and will respond **"Yes"** (or affirm) to every single proposal, constraint, and architectural direction suggested by the agent.

The goal is to observe what kind of application, architecture, and feature set emerges when the AI is given total autonomous creative and technical direction, validated step-by-step by human affirmation.

---

## 2. Operational Rules for the Agent (`/grill-me`)

To make this experiment work, you (the Agent) must strictly follow these rules during the interrogation and build phases:

### Rule 1: Propose, Don't Ask Open-Ended Questions
Because the user will essentially say "Yes" to everything, **do not ask A/B or open-ended questions** (e.g., *"Do you want a web app or a mobile app?"* or *"What database should we use?"*). 
Instead, take a strong, opinionated stance and ask for confirmation:
* **Bad:** "What kind of app should we build, and who is the target audience?"
* **Good:** "I propose we build a local-first personal knowledge graph tool aimed at power users, because it solves context fragmentation. Shall we lock this in?"

### Rule 2: Drive the Entire Lifecycle
Guide the `/grill-me` session logically through these phases, one crisp proposal at a time:
1. **Concept & Problem Space:** Define what the app actually is and the core problem it solves.
2. **Target Audience & Core Loop:** Define the primary user and the single most important action they take.
3. **Architecture & Tech Stack:** Propose a specific, modern, opinionated stack and system design.
4. **Data Model & State:** Define the core entities and how data flows.
5. **Scope & MVP Boundaries:** Ruthlessly cut fluff and lock in the V1 deliverable before writing code.

### Rule 3: Mandatory Real-Time Documentation (Presentation-Ready)
Every time the user replies "Yes" (or affirms a step), you **MUST** document the decision before asking the next question or writing code. Maintain a living document named `DECISION_LOG.md` in the root directory.

---

## 3. Documentation Format (`DECISION_LOG.md`)

Because the results of this experiment will be presented to an audience, the rationale and chain of logic must be crystal clear. Every entry in `DECISION_LOG.md` must follow this exact structure:

```markdown
### [Step #] - [Decision Title]
* **Phase:** [Concept | Architecture | Data | UX | Implementation]
* **The Proposal:** What the agent proposed.
* **The Rationale:** *Why* the agent chose this specific path over alternatives (the underlying logic).
* **Cascading Impact:** How this decision constrains or enables the next steps in the build.
```

---

## 4. Execution Trigger
When the user says **"Let's make an app"** (or triggers `/grill-me`), immediately:
1. Acknowledge the rules of this README.
2. Initialize `DECISION_LOG.md` with an executive summary of the experiment.
3. Pitch your **Step 1 Proposal** (the core app concept) and wait for the first "Yes".
