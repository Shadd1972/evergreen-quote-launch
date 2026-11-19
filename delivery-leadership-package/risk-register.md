# Risk Register

| # | Risk | Owner | Likelihood (L/M/H) | Impact (L/M/H) | Mitigation | Trigger to escalate |
|---|---|---|---|---|---|---|
| R1 | Page renders while the client/API contract is quietly wrong (e.g., `id` vs `_id`), so the demo "works" until a field goes missing. | Front-end team | M | H | Run `npm run type-check` and `npm test` after every wiring step; CI on every push. | Either check red at 16:00: hold the push, raise at check-in. |
| R2 | Customer sees one price and is saved at another (client and API rate tables drift). | Delivery Lead / sponsor | H | H | Align client to API per sponsor; verify auto/35/50000 shows $450 in both places. | Any estimate/saved mismatch: no-go for demo until resolved. |
| R3 | Demo shows the wrong or empty database (VM DB vs cluster DB are different). | Delivery Lead | M | M | Write the demo plan naming the cluster DB; save realistic quotes into it Thursday. | Panel empty at Friday 13:30: switch to screenshots. |
| R4 | Port-forward or a dev server dies mid-demo; nothing answers on port 3000. | Delivery Lead | M | H | Pre-demo checklist (Step 5.1); screenshot fallback ready. | No response 30 s before talk: use fallback. |
| R5 | CI red on the merge commit, undermining the go/no-go. | Platform services team | L | H | Run tests locally before PR; merge only on green. | Red on PR: route to owning team, do not merge. |
| R6 | AI-generated changes (Copilot seed rows) break the data contract unnoticed. | Delivery Lead | M | M | Review before accepting; run `npm run seed` to test against the schema. | Seed fails or rows look wrong: revert, do not commit. |
| R7 | Managers lose the story because it assumes insider context. | Delivery Lead | M | H | Timed rehearsal in manager language. | Rehearsal over 5:00 or uses jargon: cut and rewrite. |
| R8 | A "one-word" launch-week change to a shared hook (form default to life, Inject #1) ships without the owning team's review and breaks every estimate. | Front-end team | M | H | Route to the front-end team with the launch date; Delivery Lead does not edit `useQuoteEstimate.ts`; otherwise defer post-launch. | Change appears in the diff without front-end review: block the merge. |
| R9 | Shared demo environment down (Inject #2: API pods crash after the `MONGO_URI` rename) and confuses the launch story or the go/no-go. | Platform services team | H | M | Route with evidence; Friday demo runs on my own kind cluster; verify my own context, pods, manifest, and CI. | Platform team has no ETA by Thursday 10:00, or the cause turns out to be in our image or manifests: re-evaluate go/no-go. |

## How I'll use this register

_One short paragraph. When will you re-read it? Who else can see it? What's the cadence?_
