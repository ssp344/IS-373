# IS 373 - Secure DigitalOcean Deployment

## Project Overview
This project demonstrates Docker, DigitalOcean, GitHub Actions, and secure SSH deployment.

## GitHub Repository
https://github.com/ssp344/IS-373

## Production Website
https://shiv-is373.xyz

## QA Website
https://qa.shiv-is373.xyz

Note: QA and production deployment verification is in progress.

## Technology Used
- DigitalOcean Ubuntu 24.04 Droplet
- Docker and Docker Compose
- GitHub Actions
- GitHub Container Registry
- Traefik reverse proxy
- SSH key authentication

## SSH Security
Created a non-root user named deploy.

Configured:
- PermitRootLogin no
- PasswordAuthentication no
- KbdInteractiveAuthentication no
- PubkeyAuthentication yes

Verified successful SSH-key login.

## CI/CD
GitHub Actions validates the website, builds a Docker image, and publishes it to GitHub Container Registry.

Successful workflow:
https://github.com/ssp344/IS-373/actions/runs/37818179080

Automatic deployment configuration is being completed.

## Deployment
The DigitalOcean Droplet runs Docker containers and Traefik for HTTPS routing.

## Test Evidence
- SSH security settings verified in Terminal.
- Docker containers confirmed running.
- GitHub Actions build completed successfully.
- QA and production promotion testing pending.
