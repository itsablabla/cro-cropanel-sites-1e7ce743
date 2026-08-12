# Unsupported trust badge — dev spec
Site: nomadinternet.com · Priority 9 · Medium · Effort: Medium (2-5 days)

## Problem
Trust badge 'SHOP WITH CONFIDENCE' lacks supporting guarantee or security details.

## Evidence (from the live site)
> A section heading reads “SHOP WITH CONFIDENCE”.

## Current state
notes: Trust badge without details.

## Required change
notes: Add guarantee terms, return window, security certifications.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add guarantee terms, return window, security certifications.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_unsupported_trust_badge` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
