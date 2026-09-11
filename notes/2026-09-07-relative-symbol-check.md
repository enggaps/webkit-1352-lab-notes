# 7 September 2026 — import-relative code check

## Purpose

Earlier cold runs produced a stable, bounded browser-linked capture. Offline comparison identified four code windows relative to an already checked import target. This run tested whether those exact hashes appeared again on retail hardware.

## Result

All four frozen windows matched. The combined read size was 482 bytes. The final summary recorded:

```text
matched=4/4
bytes=0x1e2
anchor=__error
addresses=redacted
STOP
```

The screenshot retained with the local evidence set has SHA-256:

`459571cb01050e576da5d6c1f97d6e84b2ec2a7f14b36831a6dcb5d60c0f214b`

## Interpretation

The run supports repeatable import-relative code identity for those four windows. It does not establish a module base, calling convention, ABI safety, or permission to call any of the functions.

No raw bytes or live addresses were uploaded. No function, syscall, kernel operation, patch, or payload was executed.
