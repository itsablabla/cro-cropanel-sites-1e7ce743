# Conflicting value propositions — dev spec
Site: nomadinternet.com · Priority 1 · High · Effort: Low (0.5-2 days)

## Problem
Two different primary headlines dilute the core message about reliability and simplicity.

## Evidence (from the live site)
> The page's main headline reads “Reliable Internet That Works Anywhere in the U.S”.
> The page's main headline reads “Internet That Just Works”.

## Current state
h1: Reliable Internet That Works Anywhere in the U.S. / Internet That Just Works; notes: Two conflicting h1s.

## Required change
h1: Reliable Internet That Just Works Anywhere in the U.S.; notes: Single combined headline.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Single combined headline.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_conflicting_value_propositions` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
