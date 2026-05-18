# HailBytes API Documentation

> Official API and MCP server documentation for **HailBytes ASM** (Attack Surface Management) and **HailBytes SAT** (Security Awareness Training).

[![License: MPL 2.0](https://img.shields.io/badge/License-MPL_2.0-brightgreen.svg)](https://opensource.org/licenses/MPL-2.0)
[![OpenAPI 3.1](https://img.shields.io/badge/OpenAPI-3.1-blue.svg)](https://spec.openapis.org/oas/v3.1.0)
[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-purple.svg)](https://modelcontextprotocol.io)

---

## Overview

This repository contains the complete API reference, OpenAPI 3.1 specifications, MCP server definitions, integration guides, and SDK examples for the HailBytes platform.

- **HailBytes ASM** — continuous attack surface discovery, asset inventory, and vulnerability correlation for enterprise security teams and MSSPs.
- **HailBytes SAT** — automated security awareness training delivery, phishing simulation, and compliance reporting.

📖 **Full documentation:** [hailbytes.com/docs](https://hailbytes.com/docs)

---

## Contents

| Path | Description |
|------|-------------|
| `asm/openapi.yaml` | OpenAPI 3.1 spec for the ASM REST API |
| `sat/openapi.yaml` | OpenAPI 3.1 spec for the SAT REST API |
| `mcp/` | MCP server definitions for ASM and SAT tool integrations |
| `guides/` | Integration guides (SIEM, ticketing, MSSP multi-tenant) |
| `sdk/` | SDK examples (Python, Go, TypeScript) |
| `postman/` | Postman collections for both APIs |

---

## Quick Start

### Authentication

All HailBytes APIs use Bearer token authentication:

```http
Authorization: Bearer <your-api-key>
```

API keys are provisioned from the [HailBytes dashboard](https://hailbytes.com/docs/authentication).

### ASM — List Assets

```bash
curl -X GET "https://api.hailbytes.com/asm/v1/assets" \
  -H "Authorization: Bearer <your-api-key>" \
  -H "Content-Type: application/json"
```

### SAT — Enroll a User

```bash
curl -X POST "https://api.hailbytes.com/sat/v1/users" \
  -H "Authorization: Bearer <your-api-key>" \
  -H "Content-Type: application/json" \
  -d '{"email": "user@example.com", "group_id": "grp_abc123"}'
```

---

## MCP Server

HailBytes exposes a [Model Context Protocol (MCP)](https://modelcontextprotocol.io) server, enabling AI assistants and agentic workflows to query your attack surface, trigger scans, and manage training campaigns programmatically.

```json
{
  "mcpServers": {
    "hailbytes": {
      "url": "https://mcp.hailbytes.com/sse",
      "headers": {
        "Authorization": "Bearer <your-api-key>"
      }
    }
  }
}
```

See [`mcp/README.md`](mcp/README.md) for full tool definitions and usage examples.

---

## MSSP & Multi-Tenant

HailBytes supports MSSP deployments with tenant isolation, delegated API keys, and per-tenant reporting. See [`guides/mssp-multitenancy.md`](guides/mssp-multitenancy.md).

---

## Support

- 📧 [support@hailbytes.com](mailto:support@hailbytes.com)
- 📖 [hailbytes.com/docs](https://hailbytes.com/docs)
- 🔒 Security issues: see [SECURITY.md](SECURITY.md)

---

## License

Mozilla Public License 2.0 — see [LICENSE](LICENSE) for details.
