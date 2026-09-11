# Test method

The lab uses small gates so that one result does not silently become a larger claim.

## Before a run

1. Use a console and private network under my control.
2. Start a local HTTP server that exposes only the files required by the test page.
3. Confirm that responses use `no-store` and that unrelated routes are rejected.
4. Close the PS4 browser completely before a cold run.
5. Confirm the page detects firmware 13.52 exactly.

## During a run

- Each stage requires a separate manual action.
- A profile or hash mismatch stops the stage.
- Read-only stages use fixed windows and fixed byte limits.
- Logs show hashes, symbolic labels, and relative values. Live pointers and raw memory are not displayed.
- Browser objects are restored after a successful bounded read. Unsafe or uncertain states stop without continuing to another stage.
- Native calls, syscalls, kernel operations, patches, and payloads are outside the published test path.

## Evidence

For each useful run I keep the date, test revision, result, and SHA-256 of the retained screenshot or capture. Cold-launch repetition is required before treating a value as a baseline.

A pass is described only at the level it proves. For example, a userland read pass does not imply code execution, kernel access, or a jailbreak.

## Third-party material

Public repositories, offset lists, binaries, videos, and forum attachments are treated as untrusted leads. I record their commit or file hash where possible and compare them offline. A matching name or nearby firmware version is not enough to route a value into a hardware test.
