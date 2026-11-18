# Go / No-Go: Launch Decision
 
**Date / time:** Wednesday 11-18-2026, 15:15
**Decision:** ☐ GO   ☐ NO-GO   ☒ GO WITH CONDITIONS
 
## CI evidence
 
- Latest run on delivery/lead (both jobs): green · link: https://github.com/Shadd1972/evergreen-quote-launch/actions/runs/44340557532
- Workflow file: .github/workflows/ci.yml
- What the workflow actually checked: Test the API (mongo:7 service
  container, npm ci, npm test: 7 tests); Type-check and build the
  client (npm ci, npm run type-check, npm run build).
 
## Other evidence, by environment
 
- My local kind cluster "evergreen": 3 evergreen-quote-api pods +
  1 mongo pod Running; a quote saved through the port-forward
  survives a reload.
- My repo: k8s/deployment.yaml and api/src/db.js both use MONGODB_URI.
- Shared demo cluster (platform team): API pods in CrashLoopBackOff
  since ~13:25 after an env-variable rename (MONGO_URI). Routed to the
  platform team at 14:30; tracked in the risk register (R9).
 
## What "GO" would mean
 
- Merge delivery/lead → main, squash, delete branch.
- Tag the merge commit "launch".
 
## What "NO-GO" would mean
 
- Hold the merge until: CI is green on the PR, and the platform team
  confirms the incident is isolated to the shared demo cluster.
- Owner of that condition: me (CI); platform team (the incident).
- Re-evaluate at: Thursday 10:00 check-in.
 
## My call
 
GO WITH CONDITIONS. Friday's demo runs on my own local cluster and is
proven by my CI, and both are green; the shared demo environment is
broken, but it belongs to the platform team, it is tracked, and
nothing in my merge path depends on it. I flip to NO-GO if CI on the
PR turns red, or if the platform team finds the cause is in our
image or manifests rather than in their environment.
