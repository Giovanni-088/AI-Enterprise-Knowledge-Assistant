# Monitoring

## Overview

The project includes basic monitoring through Docker logs and service health validation.

Each service operates independently, simplifying troubleshooting and future scalability.

---

## Services

Current services:

- n8n
- docx-parser

---

## Docker Health

Container status can be verified using:

```bash
docker ps
```

View logs:

```bash
docker logs n8n

docker logs docx-parser
```

---

## Network Validation

Both services communicate through the internal Docker network.

Verify network:

```bash
docker network inspect ai-network
```

Expected communication:

n8n

↓

docx-parser

↓

JSON Response

---

## Common Issues

### DOCX parser unavailable

Symptoms:

- HTTP Request node returns connection error.

Possible causes:

- Container stopped
- Network disconnected
- Incorrect service name

---

### Invalid document

Symptoms:

- Parser returns extraction error.

Possible causes:

- Corrupted DOCX
- Unsupported file
- Empty document

---

### Google Drive retrieval failure

Symptoms:

- No documents returned.

Possible causes:

- Missing permissions
- Incorrect File ID
- Deleted file

---

## Future Monitoring

Future versions may include:

- Prometheus
- Grafana
- Health endpoints
- Metrics collection
- Centralized logging
