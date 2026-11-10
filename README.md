<div align="center">

# PathWise AI

**Intelligent Course Recommendation & Academic Path Planning System**

An AI-powered academic planning platform that helps students discover relevant courses, build structured learning roadmaps, identify skill gaps, and track progress.

</div>

## Overview

PathWise AI combines a React-based student experience with a FastAPI backend and MongoDB persistence. Its five core modules cover student profiles, course discovery, personalized recommendations, academic roadmaps, and skill-gap/progress analysis.

## Core modules

1. **Student profiles** — registration, authentication, onboarding, academic details, interests, skills, and study availability.
2. **Course catalog** — searchable courses, category and difficulty filters, and prerequisite readiness checks.
3. **Course recommendations** — explainable weighted scoring using career goals, skills, interests, skill gaps, prerequisites, and study feasibility.
4. **Academic roadmaps** — prerequisite-aware sequencing using a directed acyclic graph and topological sorting, with workload estimates.
5. **Skill gaps and progress** — career competency comparisons, gap prioritization, course status updates, and progress visualizations.

## Technology stack

| Layer | Technologies |
|---|---|
| Frontend | React, TypeScript, Vite, Tailwind CSS, Recharts, Axios |
| Backend | Python, FastAPI, Pydantic, Uvicorn |
| AI / recommendation logic | scikit-learn, pandas, NumPy, TF-IDF, weighted recommendation scoring |
| Planning algorithms | Directed acyclic graphs (DAGs), Kahn's topological sorting algorithm |
| Database | MongoDB, PyMongo |
| Testing | Pytest, Vitest |

## Project structure

```text
Path_Wise_Ai/
├── backend/
│   ├── app/
│   │   ├── api/          # API routes
│   │   ├── core/         # Configuration and security
│   │   ├── database/     # MongoDB connection
│   │   ├── schemas/      # Request/response schemas
│   │   └── services/     # Recommendation, roadmap, and domain logic
│   ├── scripts/          # Seed scripts
│   ├── tests/            # Backend tests
│   └── requirements.txt
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── contexts/
│   │   ├── pages/
│   │   ├── services/
│   │   └── types/
│   └── package.json
├── .env.example
└── README.md
```

## Getting started

### Prerequisites

- Python 3.10+ (use the version supported by the backend dependencies)
- Node.js and npm
- MongoDB running locally or a MongoDB connection string

### 1. Clone the repository

```bash
git clone https://github.com/ashis643/Path_Wise_Ai.git
cd Path_Wise_Ai
```

### 2. Configure the backend

```bash
cd backend
python -m venv venv
```

Activate the environment:

```bash
# Windows PowerShell
.\venv\Scripts\Activate.ps1

# macOS / Linux
source venv/bin/activate
```

Install dependencies and configure environment variables:

```bash
pip install -r requirements.txt
cp .env.example .env
```

On Windows, copy `.env.example` to `.env` manually if `cp` is unavailable. Update the MongoDB URL and replace the development secret with a strong, unique random secret. Never commit `.env`.

Start the API (from the `backend` directory):

```bash
uvicorn app.main:app --reload
```

### 3. Configure and start the frontend

In a second terminal:

```bash
cd frontend
npm install
npm run dev
```

Use the local URL printed by Vite. Check `frontend/package.json` for the available build and test scripts.

## Configuration and security

- Use `.env.example` as a template; create local `.env` files for actual credentials.
- Do not commit database credentials, JWT secrets, API keys, or production environment files.
- Change all development secrets before deployment and configure production CORS, database access, and token lifetimes appropriately.

## Testing

Backend tests are in `backend/tests/` and can be run from the backend directory with:

```bash
pytest
```

Frontend tests and build scripts are defined in `frontend/package.json`.

## Project status

This repository contains the application source, configuration templates, seed scripts, and tests. Deployment requires environment-specific configuration (especially MongoDB and the backend secret). Review and run the test suites in your environment before treating a deployment as production-ready.

## License

No license has been specified yet. Unless a license is added, all rights remain with the copyright holder; reuse and redistribution are not automatically granted.
