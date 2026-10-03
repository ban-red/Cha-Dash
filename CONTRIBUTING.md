# Contributing to Cha Dash

Thanks for your interest! Cha Dash is in its **planning phase**: there's no application code yet. The research and product plan live in [`docs/`](docs/).

## How to help right now

- **Read the plan and push back.** Start with [docs/plan/01-vision.md](docs/plan/01-vision.md). Open an issue if something is wrong, missing, or could be better.
- **Share your homelab.** Which platforms, services and pain points should Cha Dash handle? Real setups shape what gets built first.
- **Design feedback.** Visual and interaction design is a core part of this project. Critique and ideas are very welcome.

## Code contributions

We'll start accepting code once the M0 foundations land (see [docs/plan/04-roadmap.md](docs/plan/04-roadmap.md)). The contribution terms will be published here before the first outside pull request is merged.

When code contributions open, expect a few house rules:

- **Integrations ship with recorded fixtures and contract tests** ([architecture → integration framework](docs/plan/03-architecture.md#integration-framework)).
- **Every widget is designed for all its sizes and states** (loading, live, stale, error, empty) ([experience doc](docs/plan/02-experience.md#widget-anatomy-and-states)).
- **No third-party JavaScript in the app.** Integrations emit data, and our widgets render it.

## Fixtures and privacy

Fixtures must **never** contain real secrets, domains, public IPs or personal names. Sanitize them the way [testdata/importers/homepage/dogfood](testdata/importers/homepage/dogfood/README.md) does:

- replace domains with reserved example names (`*.example`)
- replace secrets with fake values in the same format
- map LAN IPs to a different private range

## Security

Please report vulnerabilities privately. See [SECURITY.md](SECURITY.md).

## License

Cha Dash is licensed under the [GNU Affero General Public License v3.0 or later](LICENSE).
