# Random Number Generation

![](<../../.gitbook/assets/RNG Masthead.jpg>)

{% hint style="info" %}
**This is more of a technical documentation, and isn't a **_**must read\*\* \*\***_**to understand the Summit ecosystem.**
{% endhint %}

## **Randomness Flow**

Random number generation is used to select the winning totem, and must be ensured to be accurate. Randomness is ensured by using a webserver watching the state of `ElevationHelper.sol` (open source) and seeding randomness using the following flow:

1. Cron job starts a script 60 seconds before the end of each round
2. Webserver waits for `nextSeedRoundAvailable` to switch to true
3. It then generates a random seed and encrypts it with its own address (Trusted Seeder address)
4. `receiveSealedSeed` is called with the newly sealed seed
   1. `ElevationHelper.sol` marks the upcoming block in the future as a target
   2. When the future block is mined, its hash is stored
5. Webserver waits for `futureBlockMined` to become true
6. `receiveUnsealedSeed` is called with the unencrypted random seed
   1. `ElevationHelper.sol` validates that this is true random seed by hashing it with the Trusted Seeder address (same as above), and matching the hash against the sealed seed
   2. The hashes match, validating that the same random seed was used in both the sealed and unsealed seed
7. Webserver waits for the full round to end, then calls `rollover` of `Cartographer.sol` for any elevations whose rounds are ending
8. Webserver waits for that transaction to succeed, then calls `rolloverPools` of `Cartographer.sol` for those same elevations

**The entirety of this flow occurs during the 60 second lockout at the end of each round, preventing users from changing anything about their risked yield until after the round is finalized.**

## How the Flow guarantees Randomness

The key aspect of the Randomness flow above is that

1. The Trusted Seeder webserver is blind to the future block hash when it generates the initial randomness seed (through matching of sealed and hashed unsealed seeds before and after future block mined)
2. The miner is blind to the unencrypted randomness seed when it generates the future block hash

With both parties blind to the actions of the other, neither can alone manipulate the final result. This is a known valid randomness pattern, adapted to the summit defi ecosystem.

## Webservice

This in-house webservice will be open source along with the rest of the summit ecosystem.

In the future this in-house webservice will be made available for a small fee to cover gas to any projects wishing to have trusted seeding for their projects. Though it is more centralized than VRF from chainlink, it costs a fraction of the price in gas (and link), and is very easy to implement in any contract.
