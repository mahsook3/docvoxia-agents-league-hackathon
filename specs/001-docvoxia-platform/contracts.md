# API Contracts

Base URL

/api/v1

---

# POST /conversation/analyze

Purpose:

Analyze consultation transcript.

Request

{
"transcript": "...",
"language": "hi-en"
}

Response

{
"encounter_id": "uuid",
"entities": [],
"detected_conditions": [],
"confidence": 0.94
}

---

# POST /reasoning/run

Purpose:

Execute reasoning workflow.

Request

{
"encounter_id": "uuid"
}

Response

{
"diagnoses": [],
"confidence": 0.91,
"reasoning_summary": "...",
"evidence_sources": []
}

---

# POST /safety/check

Purpose:

Run medication safety checks.

Request

{
"encounter_id": "uuid",
"medications": []
}

Response

{
"risk_level": "LOW",
"interaction_found": false,
"recommendations": []
}

---

# POST /prescription/generate

Purpose:

Generate draft prescription.

Request

{
"encounter_id": "uuid"
}

Response

{
"prescription": {},
"follow_up": {},
"confidence": 0.92
}

---

# POST /fhir/generate

Purpose:

Generate FHIR bundle.

Request

{
"encounter_id": "uuid"
}

Response

{
"bundle": {}
}

---

# POST /review/approve

Request

{
"encounter_id": "uuid",
"reviewer_id": "uuid",
"comments": "Approved"
}

Response

{
"status": "approved"
}

---

# POST /review/reject

Request

{
"encounter_id": "uuid",
"reviewer_id": "uuid",
"comments": "Needs review"
}

Response

{
"status": "rejected"
}

---

# GET /metrics

Response

{
"total_encounters": 100,
"approved_prescriptions": 95,
"average_processing_time": 12.3
}

---

# GET /health

Response

{
"status": "healthy"
}
