# Model Context Protocol (MCP) Environment

This repository contains configurations and workflows for a comprehensive AI automation environment using n8n, Ollama, and other tools.

## Project Structure

The project is organized into several key directories:

| Directory | Purpose |
|-----------|---------|
| `/n8n-data` | Contains n8n configuration, database files, and binary data |
| `/n8n-data/postgres` | PostgreSQL database files used by n8n |
| `/n8n-data/ollama` | Ollama model files and configurations |
| `/ngrok-v3` | ngrok tunnel service for exposing local services |
| `/puppeteer` | Browser automation screenshots and resources |
| `/workflow` | JSON workflow definitions |
| `/AI Agents` | Collection of n8n workflow templates for different AI agent types |

## Docker Compose Configuration

This project uses multiple Docker Compose configurations for different components and hardware:

### Main Docker Compose (`/docker-compose.yml`)

Primary configuration running n8n with PostgreSQL database on a Raspberry Pi 4.

| Service | Image | Purpose | Hardware |
|---------|-------|---------|----------|
| n8n | n8nio/n8n:latest | Workflow automation platform | Raspberry Pi 4 |
| postgres | postgres:15-alpine | Database for n8n | Raspberry Pi 4 |

### AI Agents Docker Compose (`/AI Agents/docker-compose.yml`)

Configuration for running Ollama models on Intel machine.

| Service | Image | Purpose | Hardware |
|---------|-------|---------|----------|
| Ollama | ollama:latest | Large language model hosting | Intel Machine |

## Hardware Configuration

The system components are distributed across different hardware:

| Component | Hardware | Notes |
|-----------|----------|-------|
| n8n Workflows | Raspberry Pi 4 | Main workflow automation and agent orchestration |
| Ollama Models | Intel Machine | More powerful hardware for running LLMs |
| ngrok | Either machine | Exposes local services to the internet |

## Planned Expansion

We're planning to add a new folder for Affine software to enhance the capabilities of our system:

| Upcoming Addition | Purpose |
|------------------|---------|
| `/affine` | Knowledge management and collaboration software |

## Usage Instructions

1. Start n8n and PostgreSQL on the Raspberry Pi 4 using the main Docker Compose file:
   ```
   docker-compose up -d
   ```

2. Start Ollama on the Intel machine using the AI Agents Docker Compose file:
   ```
   cd AI\ Agents
   docker-compose up -d
   ```

3. Access the n8n interface at http://localhost:5678 or via the ngrok URL

## Available Workflows

The project includes numerous pre-built AI agent workflows for various purposes:

- Content creation and social media management
- Customer service automation
- Research and information retrieval
- CRM and employee management
- Voice and text processing

These workflows can be imported into n8n from the `/AI Agents/n8n` directory.
