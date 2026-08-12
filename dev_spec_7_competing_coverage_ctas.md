# Competing coverage CTAs — dev spec
Site: nomadinternet.com · Priority 7 · High · Effort: Medium (2-5 days)

## Problem
Multiple competing coverage-check CTAs split user attention and obscure the primary action.

## Evidence (from the live site)
> 7 distinct calls to action compete on the same page: “CHECK COVERAGE”, “CHECK IF IT WORKS AT MY ADDRESS”, “SEE MY OPTIONS”, “GET STARTED”, “START CHAT”, “SEE WHAT I QUALIFY FOR”, “CHECK MY COVERAGE”.

## Current state
cta: Multiple competing CTAs; notes: Coverage check offered under several labels across pages.

## Required change
cta: Single 'Check Coverage' CTA; notes: Consolidate all coverage entry points into one primary CTA.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Consolidate all coverage entry points into one primary CTA.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_competing_coverage_ctas` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
