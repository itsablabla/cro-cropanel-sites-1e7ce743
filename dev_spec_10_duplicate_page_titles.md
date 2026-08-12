# Duplicate page titles — dev spec
Site: nomadinternet.com · Priority 10 · Medium · Effort: Medium (2-5 days)

## Problem
Identical page titles across pages weaken information scent and confuse navigation.

## Evidence (from the live site)
> The browser title reads “nomadinternet.com”.

## Current state
notes: All pages have same title.

## Required change
notes: Unique descriptive titles per page.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Unique descriptive titles per page.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_duplicate_page_titles` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
