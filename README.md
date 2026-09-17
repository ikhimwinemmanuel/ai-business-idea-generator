# MediNotes AI

A full-stack healthcare consultation assistant that turns a doctor's consultation notes into:

- a structured summary for medical records
- clear follow-up actions for the doctor
- a patient-friendly email draft

The project started as a simple LLM web application and was progressively expanded with authentication, paid access, streaming responses, structured form input, backend validation, Docker containerisation and AWS deployment.

> **Important:** MediNotes AI is a portfolio and learning project. It is not intended for use with real patient information or as a medical decision-making system.

---

## What the Application Does

A signed-in user can enter:

- Patient name
- Date of visit
- Consultation notes

The application sends the information to a FastAPI backend, which validates the request and sends a structured prompt to the OpenAI API.

The response is streamed back to the browser and displayed in three sections:

1. **Summary of visit for the doctor's records**
2. **Next steps for the doctor**
3. **Draft of email to patient in patient-friendly language**

The application also includes user authentication and subscription-based access.

---

## Tech Stack

### Frontend

- Next.js
- React
- TypeScript
- Tailwind CSS
- React Markdown
- React DatePicker

### Backend

- Python
- FastAPI
- Pydantic
- OpenAI API
- Server-Sent Events

### Authentication and Billing

- Clerk authentication
- JWT-based API authentication
- Clerk subscriptions
- Protected premium access

### Deployment and Infrastructure

- Docker
- Amazon ECR
- AWS Lambda
- AWS Lambda Web Adapter
- Lambda Function URLs
- Amazon CloudWatch
- Vercel during the earlier development stages

---

## How It Works

```text
User
  |
  v
Next.js Consultation Form
  |
  | Patient name
  | Visit date
  | Consultation notes
  | Clerk JWT
  v
FastAPI Backend
  |
  | Pydantic validation
  | Authentication check
  | Prompt construction
  v
OpenAI API
  |
  | Streaming response
  v
FastAPI
  |
  | Server-Sent Events
  v
Next.js Interface
  |
  v
Medical summary
Doctor action items
Patient email draft