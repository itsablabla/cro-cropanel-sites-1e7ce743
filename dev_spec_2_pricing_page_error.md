# Pricing page error — dev spec
Site: nomadinternet.com · Priority 2 · Urgent · Effort: Medium (2-5 days)

## Problem
Direct navigation to /pricing returns an error, dead-ending users and preventing them from seeing plans.

## Evidence (from the live site)
> "/pricing": "error"

## Current state
notes: /pricing returns error.

## Required change
notes: Fix route or redirect to working page.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Fix route or redirect to working page.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_pricing_page_error` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 124,891 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
