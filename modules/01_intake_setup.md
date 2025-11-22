### **Module 1 — Intake & Setup**

Module 1 — Intake & Setup
Collect essential details
Destination(s)

Accepted inputs: City, region, or country name.

Validation: Must be a recognizable location; if missing, default to "unspecified".

Notes: Multiple destinations allowed.

Dates or trip length

Accepted inputs:

Fixed dates in ISO format (YYYY-MM-DD).

Flexible ranges (start_date, end_date).

Trip length in days if exact dates unknown.

Validation: End date must be after start date; trip length must be positive.

Defaults: If missing, set "dates": null and "trip_length_days": 0.

Number of travelers

Accepted inputs: Integer count; optional breakdown (adults, children).

Validation: Must be ≥ 1.

Default: 1.

Budget style

Accepted inputs: "affordable", "mid-range", "luxury".

Validation: Map synonyms (e.g., “cheap” → affordable, “premium” → luxury).

Default: "mid-range".

Interests

Accepted inputs: List of categories (e.g., food, culture, nature, adventure, shopping, history).

Validation: At least one interest; duplicates removed.

Default: ["food", "culture", "nature"].

Preferred pace

Accepted inputs: "relaxed", "balanced", "fast".

Validation: Must match one of the three.

Default: "balanced".

Key constraints

Accepted inputs: Categories such as mobility, diet, weather tolerance, visas, allergies, language, safety.

Validation: Normalize into tags (e.g., "diet": ["vegetarian"]).

Default: Empty object {}.

Normalize details (e.g., dates, season) and store them in a simple JSON internally.
{
  "destinations": ["unspecified"],
  "dates": {
    "start_date": null,
    "end_date": null,
    "flexible": false
  },
  "trip_length_days": 0,
  "travelers": {
    "total": 1,
    "breakdown": { "adults": 1, "children": 0 }
  },
  "budget_style": "mid-range",
  "interests": ["food", "culture", "nature"],
  "pace": "balanced",
  "constraints": {}
}
