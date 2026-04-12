# ScanBIM MCP

**The AI Hub for AEC** — Unified MCP server connecting Revit, Navisworks, ACC, Twinmotion, and 50+ 3D formats via Autodesk Platform Services.

[![Live](https://img.shields.io/badge/status-live-brightgreen)](https://scanbim-mcp.itmartin24.workers.dev/)
[![MCP](https://img.shields.io/badge/protocol-MCP%202024--11--05-blue)](https://modelcontextprotocol.io)

## Overview

ScanBIM MCP is the central coordination hub for the ScanBIM Labs AEC MCP ecosystem. It provides 11 tools for model management, clash detection with D1-backed VDC rules, ACC issue/RFI management, and 3D viewer integration.

## Tools (11)

| Tool | Description |
|------|-------------|
| `upload_model` | Upload 3D models (Revit, IFC, point clouds, 50+ formats) |
| `detect_clashes` | VDC clash detection with D1 rules database |
| `get_viewer_link` | Generate ScanBIM viewer URL + QR code |
| `list_models` | List all uploaded models |
| `get_model_metadata` | Get APS translation status and metadata |
| `get_supported_formats` | List supported file formats by tier |
| `acc_list_projects` | List ACC/BIM 360 projects |
| `acc_create_issue` | Create ACC issues |
| `acc_list_issues` | List/filter ACC issues |
| `acc_create_rfi` | Create ACC RFIs |
| `acc_list_rfis` | List/filter ACC RFIs |

## Endpoints

| Path | Method | Description |
|------|--------|-------------|
| `/mcp` | POST | MCP JSON-RPC endpoint |
| `/info` | GET | Server info |
| `/health` | GET | Health check |

## Quick Start

```json
{
  "mcpServers": {
    "scanbim": {
      "url": "https://scanbim-mcp.itmartin24.workers.dev/mcp"
    }
  }
}
```

## Architecture

- **Runtime**: Cloudflare Workers
- **Auth**: Autodesk Platform Services (APS) OAuth2
- **Database**: Cloudflare D1 (VDC rules + usage logging)
- **Cache**: Cloudflare KV (token caching)

## Part of the ScanBIM Labs AEC MCP Ecosystem

| Server | Tools | Status |
|--------|-------|--------|
| [scanbim-mcp](https://github.com/ScanBIM-Labs/scanbim-mcp) | 11 | Live |
| [revit-mcp](https://github.com/ScanBIM-Labs/revit-mcp) | 8 | Live |
| [acc-mcp](https://github.com/ScanBIM-Labs/acc-mcp) | 9 | Live |
| [navisworks-mcp](https://github.com/ScanBIM-Labs/navisworks-mcp) | 5 | Live |
| [twinmotion-mcp](https://github.com/ScanBIM-Labs/twinmotion-mcp) | 5 | Live |

## License

MIT — ScanBIM Labs LLC
