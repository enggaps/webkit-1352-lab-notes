# Sources and attribution

This project builds on public PS4 research. I do not claim authorship of upstream vulnerabilities, exploit primitives, firmware tables, SDK code, HEN code, or payloads.

Public material reviewed during the work includes:

- `adri22235/ps4-suid-scanner`, audited at commit `1089382ec1e0000e9557b7748d39b57952bbc4f3`;
- `adri22235/ps4-13xx-research`, audited at commit `2950dd69b961908ca6d909e089795be1219534e4`;
- Scene-Collective PS4HEN 13.52 source, audited at commit `2beb4cfcef1d416a32d6fb7b35f01189e9eb62e2`;
- PS4 payload SDK source with 13.52 definitions, pinned at commit `46efae910f3705e0171edea5b94e572d01bc00e8`;
- a supplied WebRTE source tree and partial libkernel material, used only for offline comparison.

Several public files were incomplete, lacked a reproducible run log, or were not tied to an exact 13.52 image. Those items remain leads and are not presented as verified results.

My contribution documented here is the firmware-specific test setup, fail-closed checks, hardware observations, evidence handling, and separation between measured results and unresolved claims.
