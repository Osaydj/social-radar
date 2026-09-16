# Privacy Design

Social Radar is designed around explicit account authorization and data minimization.

## Principles

- **No Instagram password collection.** Account access is intended to use supported Meta authorization flows.
- **No unsupported profile-viewer claims.** Social Radar does not present silent profile visits as identifiable users unless a supported provider explicitly exposes that information.
- **No session-cookie harvesting.** The application does not rely on taking a user's Instagram browser session or asking them to paste private cookies.
- **No scraping dependency.** The product architecture is centered on supported provider APIs and webhooks.
- **User controls are first-class.** Connected accounts can be disconnected, application data can be exported, and the Social Radar account can be deleted.
- **Secrets stay outside Git.** Provider credentials, database URLs, application secrets, and cron secrets are supplied through deployment environment variables.

## Token handling

Provider access tokens are treated as sensitive application secrets. The production design encrypts them before persistence and limits their use to the provider integration layer.

## Session handling

Production browser authentication uses secure HttpOnly cookies. The frontend communicates through a same-origin proxy so application sessions do not depend on fragile cross-site cookie behavior between separate hosting providers.

## Data interpretation

Analytics describe **observable interaction patterns**. Scores such as reciprocity, consistency, and momentum are product metrics derived from available events; they are not claims about a user's private intent or real-world relationship quality.

## Data lifecycle

The product includes flows for:

- disconnecting a linked Instagram account;
- exporting stored application data;
- deleting the Social Radar account and associated application records.

Production retention rules and public-facing legal language will be finalized alongside the deployed privacy policy and current Meta platform requirements.