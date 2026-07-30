# Kyo

Kyo (kyocare.com) is a US provider of Applied Behavior Analysis (ABA) therapy for autistic children and young adults, delivering in-home, in-school and center-based care across 20+ locations with in-network coverage from major insurers.

Kyo operates a client-facing digital surface — the Kyo Care portal (portal.kyocare.com) and mobile app — for scheduling, session notes, progress tracking and family communication.

## API surface

Kyo publishes **no public developer program**: no documentation, no OpenAPI, no SDKs, no sandbox and no open registration. Two API hosts are nonetheless observable:

- **`api.attain.kyocare.com`** — the "Attain" platform API backing the Kyo Care portal and app. It serves live [OpenID Connect discovery](https://api.attain.kyocare.com/.well-known/openid-configuration) and [RFC 8414 authorization-server metadata](https://api.attain.kyocare.com/.well-known/oauth-authorization-server), advertising `authorization_code` (PKCE S256) and `client_credentials` grants over AWS Cognito, with `openid` and `email` scopes.
- **`api.kyocare.com`** — a private Workato-managed partner gateway (Envoy). Every path returns `401 {"error":"access to this API has been disallowed"}`.

## Artifacts

| Artifact | Path | Method |
|---|---|---|
| Well-Known index + raw docs | `well-known/` | searched |
| Authentication profile | `authentication/kyocare-authentication.yml` | searched |
| OAuth scopes | `scopes/kyocare-scopes.yml` | searched |
| Conformance | `conformance/kyocare-conformance.yml` | searched |
| Conventions | `conventions/kyocare-conventions.yml` | derived |
| Domain security | `security/kyocare-domain-security.yml` | probed |
| llms.txt | `llms/kyocare-llms.txt` | generated |

No MCP server, Agent Skill, CLI, SDK, changelog, status page, vulnerability-disclosure program or trust center was found published by Kyo.

Backed by: norwest-venture-partners — https://kyocare.com
