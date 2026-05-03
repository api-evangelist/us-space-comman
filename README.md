# US Space Command

US Space Command (USSPACECOM) is a unified combatant command in the United States Department of Defense responsible for conducting operations in, from, and through space to deter conflict and, if necessary, defeat aggressors. The command provides space situational awareness (SSA) data through Space-Track.org, including the official satellite catalog and collision avoidance data.

**Space-Track.org:** https://www.space-track.org  
**APIs.yml:** https://raw.githubusercontent.com/api-evangelist/us-space-comman/refs/heads/main/apis.yml

---

## Scope

- **Type:** Contract
- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

Federal Government, Space, Space Situational Awareness, Satellite Tracking, Open Data

## Timestamps

- **Created:** 2024-12-03
- **Modified:** 2026-05-03

---

## APIs

### Space-Track.org REST API
Official USSPACECOM source for satellite tracking data, maintained by the 18th Space Defense Squadron. Provides orbital element sets, conjunction warnings, satellite catalog, and reentry predictions.

- **Base URL:** `https://www.space-track.org`
- **Auth:** Session cookie (authenticate via `POST /ajaxauth/login`) — free account required
- **OpenAPI:** [openapi/us-space-command-space-track-openapi.yml](openapi/us-space-command-space-track-openapi.yml)
- **Documentation:** https://www.space-track.org/documentation

Key endpoints:
- `GET /basicspacedata/query/class/gp/format/{format}` — Current orbital elements (GP/TLEs)
- `GET /basicspacedata/query/class/satcat/format/{format}` — Satellite catalog
- `GET /basicspacedata/query/class/cdm_public/format/{format}` — Conjunction warnings
- `GET /basicspacedata/query/class/decay/format/{format}` — Satellite decay data
- `GET /basicspacedata/query/class/boxscore/format/{format}` — Object counts by country

---

## Artifacts

| Type | Files |
|------|-------|
| OpenAPI Specs | [openapi/](openapi/) — 1 spec |
| Examples | [examples/](examples/) — 2 examples |
| Spectral Rules | [rules/us-space-comman-rules.yml](rules/us-space-comman-rules.yml) |
| Naftiko Capabilities | [capabilities/](capabilities/) — 1 workflow + 1 shared |
| JSON Schema | [json-schema/](json-schema/) — 1 schema |
| JSON Structure | [json-structure/](json-structure/) — 1 structure |
| JSON-LD | [json-ld/](json-ld/) — 1 context |
| Vocabulary | [vocabulary/](vocabulary/) — 1 vocabulary |

---

## Capabilities

### Shared Definitions
- [capabilities/shared/space-track.yaml](capabilities/shared/space-track.yaml) — Space-Track.org API (5 operations)

### Workflow Capabilities
- [capabilities/space-situational-awareness.yaml](capabilities/space-situational-awareness.yaml) — SSA workflow (6 MCP tools)
  - Orbital element search
  - Satellite catalog queries
  - Collision warning monitoring
  - Reentry prediction access
  - Catalog statistics

---

## Use Cases

- **Satellite Operations** — Query orbital elements and conjunction warnings for collision avoidance
- **Space Debris Monitoring** — Track fragmentation debris and defunct satellites
- **Orbital Mechanics Research** — Access historical ephemerides for analysis
- **Satellite Tracking** — Identify and locate specific satellites by name or NORAD ID
- **Space Traffic Management** — Monitor the space environment for congestion and collision risk
- **Launch Planning** — Assess orbital debris density for new launch trajectories

---

## Maintainers

**FN:** Kin Lane  
**Email:** kin@apievangelist.com
