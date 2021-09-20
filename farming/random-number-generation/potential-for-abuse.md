# Potential for Abuse

![](../../.gitbook/assets/rng-potential-for-abuse-masthead.jpg)

{% hint style="info" %}
_**In the interest of transparency, we have written this article so our users are as informed as possible.**_
{% endhint %}

Random Number Generation is at the core of any gambling based ecosystem. If the result can be manipulated or known before hand, the entire system comes crumbling down.  
  
We have done everything we can to prevent this from happening, but there is theoretically still a way for this to be manipulated.

On-Chain VRF, or even a good oracle system, doesn't exist for every chain we want to launch on, and as a result to maintain a unified codebase we have gone with our own randomness system.

## Trusted Seeder

We use a trusted seeder system to generate and send in the random seeds for each round rollover event. The trusted seeder is a webservice with access to a funded wallet. The webservice uses a cron job to send an encrypted random seed 60 seconds before the end of each round, seeding the randomness that eventually decides the winner of the round.

This Trusted Seeder address is still owned by the Summit devs. And thus the only way to manipulate the randomness is by ourselves, though this would still be an extremely difficult process. We would have to manipulate the randomness **AND** operate a node on the chain **AND** be the node to validate the single block an hour that rolls over a round. Seriously, we couldn't do this if we tried.

To mitigate this fear the sourcecode for the webservice, as well as the address of the trusted seeder wallet, is open source and verifiable externally. Every transaction sent can be seen to be coming from the webservice itself, and the timing of each transaction verified against the cron job.

