<!--
  Write for a reviewer who has not seen the ticket or your session. Say only what the diff
  cannot. Aim for 100–300 words; over 400, cut. Delete every comment and every optional
  section you do not use. British English, no preamble, no closing summary, no
  "Generated with Claude Code" footer.
-->

## 🎯 Goal

<!--
  One or two sentences: who is affected and what changes for them. Outcome first, mechanism
  second.

  Bad:  "`FactorValue` gains a `bookableUntil` field."
  Good: "Back Office cannot assign a data package to a user who holds an expired grant for it.
         Assigning now renews the expired grant instead of returning 409."
-->

<!-- Uncomment each reference you have; the rest stay hidden. -->
<!-- - 🎫 Ticket: [PROJ-123](https://spartacommodities.atlassian.net/browse/PROJ-123) -->
<!-- - 📄 PRD / ADR: -->
<!-- - 🎨 Design: -->
<!-- - 🐛 Incident / Alert: -->
<!-- - 💬 Discussion: -->

## 🧭 Context

<!--
  Optional. Up to three sentences a reviewer needs to judge the change: the prior state, the
  root cause, or the constraint that rules out the obvious fix. Do not restate the Goal.
-->

## 📝 Changes

<!--
  The shape of the change as behaviour, not files: short prose, or up to five bullets. Name
  the decision a reviewer would question and the alternative you rejected. Flag anything easy
  to miss: API or schema changes, migrations, feature flags, new config or dependencies.

  Bad:  "- **`VesselSupplyController`** adds the endpoint"
  Good: "Assign returns 409 only while the existing grant is active. An expired grant is
         renewed in place and audited like the PATCH path. Listing expired grants in the UI
         was considered and not chosen."
-->

## 🧪 How to verify

<!--
  Scenarios a reviewer can run by hand: the happy path, then the edge case most likely to
  break. CI reports the automated suites, so never list test commands, pass counts or
  "tests green".

  **Disabled commodity row**
  - Setup: `fe_commodities_lpg_naphtha_arbs` on, a user without the LPG / Naphtha entitlement.
  - Steps: open the commodity selector and hover the LPG / Naphtha row.
  - Expect: the row aligns with the others and the unlock tooltip shows. Before, it sat
    further left.

  If nothing is observable by hand, write one line saying why, and name a test that pins the
  behaviour: "No manual check: refactor only. `ExpiredGrantTest` fails without the fix."
-->

## 💬 Notes for reviewer

<!--
  Optional. Up to five bullets a reviewer would otherwise miss: risk, what you could not
  verify, rollout order or rollback, deliberate follow-ups, before/after screenshots.
-->
