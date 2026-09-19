# PS4 13.52 WebKit — memory-safety research notes

Independent security research into browser memory-safety on a locally controlled
PlayStation 4 running system software 13.52. The work is variant-analysis: taking
publicly documented browser userland research and testing, on hardware I own,
which parts still reproduce on this exact firmware, and where new behaviour appears.

**This is a research log under responsible disclosure — not a jailbreak release.**
It contains no payload, kernel patch, persistence method, or ready-to-use exploit.
If any finding here reaches clear vendor impact, it goes to the vendor's official
security channel before any technical release. See [SECURITY.md](SECURITY.md).

- **Researcher:** enggaps
- **HackerOne:** https://hackerone.com/enggaps
- **Focus:** browser userland memory safety, exact-firmware compatibility, evidence-first methodology

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

See [SCOPE.md](SCOPE.md) for the full boundary, [SECURITY.md](SECURITY.md) for disclosure posture, and [SOURCES.md](SOURCES.md) for attribution.
