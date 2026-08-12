# Ambiguous one-time costs — dev spec
Site: nomadinternet.com · Priority 5 · Medium · Effort: Low (0.5-2 days)

## Problem
One-time amounts are shown without labeling what they cover, creating uncertainty about equipment ownership.

## Evidence (from the live site)
> A section heading reads “$0.00 (one-time)”.
> A section heading reads “$99.99 (one-time)”.
> Prices shown on the page: $99.95/month $129.95/month $99.95/mo $0.00 $99.95 $99.99

## Current state
notes: One-time fees without purpose.

## Required change
notes: Label each one-time fee and state equipment ownership.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Label each one-time fee and state equipment ownership.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_ambiguous_one_time_costs` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
