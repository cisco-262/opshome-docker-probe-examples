# Troubleshooting Docker Probe and Private Monitors

These notes cover common setup issues for OpsHome Docker Probe examples.

This is public troubleshooting documentation, not the full OpsHome NOC app or backend source code.

## Docker Probe Offline

Check:

- The container is running
- The container can resolve DNS
- The container can reach OpsHome Cloud over outbound HTTPS
- The state volume still exists
- The probe was not deleted in OpsHome NOC
- The account has available Docker Probe allowance

Useful commands:

```bash
docker ps
docker logs opshome-probe
docker compose logs -f opshome-probe
```

## Token Invalid

A bootstrap token may fail if:

- It was copied incorrectly
- It expired
- It was already used
- The probe state volume was deleted and the probe identity no longer matches

Generate a fresh Docker Probe configuration from OpsHome NOC when needed.

Do not publish bootstrap tokens in GitHub issues, screenshots, Docker Hub descriptions, or public examples.

## Network Unreachable

If Docker Probe is online but cannot reach a private service, check:

- The target IP, hostname, scheme, and port
- Docker network mode and container routing
- Host firewall rules
- VLAN or subnet routing
- Local DNS resolution from inside the Docker network
- Whether the service binds only to `127.0.0.1`

Test from a shell in the same network context when possible.

## Private Monitor Failed

A failed Private Monitor does not always mean the Docker Probe is offline.

If Docker Probe is offline, OpsHome cannot confirm dependent private monitor status.

If Docker Probe is online but the monitor fails, check:

- Target service health
- Correct HTTP, HTTPS, or TCP scheme
- Port availability
- DNS or local hostname resolution
- Firewall and routing path
- Certificate behavior for HTTPS targets

## Docker Container Event Timeline Issues

If container events do not appear as expected, check:

- The Docker host is connected as a supported Asset Source
- The probe can access supported Docker metadata
- The container actually restarted, recovered, exited, entered an abnormal state, or was OOM-killed during the visible timeline window

## Links

- Troubleshoot Docker Probe offline: https://docs.opshome.run/docs/troubleshooting/docker-probe-offline/
- Troubleshoot failed private monitors: https://docs.opshome.run/docs/troubleshooting/private-monitor-failed/
- Docker Probe install guide: https://docs.opshome.run/docs/docker-probe/install/
- OpsHome NOC: https://app.opshome.run/

