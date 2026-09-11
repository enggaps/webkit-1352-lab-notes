# Status

Last updated: 11 September 2026

## Hardware results

### Userland carrier

On 2 September 2026, the firmware-gated runner reached a userland-only pass on a PS4 reporting system software 13.52.

The run completed on attempt 2. Its final log stated that the arbitrary-read self-check passed, that no firmware offsets were asserted, and that execution stopped before module lookup, native calls, syscalls, kernel objects, patches, or payloads.

The retained screenshot has SHA-256:

`0e8e28e1834dd91bd552c881b40dc5eab78f51930da2ae645f4ec26cacbc8f29`

This result proves one successful userland observation. It does not prove reliability or a complete exploit chain.

### Read-only identity work

After the first pass, I split later checks into separate manual stages. These stages used bounded reads and returned hashes and relative positions rather than live addresses or raw bytes.

The work reproduced:

- stable WebKit code-window fingerprints;
- a JavaScript-owned buffer layout check;
- anonymous browser-linked target page hashes across cold launches;
- stable relative geometry between those targets;
- a three-page continuity hash across two cold launches.

One left-boundary experiment caused the browser process to terminate with the console's insufficient-memory message. That direction was retired. A later right-side, one-page bounded read completed successfully. The failure is recorded as a process boundary observation, not as proof of an unmapped page or a vulnerability.

### Import-relative check

On 7 September 2026, one manual hardware run matched four frozen import-relative code-window hashes. The check covered 482 bytes in total and stopped immediately after comparison.

The retained screenshot has SHA-256:

`459571cb01050e576da5d6c1f97d6e84b2ec2a7f14b36831a6dcb5d60c0f214b`

No function was called during this check. No syscall, kernel action, patch, or payload was executed.

## Static checks

The local verifier checks firmware routing, route allowlists, read limits, address redaction, and the absence of kernel, patch, and payload paths from the research page. Candidate source files and binary fragments are handled offline and are not served to the console.

## Not established

The following claims are not supported by my current evidence:

- a stable public exploit for firmware 13.52;
- kernel reachability or kernel read/write;
- a working kernel vulnerability;
- patch or HEN compatibility;
- payload execution;
- a CVE, bug bounty award, or coordinated disclosure;
- authorship of upstream exploit primitives, offsets, or payloads.

The next step remains verification of provenance and repeatability, not packaging a release.
