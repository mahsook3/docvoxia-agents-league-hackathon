# Docvoxia AI Engineering Instructions

## Project Mission

Build Docvoxia, a Real-Time Multilingual Clinical Reasoning Agent.

This is NOT a transcription application.

This is NOT a chatbot.

This is NOT a generic healthcare assistant.

Docvoxia is a multi-agent clinical reasoning system designed to transform doctor-patient conversations into safe, explainable, evidence-backed, FHIR-compliant healthcare records.

The project is optimized for:

* Microsoft Agents League Hackathon
* Reasoning Agents Category
* Best Use of IQ Tools
* Hack for Good

---

# Product Vision

Healthcare professionals spend substantial time documenting consultations and generating prescriptions.

Medication errors remain one of the most common preventable patient safety incidents.

Docvoxia reduces documentation burden while improving safety through:

* Real-time multilingual understanding
* Multi-agent reasoning
* Foundry IQ grounded retrieval
* Medication safety validation
* Human-in-the-loop governance
* Healthcare interoperability

---

# Core Architecture

Conversation Intelligence Layer

↓

Foundry IQ Knowledge Layer

↓

Clinical Reasoning Orchestrator

↓

Patient Intake Agent

Context Retrieval Agent

Diagnostic Reasoning Agent

Medication Safety Agent

Prescription Agent

Follow-Up Agent

Evidence Validation Agent

↓

FHIR Generator

↓

Human Review

↓

Hospital Integration

---

# Engineering Principles

## Patient Safety First

Every recommendation must pass validation.

Never generate a final prescription without:

* Allergy check
* Interaction check
* Contraindication check
* Human review

---

## Grounded Reasoning

No agent may generate unsupported clinical claims.

All reasoning must reference:

* Patient history
* Guidelines
* Drug references
* Hospital protocols
* Foundry IQ retrievals

---

## Explainability

Every output must contain:

reasoning_summary

confidence_score

evidence_sources

safety_flags

---

## Human Control

The doctor always remains the final decision maker.

AI recommendations are advisory.

Never bypass review workflows.

---

## FHIR Compliance

All healthcare outputs must conform to:

FHIR R4

SNOMED CT

ABDM-compatible structures

---

# Technology Stack

Language

Python 3.12

Backend

FastAPI

Agents

LangGraph

LLMs

Azure OpenAI GPT-4.1

GPT-4o

Knowledge

Azure AI Search

Foundry IQ

Database

PostgreSQL

Cache

Redis

Authentication

Microsoft Entra ID

Deployment

Docker

Azure Container Apps

Observability

OpenTelemetry

---

# Agent Responsibilities

Patient Intake Agent

Extract:

* demographics
* symptoms
* allergies
* medications
* history

---

Context Retrieval Agent

Retrieve:

* patient history
* previous encounters
* clinical guidelines
* hospital protocols
* drug references

---

Diagnostic Reasoning Agent

Generate:

* diagnostic hypotheses
* ranked possibilities
* confidence scores

---

Medication Safety Agent

Check:

* interactions
* allergies
* contraindications
* dosage issues

---

Prescription Agent

Generate:

* medication
* dosage
* frequency
* duration

---

Follow-Up Agent

Generate:

* instructions
* care plans
* escalation guidance

---

Evidence Validation Agent

Validate all outputs.

Attach evidence.

Attach citations.

---

# Code Quality

All code must:

* use typing
* include tests
* include docstrings
* include structured logging
* support observability

Avoid:

* hardcoded prompts
* giant service classes
* hidden reasoning

---

# Hackathon Priorities

When tradeoffs exist prioritize:

1. Reasoning
2. Foundry IQ integration
3. Medication safety
4. Explainability
5. FHIR generation
6. UI polish

The demo should clearly show:

Conversation

↓

Foundry IQ Retrieval

↓

Clinical Reasoning

↓

Safety Validation

↓

Evidence Validation

↓

FHIR Output

↓

Doctor Approval

This workflow is the primary judging narrative.
