# IS 373 - Secure DigitalOcean Deployment

## Project Overview
This project demonstrates Docker, DigitalOcean, GitHub Actions, secure SSH, and automatic deployment to QA and production.

## GitHub Repository
https://github.com/ssp344/IS-373

## Production Website
https://shiv-is373.xyz

## QA Website
https://qa.shiv-is373.xyz

Both websites are working over HTTPS.

## Technology Used
- DigitalOcean Ubuntu 24.04 Droplet
- Docker and Docker Compose
- GitHub Actions
- GitHub Container Registry (GHCR)
- Traefik reverse proxy
- SSH key authentication

## SSH Security
Created a non-root user named `deploy`.

Configured:
- PermitRootLogin no
- PasswordAuthentication no
- KbdInteractiveAuthentication no
- PubkeyAuthentication yes

Verified successful SSH-key login.

## CI/CD
GitHub Actions automatically:
1. Validates the website.
2. Builds the Docker image.
3. Publishes the image to GitHub Container Registry.
4. Deploys the updated website to DigitalOcean.

Successful workflow:
https://github.com/ssp344/IS-373/actions/runs/38775502508

Docker image:
`ghcr.io/ssp344/is-373:production`

## Deployment
The DigitalOcean Droplet runs Docker containers and Traefik for HTTPS routing.

QA changes are tested first and promoted to production through a pull request.

Successful QA-to-production pull request:
https://github.com/ssp344/IS-373/pull/2

## Test Evidence
- SSH security settings verified in Terminal.
- Docker containers confirmed running.
- GitHub Actions build and deployment completed successfully.
- QA website tested successfully.
- QA-to-production pull request merged successfully.
- Production updated from Version 1.0 to Version 1.2.
- Production deployment confirmed working over HTTPS.

## Final Result
Both QA and production websites are working. Version 1.2 was successfully promoted from QA to production using GitHub Actions and DigitalOcean.
