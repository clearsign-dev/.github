## Read what you are about to sign

Your hardware wallet shows you a hash. Your multisig interface shows you a
summary produced by a service. Neither of those is the transaction — they are
descriptions of it, and a description can be wrong.

On 21 February 2025 that gap cost Bybit about **$1.5 billion**. Every signer saw
what looked like an ordinary token transfer. What they approved was a
`DELEGATECALL` that ran someone else's code with the Safe's own storage and
balance.

**ClearSign decodes the transaction in front of you from the bytes themselves**,
with no knowledge of your wallet and no input from any service — including the
one that showed it to you. It holds no keys and signs nothing. Your hardware
wallet still does that.

The decoder never opens a socket: paste a transaction and nothing leaves the
machine. The one feature that reaches the network is fetching a queued
transaction by its hash, which contacts Safe's service and nothing else. The
signer image has no network stack compiled into its kernel at all.

### What is here

| | |
|---|---|
| **clearsign** | The signing core, the authority engine for AI agent actions, the command-line tool, the desktop application, and the seL4 platform they run on |

### Where it stands

Run against **238 real Safe transactions** pulled from Safe's own service, the
hash it computed agreed with the hash Safe published **238 times out of 238**.
There is exactly one `DELEGATECALL` in that set, and it is the Bybit one.

170 tests. Seven fuzz targets. Differential testing against a second
implementation. Builds that reproduce byte-for-byte on a machine that is not the
maintainer's.

And the part most projects leave out:

- **No users yet.** That is the number that matters.
- One external review, September 2026 — ten findings, all closed. **Nine of
  those fixes changed signing-critical code that nobody outside has read since.**
- No hardware root of trust, no verified boot, no secure element. Everything
  runs under emulation.
- EIP-712 typed data is not covered. The reviewer refuses it rather than guessing.
- The binaries are not code-signed.

**Early development. Unaudited beyond that one review. Not for real funds.**
Reviewing a transaction is safe on any computer; the signing and seed commands
stay behind a development guard, because a recovery phrase typed into an
everyday machine must be treated as exposed.

### Found something?

Security reports go through GitHub's private advisory form on the repository,
under **Security → Advisories**. `SECURITY.md` says what is worth attacking and
what is already known, so nobody spends an afternoon rediscovering that there is
no secure element.
