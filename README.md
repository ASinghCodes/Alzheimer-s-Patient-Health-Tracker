# Alzheimer's Patient Tracker

## Project Overview  
This project is a web-based tool designed to help track cognitive decline in Alzheimer's patients using standardized MMSE (Mini-Mental State Examination) scores. The app enables clinicians and caregivers to record, store, and visualize assessment data through a secure, FHIR-compliant system. It leverages both clinical standards and modern web technologies to support data-driven care decisions.

## Technologies Used  
- Frontend: React + Vite + TailwindCSS (In Progress)  
- Hosting: Vercel (Frontend), Railway (FHIR backend)  
- FHIR Server: HAPI FHIR (HL7 FHIR R4 standard)  
- Data Standards: LOINC-coded Observations  
- Visualization: Recharts  
- Security/Authentication: Firebase Auth, SMART on FHIR  
- Development Tools: Ngrok, GitHub  

## Project Objectives  
- Select and view patient profiles loaded from a FHIR server  
- Record MMSE test scores via an intuitive form (6 score categories, total 30 points)  
- Store MMSE data in FHIR-compliant Observations using LOINC codes  
- Retrieve and visualize a patient’s cognitive score history over time  
- Support secure access via Firebase and SMART on FHIR authentication  
- Build a foundation for future features like reminders and alerts  

## App Structure  
The app uses a 3-column responsive layout:

1. Left Panel: Patient selection (from FHIR server)  
2. Middle Panel: MMSE score input form  
3. Right Panel: Line chart of historical MMSE scores  

## MMSE Score Details  
Each MMSE score entry includes the following:

| Section                 | Range |
|-------------------------|-------|
| Orientation (Part 1)    | 0–5   |
| Orientation (Part 2)    | 0–5   |
| Registration            | 0–3   |
| Attention/Calculation   | 0–5   |
| Recall                  | 0–3   |
| Language                | 0–8   |
| **Total**               | **0–30** |

Each MMSE score is stored as a unique Observation in the FHIR backend, using LOINC codes for standardization.

## Features  
- Select patients by name or ID  
- Enter new MMSE assessments one at a time  
- Submit scores to a FHIR backend (HAPI FHIR)  
- Visualize score history via Recharts line chart  
- Secure access with Firebase Auth and SMART on FHIR  
- Supports multiple scores per patient  

## Experiments and Testing  
### Experiment 1: Score Entry and Retrieval  
- Enter scores for a test patient across several dates  
- Verify Observation creation via HAPI FHIR dashboard  
- Confirm correct rendering on score chart  

### Experiment 2: Graphing Logic  
- Use mock scores to simulate trends (improvement, decline, static)  
- Validate correct normalization and label placement  

### Experiment 3: Backend and Hosting  
- Evaluate performance and availability of Railway-hosted FHIR server  
- Test fallback behavior if FHIR server is unreachable  
- Transition away from Ngrok for long-term reliability  

## Implementation Details  
- `PatientSelector.jsx` – Loads patients via FHIR API  
- `MMSEForm.jsx` – Gathers input and composes score structure  
- `ScoreGraph.jsx` – Fetches and displays score history  
- `fhirUtils.js` – Handles FHIR Observation POST/GET  
- `auth.js` – Manages login via Firebase/SMART on FHIR  
- `App.jsx` – Coordinates routing, layout, and shared state  

## Learning Outcomes  
- Built a modular web app using modern frontend frameworks  
- Gained familiarity with healthcare data standards (FHIR, LOINC)  
- Applied clinical assessment logic to real-time data visualization  
- Integrated secure authentication using industry tools  
- Developed roadmap for long-term patient engagement features  

## Repository Access  
The full implementation—including score forms, FHIR logic, auth handlers, and charting—is stored in a private GitHub repository due to privacy and compliance concerns. Access is available upon request.
