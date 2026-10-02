# NUCEMS — National University Campus Emergency Management System

A CTADWEBL Final Project concept and starter implementation for a full-stack campus emergency management system.

## Project concept

NUCEMS manages campus emergency incidents, responders, locations, users, and assignments. It processes data to calculate priority, check responder availability, prevent conflicting assignments, enforce incident status transitions, calculate response time, and generate statistics.

## Rubric coverage

- React + Vite + TypeScript
- Tailwind CSS
- React Router
- React Hook Form + Zod
- Axios configured through one API instance
- Node.js + Express
- MongoDB Atlas + Mongoose
- Git/GitHub ready
- 5 related MongoDB collections
- 32 planned REST endpoints
- 12 React routes/pages
- Processing/business logic services
- Loading, error, empty, success, and delete-confirmation UI patterns
- Seed data
- Request logger, JSON 404 handler, and error middleware

## Five collections

1. users
2. incidents
3. responders
4. locations
5. assignments

## Processing logic

1. Priority score: severity × 2 + location risk.
2. Available responder matching.
3. Double-assignment prevention.
4. Controlled incident status transitions.
5. Response-time calculation.
6. Incident statistics.
7. Location statistics.
8. Search/filter processing.

## Planned API endpoints

### General
GET /api/health
GET /api/dashboard

### Incidents
GET /api/incidents
GET /api/incidents/:id
POST /api/incidents
PUT /api/incidents/:id
DELETE /api/incidents/:id
GET /api/incidents/search
GET /api/incidents/active
GET /api/incidents/statistics
GET /api/incidents/:id/response-time
PATCH /api/incidents/:id/status

### Responders
GET /api/responders
GET /api/responders/:id
POST /api/responders
PUT /api/responders/:id
DELETE /api/responders/:id
GET /api/responders/available
GET /api/responders/:id/workload

### Locations
GET /api/locations
GET /api/locations/:id
POST /api/locations
PUT /api/locations/:id
DELETE /api/locations/:id
GET /api/locations/:id/statistics

### Assignments
GET /api/assignments
GET /api/assignments/:id
POST /api/assignments
PUT /api/assignments/:id
DELETE /api/assignments/:id
PATCH /api/assignments/:id/status
GET /api/assignments/:id/response-time

## React pages

1. Landing
2. Dashboard
3. Incidents
4. Report Emergency
5. Incident Details
6. Edit Incident
7. Responders
8. Responder Details
9. Locations
10. Location Details
11. Assignments
12. Statistics

## Folder structure

client/
  src/components
  src/layouts
  src/pages
  src/hooks
  src/services
  src/schemas
  src/types

server/
  src/config
  src/models
  src/routes
  src/controllers
  src/middleware
  src/services
  src/seed

## Setup

### Server

1. Copy `.env.example` to `.env`.
2. Put your MongoDB Atlas URI in `MONGO_URI`.
3. Run `npm install`.
4. Run `npm run seed`.
5. Run `npm run dev`.

### Client

1. Copy `.env.example` to `.env`.
2. Run `npm install`.
3. Run `npm run dev`.

The client expects the API at `http://localhost:8000/api`.

## Important

This ZIP is a structured starter/reference implementation. Replace sample names, campus details, and seed data with your group's own original project decisions. Authentication, payments, deployment, and file uploads are not required by the supplied rubric.

## Defense flow

Report Emergency → validation → priority calculation → responder assignment → status transition → arrival → resolution → response time → dashboard statistics.

## Suggested UI

Professional campus emergency dashboard with navy/blue primary UI, neutral backgrounds, and red/amber reserved for critical/warning states. Use responsive cards, tables, badges, timelines, filters, confirmation dialogs, and clear loading/error/empty states.
