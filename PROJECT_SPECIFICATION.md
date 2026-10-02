# NUCEMS Complete Project Specification

## Purpose

NUCEMS is a campus emergency management platform. It converts emergency reports into actionable response information.

## Data relationship

User → Incident → Assignment → Responder
                    ↓
                 Location

## Users

Fields: name, email, role, department, phone, active, timestamps.
Roles: ADMIN, SAFETY_OFFICER, STAFF, REPORTER.

## Incidents

Fields: incidentCode, title, description, type, severity, locationId, reportedBy, status, priorityScore, reportedAt, resolvedAt, timestamps.
Types: MEDICAL, FIRE, SECURITY, ACCIDENT, NATURAL_DISASTER, OTHER.
Severity: LOW, MEDIUM, HIGH, CRITICAL.
Status: REPORTED, ASSIGNED, RESPONDING, RESOLVED, CANCELLED.

## Responders

Fields: name, responderType, phone, department, status, skills, location, timestamps.
Status: AVAILABLE, BUSY, OFF_DUTY.

## Locations

Fields: name, building, floor, room, capacity, riskLevel, active, timestamps.
Risk: LOW, MEDIUM, HIGH.

## Assignments

Fields: incidentId, responderId, assignedBy, assignedAt, acceptedAt, arrivedAt, completedAt, status, notes, timestamps.
Status: ASSIGNED, ACCEPTED, ARRIVED, COMPLETED, CANCELLED.

## Processing examples

Priority:
severityValue × 2 + locationRiskValue

Severity values:
LOW=1, MEDIUM=2, HIGH=3, CRITICAL=4

Location risk:
LOW=1, MEDIUM=2, HIGH=3

Priority classification:
1–4 LOW
5–7 MEDIUM
8–10 HIGH
11+ CRITICAL

Response time:
arrivedAt - reportedAt

Valid incident flow:
REPORTED → ASSIGNED → RESPONDING → RESOLVED

Allowed cancellation:
REPORTED → CANCELLED
ASSIGNED → CANCELLED

Invalid example:
RESOLVED → RESPONDING

## UI

Dashboard cards:
Total Incidents, Active Incidents, Critical Incidents, Available Responders, Average Response Time.

Incident list:
search, type filter, severity filter, status filter, location filter, date filter, sort.

Incident details:
timeline, priority, assignment, response time, status.

Forms:
React Hook Form + Zod with per-field messages.

## Presentation scenario

1. Open landing page.
2. Open dashboard.
3. Create a medical emergency.
4. Trigger and show validation.
5. Submit valid incident.
6. Show calculated priority.
7. Assign available responder.
8. Change status to RESPONDING.
9. Record arrival.
10. Resolve incident.
11. Show response-time calculation.
12. Show updated statistics.
13. Demonstrate a not-found incident.

