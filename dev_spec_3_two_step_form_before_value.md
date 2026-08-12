# Two-step form before value — dev spec
Site: nomadinternet.com · Priority 3 · High · Effort: Medium (2-5 days)

## Problem
Users must complete two sequential forms before seeing any plan details, adding friction.

## Evidence (from the live site)
> (see report)

## Current state
cta: CONTINUE (two steps); notes: Two-step form before plans/pricing.

## Required change
cta: Single coverage check; notes: Reduce to one step or show plans/pricing first.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Reduce to one step or show plans/pricing first.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_two_step_form_before_value` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
