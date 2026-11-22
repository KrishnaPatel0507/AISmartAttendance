# 🎓 SAPLS - Smart Attendance & Personalized Learning System

[![TypeScript](https://img.shields.io/badge/TypeScript-90.5%25-blue.svg)](https://github.com/Modi-Krish/SIH2026/search?l=typescript)
[![Python](https://img.shields.io/badge/Python-7.7%25-yellow.svg)](https://github.com/Modi-Krish/SIH2026/search?l=python)
[![GitHub stars](https://img.shields.io/github/stars/Modi-Krish/SIH2026?style=social)](https://github.com/Modi-Krish/SIH2026/stargazers)
[![GitHub contributors](https://img.shields.io/github/contributors/Modi-Krish/SIH2026)](https://github.com/Modi-Krish/SIH2026/graphs/contributors)

Welcome to **SAPLS**, a comprehensive project developed for **Smart India Hackathon (SIH) 2026** by [Modi Krish](https://github.com/Modi-Krish).

SAPLS is an advanced platform designed to automate attendance tracking using IoT edge devices and provide a personalized learning experience powered by Artificial Intelligence. 

## 🌟 Key Features
*   **Smart Attendance (IoT Edge)**: Hardware terminals communicate securely via MQTT (Mosquitto) to log attendance automatically.
*   **Personalized AI Learning**: Python-based AI service utilizing `pgvector` for intelligent student analytics and custom learning paths.
*   **Robust API**: Secure, highly scalable NestJS backend with JWT authentication and Supabase integration.
*   **Modern Web App**: Lightning-fast Next.js 15 frontend tailored with Tailwind CSS v4.

## 🏗️ Tech Stack

This repository is a monorepo managed using [Turborepo](https://turbo.build/repo) and `pnpm` workspaces.

*   **Frontend**: Next.js 15, React 19, Tailwind CSS v4 (`apps/web`)
*   **Backend**: NestJS 11, Supabase, Passport JWT, MQTT (`apps/api`)
*   **AI Service**: Python, FastAPI/Uvicorn (`apps/ai-service`)
*   **Database & ORM**: PostgreSQL with `pgvector` (via `@sapls/database`)
*   **Infrastructure**: Docker, Redis, Eclipse Mosquitto

## 📂 Project Structure

```text
SIH2026/
├── apps/
│   ├── web/           # Next.js 15 Frontend Application
│   ├── api/           # NestJS 11 Backend API Service
│   └── ai-service/    # Python FastAPI AI Analytics Service
├── packages/          # Shared internal packages (@sapls/database, @sapls/ui, etc.)
├── edge/              # MQTT and edge device configurations
└── docker-compose.yml # Local infrastructure setup
```

## 🚀 Getting Started

### Prerequisites
*   [Node.js](https://nodejs.org/en/) >= 20.0.0
*   [pnpm](https://pnpm.io/) >= 9.15.0
*   [Docker](https://www.docker.com/) & Docker Compose
*   Python 3.x (for the AI service)

### 1. Installation

Clone the repository and install all Node dependencies:
```bash
git clone https://github.com/Modi-Krish/SIH2026.git
cd SIH2026
pnpm install
```

### 2. Environment Setup
Copy the example environment variables and configure them:
```bash
cp .env.example .env
```
*(Ensure all database credentials, Supabase keys, and API secrets are correctly mapped).*

### 3. Start Local Infrastructure
Spin up PostgreSQL, Redis, and Mosquitto using Docker:
```bash
pnpm docker:up
```

### 4. Database Initialization
Generate your database schema, push to Postgres, and optionally seed it with test data:
```bash
pnpm db:generate
pnpm db:push
pnpm db:seed
```

### 5. Run the Application
Start the development servers for all apps (`web`, `api`, `ai-service`) concurrently:
```bash
pnpm dev
```

## 🛠️ Useful Commands

| Command | Description |
|---|---|
| `pnpm dev` | Start all development servers (`web`, `api`, `ai`) |
| `pnpm build` | Build all apps and packages for production |
| `pnpm lint` | Lint the entire codebase via ESLint |
| `pnpm format` | Format code using Prettier |
| `pnpm test` | Run unit tests (Jest) across the workspace |
| `pnpm db:studio`| Launch the Database Studio UI |
| `pnpm docker:up`| Start local Docker infrastructure |

## 👥 Contributors

*   **[Modi Krish](https://github.com/Modi-Krish)** - *Creator & Lead Developer*
