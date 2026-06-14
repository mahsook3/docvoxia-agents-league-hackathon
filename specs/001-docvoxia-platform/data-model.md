# Data Model

Feature: Docvoxia Clinical Reasoning Platform

---

# Entity: Patient

Represents a patient.

Fields:

* id (UUID)
* first_name
* last_name
* date_of_birth
* gender
* phone_number
* preferred_language
* consent_status
* created_at
* updated_at

Relationships:

Patient
1:N
Encounter

Patient
1:N
Allergy

Patient
1:N
Medication

---

# Entity: Encounter

Represents a consultation.

Fields:

* id
* patient_id
* doctor_id
* consultation_type
* transcript
* detected_languages
* encounter_date
* status

Relationships:

Encounter
1:N
Observation

Encounter
1:N
Condition

Encounter
1:N
ReasoningTrace

---

# Entity: Observation

FHIR Observation.

Fields:

* id
* encounter_id
* observation_type
* value
* confidence
* source_agent

Examples:

* Temperature
* Blood Pressure
* Weight

---

# Entity: Condition

FHIR Condition.

Fields:

* id
* encounter_id
* snomed_code
* diagnosis_name
* confidence
* evidence_summary

---

# Entity: Medication

Fields:

* id
* patient_id
* medication_name
* dosage
* frequency
* duration
* source

---

# Entity: MedicationRequest

FHIR MedicationRequest.

Fields:

* id
* encounter_id
* medication_name
* dosage
* route
* frequency
* duration
* safety_status

---

# Entity: Allergy

Fields:

* id
* patient_id
* allergen
* severity
* reaction

---

# Entity: ClinicalEvidence

Stores grounding data.

Fields:

* id
* encounter_id
* source_type
* source_name
* citation
* relevance_score

Examples:

* Foundry IQ
* Clinical Guideline
* Drug Reference

---

# Entity: ReasoningTrace

Stores explainability.

Fields:

* id
* encounter_id
* agent_name
* input_summary
* output_summary
* confidence_score
* execution_time

---

# Entity: SafetyValidation

Stores medication checks.

Fields:

* id
* encounter_id
* risk_level
* interaction_found
* contraindication_found
* allergy_conflict
* recommendations

Risk Levels:

* LOW
* MEDIUM
* HIGH
* CRITICAL

---

# Entity: ApprovalRecord

Stores doctor review.

Fields:

* id
* encounter_id
* reviewer_id
* decision
* comments
* reviewed_at

Decision:

* APPROVED
* REJECTED

---

# Entity: AuditLog

Stores compliance trail.

Fields:

* id
* user_id
* action
* entity_type
* entity_id
* timestamp
* metadata

All critical actions must generate audit logs.
