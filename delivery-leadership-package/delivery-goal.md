# Delivery Goal: Evergreen Quote

## Goal

> By Thursday EOD, the wired Evergreen Quote app saves quotes that survive a reload at the same premium the estimate promised, the containerized API runs as three pods on the local cluster, and the launch is merged to main through a reviewed PR with both CI jobs green.

## "Done" looks like

- The quote page loads its recent quotes from the API, and a saved quote survives a reload.
- The estimate on screen and the saved premium agree, at the launch rates (auto 90, home 135, life 70; auto, age 35, coverage 50000 shows $450.00 in both places).
- `npm test` (API) and `npm run type-check` + `npm run build` (client) pass; both CI jobs on the merge commit are **green**.
- The containerized API (`evergreen-quote-api:2.0`) serves the wired app, and the cluster demo shows three API pods behind one Service.
- The landing page carries the launch banner and points at the app.
- A reviewed PR is merged, branch deleted.
- `delivery-leadership-package/` is complete and committed.

## Out of scope (this week)

- Authentication, accounts, or login.
- Payments or binding a policy; we quote, we do not sell.
- A real rate engine; premiums use the existing formula at the sponsor's launch rates.
- New coverage types (renters stays on the wish list, as deferred last week).
- Moving all premium math to one place; the client estimate and the API calculation stay in both places with rates aligned, tracked in the risk register.
- Any cloud dependency for the launch demo; Friday runs on the local kind cluster. The Thursday EKS window, if the sponsor opens it, is a verification pass only.
- Writing new application code or refactoring any team's work; we assemble the provided pieces.