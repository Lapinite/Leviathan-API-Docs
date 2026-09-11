# Public API guide

[API overview](README.md)

**Status: planned public contracts.** This repository currently provides documentation, not a running API implementation. No production base URL, route, scope, quota, webhook schema, or stable contract is asserted here.

## Authentication model

Authentication requirements must be documented per released interface. A Minecraft login token is not automatically a credential for a Leviathan API. Clients must not send Microsoft, Xbox, or Minecraft tokens to an unrelated integration. Public desktop clients must not embed confidential secrets.

The chosen grant, scopes, credential lifecycle, and revocation behavior remain unspecified until a public contract is released. Do not reuse the launcher application registration.

## Endpoint conventions

A released endpoint reference should specify its method, public path, authorization requirements, parameters, response schema, pagination, and side effects. No example route is supplied because it could be mistaken for an available service.

## Versioning

Public version selection, deprecation notice periods, and migration guarantees are not yet defined. A future reference should identify breaking changes and describe migration before clients rely on a new version.

## Rate limiting

No numeric quotas or response headers are currently promised. Clients should be designed to respect the released service's limits and retry guidance. Avoid unbounded retries and retrying operations with side effects unless the contract defines safe behavior.

## Errors

A future contract must separate validation failures, authentication failures, permission failures, throttling, and temporary service failures. Do not invent an error schema. User-facing messages and logs must exclude authorization headers, credentials, raw account data, and sensitive response bodies.

## Webhooks

Webhook delivery is planned. Event names, payloads, signing algorithms, signature headers, replay protection, retry policy, and delivery identifiers are not yet specified. Do not deploy a receiver that assumes verification behavior from these planning notes.

## SDK usage

No published SDK package or install command is specified here. See [Leviathan SDK](https://github.com/Lapinite/Leviathan-SDK) for the current status. A release must tie each example to an actual package version and supported API contract.

## Integrations

See [Leviathan Integrations](https://github.com/Lapinite/Leviathan-Integrations) for public integration areas. Each adapter must document which service owns authentication, the minimum permissions required, and how access can be revoked.

## Security

Never publish real credentials, Microsoft administrative identifiers, private endpoints, or unsanitized captures. Examples should use unmistakable placeholders and remain non-networked until a real public contract exists. Follow [SECURITY.md](SECURITY.md) for reporting.
