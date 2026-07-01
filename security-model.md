# Docker Probe Security Model

This document summarizes the security model for OpsHome Docker Probe examples.

These examples are public setup notes, not the full OpsHome NOC app or backend source code.

## Outbound-Only Connections

Docker Probe runs inside your private network and initiates outbound HTTPS connections to OpsHome Cloud.

OpsHome Cloud does not directly connect into your LAN. Private services stay inside your network.

## No Inbound Ports Required

You do not need to open inbound firewall rules or configure port forwarding for Docker Probe.

Private services do not need to be exposed with:

- Public IP addresses
- Router port forwarding
- Public reverse proxies
- Internet-facing NAS or Proxmox management panels

## Private Services Stay Private

Docker Probe checks services from inside your authorized network and reports supported status back to OpsHome Cloud.

Use this model for private HTTP, HTTPS, and TCP services such as:

- NAS dashboards
- Proxmox VE interfaces and services
- Docker-hosted applications
- Home automation dashboards
- Internal APIs
- Databases or TCP services that should remain LAN-only

## Token Handling

The Docker Compose example uses placeholder values only.

Do not publish:

- Bootstrap tokens
- Probe IDs tied to your account
- API credentials
- Synology DSM passwords
- Proxmox API tokens
- Private hostnames or internal IP maps

Generate real configuration from OpsHome NOC and keep it private.

## Links

- Docker Probe install guide: https://docs.opshome.run/docs/docker-probe/install/
- Docker Probe security model: https://docs.opshome.run/docs/docker-probe/security-model/
- OpsHome NOC: https://app.opshome.run/

