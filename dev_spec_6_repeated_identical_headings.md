# Repeated identical headings — dev spec
Site: nomadinternet.com · Priority 6 · Medium · Effort: Low (0.5-2 days)

## Problem
Repeated identical headings across pages and sections confuse visitors about their location.

## Evidence (from the live site)
> The page's main headline reads “Let's Get You the Right Internet”.
> The page's main headline reads “What Best Describes Your Time on the Road?”.
> The page's main headline reads “How Do You Use the Internet at Home?”.
> A section heading reads “How It Works”.

## Current state
h1: Multiple repeated h1s; notes: Same headings repeated across pages.

## Required change
h1: Unique headings per page; notes: Use descriptive, unique headings.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Use descriptive, unique headings.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_repeated_identical_headings` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
