# Installation Guide

## Requirements

## Server

- Ubuntu Server
- Docker
- Docker Compose
- Git


## External Accounts

Required:

- GitHub Account
- Slack Workspace
- Google Cloud Account
- Groq Account


---

# Project Setup


Clone repository:

```bash
git clone git@github.com:Giovanni-088/AI-Enterprise-Knowledge-Assistant.git

Enter directory:

cd AI-Enterprise-Knowledge-Assistant
Environment Configuration

Copy example environment file:

cp .env.example .env

Edit variables:

nano .env
Docker Deployment

The project uses Docker Compose to maintain a reproducible deployment environment.

Start services:

docker compose up -d

Check status:

docker compose ps
Project Structure
AI-Enterprise-Knowledge-Assistant

├── docs
├── workflows
├── images
├── examples
├── docker-compose.yml
└── README.md
Current Status

Phase 00 completed.

Deployment services will be added in future phases.


---
