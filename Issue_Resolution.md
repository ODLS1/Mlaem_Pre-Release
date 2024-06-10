## MLAEM Issue Resolution Approach

This document describes the issue resolution and bug fixing approach for MLAEM.

### Definition of Issue Priorities
* Priority 0 (P0): Completely blocks use of a feature (no workaround)
* Priority 1 (P1): Blocks feature, but has a cumbersome workaround
* Priority 2 (P2): Blocks feature, but has a reasonable workaround
* Priority 3 (P3): Does not block a feature and represents an enhancement

### Process
Users are instructed to file issues/bugs in the Github Issues log on any MLAEM Repository (`Pre-Release`, `Release`, `Mlaem Source`)
  * Confirm reproduction of issue 
  * Move issues from `Release` repositories into `MLAEM Source` Repository
  * Triage async or non-P0 Tasks during Weekly Standup

### Bug Remediation

This section describes the bug remediation process for the pre-release and production versions of MLAEM.

#### Alpha/Beta Bug Fixing Schedule:

* P0: Triage and fix immediately
* P1: Fix during this sprint or next
* P2: Fix during next bug week (every 4 or 6 weeks)
* P3: Fix when able or move to story/milestone

#### Production Bug Fixing Schedule: 

* P1’s to be fixed within a week, alongside feature work
* One or two P2’s selected weekly to be fixed alongside feature work
* Dedicate a week to bug fixes monthly as needed to remediate P2, P3 backlog
