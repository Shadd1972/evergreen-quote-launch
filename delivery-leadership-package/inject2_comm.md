# Communication: Holding Message to Reporting Manager (Inject #2)

| | |
|---|---|
| **To** | Reporting manager, reported the issue during the pre-launch dry run |
| **From** |Shadd Schutte, Delivery Lead |
| **Date / time** | Wednesday 11-18-2026, 14:30 EST |
| **Channel** | Email |
| **Subject** | Re: "Could not load recent quotes" in the demo environment |

## Message

Thanks for flagging this. The "Could not load recent quotes" error is in
the shared demo environment, where a configuration change this afternoon
stopped the quote service reaching its database. The platform team owns
that environment and is looking at it now.

Friday's launch demo does not run on that environment: it runs on our own
verified setup, which is healthy, and all our automated checks are
passing. So Friday is not at risk from this.

I'll update you by **16:30 today**, or sooner if the shared environment
is back.

Shadd Schutte
Delivery Lead, Evergreen Quote Launch

## Why this message is written this way

- **Calm and specific:** names what is known and what is not affected.
- **Names the environment:** "the shared demo environment", so it cannot
  be mistaken for the launch setup.
- **No blame:** says what changed, not who changed it.
- **A commitment with a time:** the next update is due by 16:30.