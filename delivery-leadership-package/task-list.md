# Task List: Evergreen Quote Launch

**Board:** [Evergreen Quote Launch](https://github.com/users/Shadd1972/projects/6) (GitHub Project, linked from `vision-brief.md`)
**Repo:** [Shadd1972/evergreen-quote-launch](https://github.com/Shadd1972/evergreen-quote-launch)
**Owner:** Shadd Schutte, Delivery Lead
**Last updated:** 11-17-2026

> The live task list is the GitHub Project board above; this file records how
> the work is organized and what every issue must contain before it is
> considered ready. When the board and this file disagree, the board wins.

## How the board works

| Column | Meaning |
|---|---|
| To Do | Ready to start: done criteria written, priority set |
| In Progress | Being worked today; no more than two at a time |
| Done | Every done-criteria box is checked and the evidence (screenshot, CI link, or PR) is in an issue comment |
| Deferred / Post-launch | Deliberately not this week; each card says why and who owns it next |

## Priorities

| Priority | Meaning |
|---|---|
| P0 | Required for Friday's launch; the delivery goal fails without it |
| P1 | Expected this week, but the launch can still go ahead without it |
| P2 | Stretch; only after every P0 is Done |

## Area labels

`WIRE` client-to-API connection · `TYPES` contracts and the type-check ·
`DATA` stub retirement · `CONFIG` launch values · `GRAPHQL` partner API ·
`DOCKER` container image · `K8S` local cluster · `CI` pipeline ·
`BUILD` production build · `REVIEW` PR and merge · `SHOWCASE` Friday demo ·
`AI` Copilot oversight · `ROUTED` / `DEFERRED` decisions from injects

## Changes since Monday

- **Inject #1 (Tuesday):** added `[ROUTED] Request: quote form defaults to life`
  (owned by the front-end team) and `[DEFERRED] Renters coverage (post-launch)`.
  Both are in Deferred / Post-launch; the delivery goal did not change.
- **Inject #2 (Wednesday):** <note any board change, e.g. a comment on [K8S]
  recording that the shared demo environment incident was routed to the
  platform team>.

## Issue template

```
Title: [AREA] short verb-first description

Who it's for: <user>. What they get: <thing>. Why it matters: <outcome>.

Done criteria
- [ ] Observable thing 1
- [ ] Observable thing 2
- [ ] Observable thing 3

Out of scope
- Anything that is *related* but explicitly not in this issue.

Linked decisions / risks
- (links to decision memos or risk-register rows if applicable)
```

## Initial Task List - For complete list use GitHub

| # | Title | Area | Priority |
|---|---|---|---|
| 1 | Run all three parts; log the client/API data gap | WIRE | P0 |
| 2 | Wire the client to the API (proxy, types, api module, context, form) | WIRE | P0 |
| 3 | Fix the seam defect the type-check catches (kit one-line fix) | TYPES | P0 |
| 4 | Retire the static data feed and bundled sample | DATA | P0 |
| 5 | Align the client rates to the API; set the launch title and banner | CONFIG | P0 |
| 6 | Mount GraphQL; run one query in the explorer; peek in mongosh | GRAPHQL | P1 |
| 7 | Build evergreen-quote-api:2.0; run the stack with the container | DOCKER | P0 |
| 8 | Demonstrate the full stack on the local cluster | K8S | P0 |
| 9 | Enable the two-job CI workflow | CI | P0 |
| 10 | Production build; preview the built client against the API | BUILD | P0 |
| 11 | Open PR from delivery/lead → main; self-review the program's diff | REVIEW | P0 |
| 12 | Build and rehearse the program showcase | SHOWCASE | P0 |
| 13 | Document one Copilot-assisted step + critique | AI | P2 (stretch) |
