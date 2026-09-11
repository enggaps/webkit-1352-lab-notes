# Scope and safety boundary

This work is for compatibility research on hardware and a network under my control.

## In scope

- source review;
- exact-firmware compatibility checks;
- browser userland testing;
- bounded read-only fingerprints;
- crash and process-termination analysis;
- offline comparison of hashes and public source candidates;
- documentation of failed as well as successful runs.

## Out of scope

- testing systems owned by other people;
- scanning public targets;
- credential collection or account access;
- persistence;
- destructive payloads;
- kernel writes or patching in the published test path;
- packaging a ready-to-use exploit;
- claiming a CVE, bounty, employer, or disclosure that does not exist.

Private IP addresses, console identifiers, live addresses, raw memory captures, and firmware dumps are not published here.

If the work later identifies a new security issue with clear vendor impact, disclosure should happen through the vendor's official security channel before technical release.
