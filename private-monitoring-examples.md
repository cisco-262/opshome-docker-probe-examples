# Private Monitoring Examples

These examples show the types of private targets Docker Probe can monitor from inside an authorized homelab network.

This file is public setup documentation. It is not the full OpsHome NOC app or backend source code.

## HTTP Private Monitor

```text
http://192.168.1.20:8080
http://homeassistant.local:8123
```

Use HTTP monitors for internal dashboards, APIs, and services that do not require TLS inside your LAN.

## HTTPS Private Monitor

```text
https://nas.local:5001
https://proxmox.local:8006
```

Use HTTPS monitors for NAS panels, Proxmox dashboards, and internal web services using TLS.

## TCP Private Monitor

```text
tcp://192.168.1.10:5432
tcp://192.168.1.30:22
```

Use TCP monitors for ports where a connection check is enough.

## Asset Source Examples

Docker Probe can also support Asset Sources for:

- Synology
- Proxmox
- Linux hosts
- Docker hosts

Asset Sources help OpsHome NOC organize infrastructure health beyond a flat uptime monitor list.

## Docker Container Event Timelines

For Docker hosts, OpsHome NOC can help review container events such as:

- Restarts
- Recoveries
- Abnormal states
- Exits
- Recreated containers
- OOM kills

## Links

- Private Monitoring: https://app.opshome.run/private-monitoring/
- Create private HTTP, HTTPS, and TCP monitors: https://docs.opshome.run/docs/private-monitors/http-https-tcp/
- Docker Container Monitoring: https://app.opshome.run/docker-container-monitoring/

