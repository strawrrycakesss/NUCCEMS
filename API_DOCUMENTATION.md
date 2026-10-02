# NUCEMS API Documentation

Base URL: http://localhost:8000/api

| Method | Path | Purpose |
|---|---|---|
| GET | /health | API health |
| GET | /dashboard | Dashboard summary |
| GET | /incidents | List incidents |
| GET | /incidents/:id | Get incident |
| POST | /incidents | Create incident and calculate priority |
| PUT | /incidents/:id | Update incident |
| DELETE | /incidents/:id | Delete incident |
| GET | /incidents/search | Search/filter incidents |
| GET | /incidents/active | Active incidents |
| GET | /incidents/statistics | Incident statistics |
| GET | /incidents/:id/response-time | Response time |
| PATCH | /incidents/:id/status | Rule-based status change |
| GET | /responders | List responders |
| GET | /responders/:id | Get responder |
| POST | /responders | Create responder |
| PUT | /responders/:id | Update responder |
| DELETE | /responders/:id | Delete responder |
| GET | /responders/available | Available responders |
| GET | /responders/:id/workload | Responder workload |
| GET | /locations | List locations |
| GET | /locations/:id | Get location |
| POST | /locations | Create location |
| PUT | /locations/:id | Update location |
| DELETE | /locations/:id | Delete location |
| GET | /locations/:id/statistics | Location statistics |
| GET | /assignments | List assignments |
| GET | /assignments/:id | Get assignment |
| POST | /assignments | Assign responder |
| PUT | /assignments/:id | Update assignment |
| DELETE | /assignments/:id | Delete assignment |
| PATCH | /assignments/:id/status | Assignment status |
| GET | /assignments/:id/response-time | Assignment response time |
