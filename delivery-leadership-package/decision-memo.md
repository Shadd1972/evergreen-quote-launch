# Decision Memo: Where the price is calculated
 
**Date:** Tue 11-17-2026  
**Author:** Shadd Schutte      
**Decision area:** Day 2 pricing consistency
 
## Context
When the quote page and the quote service were connected, the same
inputs showed $425 on screen but saved at $450. Each half calculates
the price itself, using different rate tables.
 
## Options considered
1. Keep both calculations, align the rates. Instant estimates, no
   extra waiting; but two copies can drift again.
2. Every estimate asks the service. One source of truth; but each
   keystroke waits on the network, and the estimate fails if the
   service is down.
3. Show no estimate until saved. Simplest; but removes the instant
   number customers come for.
 
## Recommendation
Option 1 for launch: align the client's rates to the service's
(the sponsor's rule: the server is the source of truth), and log
the duplication as a tracked risk.
 
## Why
Customers came for an instant, believable number. Option 1 keeps it
instant and makes it agree with what we store.
 
## What would change my mind
If rates must change more than once a quarter, or a second mismatch
appears before launch, I would move to Option 2 next release.