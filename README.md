# OpsHome NOC Docker Probe Examples

This repository contains public examples and setup notes for OpsHome Docker Probe.

It is not the full source code of the OpsHome NOC iOS app, OpsHome Cloud backend, or production Docker Probe service. Use these files as deployment references, security notes, and troubleshooting examples for private monitoring in homelab environments.

## What OpsHome NOC Is

OpsHome NOC is an iPhone-first Network Operations Center view for homelab operators. It helps you review public monitors, Private Monitors, Docker Probe status, Asset Sources, alerts, Docker container event timelines, and infrastructure health from one place.

## What Docker Probe Does

Docker Probe runs inside your private network and connects outbound to OpsHome Cloud over HTTPS. It lets OpsHome NOC monitor private services without requiring inbound port forwarding or exposing private dashboards to the public internet.

Docker Probe can support:

- Private Monitors for HTTP, HTTPS, and TCP targets
- Asset Sources for Synology, Proxmox, Linux hosts, and Docker hosts
- Docker container event timelines for restarts, recoveries, abnormal states, exits, recreations, and OOM kills

## Example Files

- `docker-compose.yml`: minimal Docker Compose example using placeholder values
- `security-model.md`: outbound-only connection model and private network boundaries
- `private-monitoring-examples.md`: example private HTTP, HTTPS, and TCP monitor targets
- `troubleshooting.md`: common Docker Probe and Private Monitor failures
- `CHANGELOG.md`: examples repository changelog

## Important

Do not commit real bootstrap tokens, probe IDs, user IDs, credentials, NAS passwords, Proxmox tokens, or private hostnames to a public repository.

Generate the actual Docker Probe configuration from the OpsHome NOC app.

## Links

- OpsHome NOC: https://app.opshome.run/
- Docker Probe overview: https://app.opshome.run/docker-probe/
- Private Monitoring: https://app.opshome.run/private-monitoring/
- Docker Container Monitoring: https://app.opshome.run/docker-container-monitoring/
- Docker Probe install guide: https://docs.opshome.run/docs/docker-probe/install/
- Docker Probe security model: https://docs.opshome.run/docs/docker-probe/security-model/
- Docker Hub image: https://hub.docker.com/r/opshomenoc/opshome-noc
- App Store: https://apps.apple.com/us/app/opshome-noc/id6763890679

