## ClearSign

Local transaction review for Safe and supported EVM transactions. ClearSign decodes signed fields, recomputes hashes and flags operations that need closer review. The desktop reviewer requires no keys and signs nothing.

### Repositories

- [clearsign](https://github.com/clearsign-dev/clearsign): Rust decoder, desktop reviewer, CLI and experimental signing platform.
- [clearsign.dev](https://github.com/clearsign-dev/clearsign.dev): source for the public website.

### Start Here

[Website](https://clearsign-dev.github.io/clearsign.dev/) · [Downloads](https://github.com/clearsign-dev/clearsign/releases) · [Supported formats](https://github.com/clearsign-dev/clearsign/blob/main/docs/10-what-is-supported.md) · [Verification status](https://github.com/clearsign-dev/clearsign/blob/main/docs/03-verification-status.md)

**Developer preview.** Decoding a call does not verify the target contract's behaviour. The desktop app depends on the computer displaying it; the dedicated signing platform has been tested only in emulation. Do not use the development signing tools with real keys or funds.

The verification record documents the reported human review, subsequent AI-assisted checks and work still requiring independent assessment.

### Reports and Contributions

[Report a bug](https://github.com/clearsign-dev/clearsign/issues/new/choose) or [read the contribution guide](https://github.com/clearsign-dev/clearsign/blob/main/CONTRIBUTING.md). Send vulnerabilities through [private security reporting](https://github.com/clearsign-dev/clearsign/security/advisories/new), not a public issue. Never submit private keys or recovery phrases.
