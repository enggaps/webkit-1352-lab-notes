# 2 September 2026 — userland check

## Setup

- Target reported PS4 system software 13.52.
- The page was served from an allowlisted local server on a private network.
- The runner was locked to the exact firmware.
- The browser was started fresh.

## Result

The first attempt did not complete the placement step. The second attempt reached the carrier self-check and reported:

```text
READ-PRIMITIVE-PASS arbitrary-read-established
firmware-offsets-asserted=none
PROBE-PASS userland carrier self-check passed; attempts=2
STOP
```

The screenshot retained with the local evidence set has SHA-256:

`0e8e28e1834dd91bd552c881b40dc5eab78f51930da2ae645f4ec26cacbc8f29`

## Interpretation

This was enough to continue with a separate read-only identity stage. It was not evidence of a native-call bridge, syscall access, kernel access, patching, or payload execution.

I closed the browser after the result instead of continuing in the same process.
