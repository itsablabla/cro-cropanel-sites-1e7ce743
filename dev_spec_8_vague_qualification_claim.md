# Vague qualification claim — dev spec
Site: nomadinternet.com · Priority 8 · Medium · Effort: Medium (2-5 days)

## Problem
Claim of universal qualification lacks specifics, leaving offer unclear.

## Evidence (from the live site)
> A section heading reads “You qualify for everything”.

## Current state
notes: Vague claim without details.

## Required change
notes: Provide specific coverage, speeds, and plan options.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Provide specific coverage, speeds, and plan options.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_vague_qualification_claim` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
