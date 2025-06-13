# GitHub Actions Docker Python Example

This repository demonstrates GitHub Actions workflows for building and deploying Docker Python applications.

## Features

- **Docker Build Workflow**: Automatically builds and pushes Python Docker images to GitHub Container Registry
- **Sample Python App**: Flask web application demonstrating containerization
- **CI/CD Pipeline**: Automated builds on push and pull requests

## Workflows

### Docker Build (`docker-build.yml`)
- Triggers on push/PR to main branch
- Builds Docker image from Python Flask app
- Pushes to GitHub Container Registry (ghcr.io)
- Uses Docker BuildKit caching for performance
- Tags images with branch, PR, SHA, and latest

### Simple CI (`simple-ci.yml`)
- Basic GitHub Actions workflow example
- Runs on push/PR to main branch

## Sample Application

The repository includes a sample Flask web application:
- `app.py` - Simple Flask web server
- `Dockerfile` - Multi-stage Python container build
- `requirements.txt` - Python dependencies

## Usage

1. Fork or clone this repository
2. Push changes to trigger the Docker build workflow
3. Images are automatically pushed to GitHub Container Registry
4. Access your built images at `ghcr.io/your-username/gh-action`

## Local Development

Build the Docker image locally:
```bash
docker build -t python-app .
docker run -p 8000:8000 python-app
```

Access the app at http://localhost:8000