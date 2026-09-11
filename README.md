# PS4 13.52 WebKit lab notes

This repository records compatibility testing I carried out on a locally controlled PS4 running system software 13.52. The question was narrow: which parts of an earlier browser userland research path could still be reproduced on this firmware?

This is a research log, not a jailbreak release. It does not contain a payload, kernel patch, persistence method, or a ready-to-use exploit.

## What I verified

- The test page refuses to run unless the browser reports firmware 13.52.
- A self-checking userland read primitive passed on hardware on 2 September 2026. It completed on the second attempt and stopped before module lookup, native calls, syscalls, or kernel work.
- Later read-only checks reproduced stable WebKit code fingerprints and bounded module-relative identities.
- A bounded import-relative check matched four previously frozen code-window hashes on hardware on 7 September 2026.
- Local server routes were allowlisted, used no-store responses, and rejected unrelated paths.

The detailed results and their limits are in [STATUS.md](STATUS.md). The procedure is described in [METHOD.md](METHOD.md).

## Run notes

- [2 September 2026 — userland check](notes/2026-09-02-userland-check.md)
- [7 September 2026 — import-relative code check](notes/2026-09-07-relative-symbol-check.md)

## Current limit

There is no verified public 13.52 jailbreak chain here. I have not established kernel read/write, a kernel exploit, patch compatibility, or payload execution. Third-party offsets and binaries are treated as leads until they can be tied to an exact image and checked byte for byte.

## Scope

Testing is limited to a console and network under my control. The published notes exclude live addresses, raw memory, private network details, console identifiers, firmware dumps, and operational exploit code.

See [SCOPE.md](SCOPE.md) for the full boundary and [SOURCES.md](SOURCES.md) for attribution.
