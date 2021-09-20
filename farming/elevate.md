# Elevating Funds

![](../.gitbook/assets/elevating-funds-masthead.jpg)

{% hint style="success" %}
**Elevating funds transfers staked tokens or LP from one elevation to another, without requiring separate withdraw & deposit transactions.**

**"Elevating" does not charge a deposit fee, even if the farm has a deposit fee.**
{% endhint %}

"Elevating" Funds is part of our mission to create a frictionless and mature experience for users. Being forced to withdraw and then deposit your funds to move across elevations \(potentially paying a second deposit fee\) was unacceptable to us, so we implemented Elevating to make the process as smooth as possible.

_Elevating funds can be done from the Summit Defi frontend from any staked farm, and can also be executed through each networks bscscan equivalent._

## FAQ:

## When can I elevate funds?

You can Elevate funds at any time from any farm to a matching farm \(a farm sharing the same token / LP\) at a different elevation.

## Can I elevate into the Expedition?

Of course. Expeditions stake SUMMIT, and your SUMMIT can be transferred directly from a farm to an expedition \(and back again\) without slowing you down at all.

## Do I lose my winnings if I elevate?

Elevating will attempt to harvest any winnings in both the source and destination pool. Any already vested and available to harvest funds will be harvested, and any funds still vesting will continue to do so.

## Can't I just withdraw and deposit?

Of course, this is a completely viable way to move funds between elevations. You will have to pay the gas fees for both transactions though. Additionally, a deposit fee is shared across all elevations, so if you withdraw and deposit, you may get hit by the deposit fee again.

## Are my funds actually moved?

Elevating funds actually doesn't touch the funds at all. Funds management is always completed in the Cartographer, which would be both the source and destination of your tokens during an elevate transaction, so no movement needs to happen.

Instead, the amount elevated is removed from your staking balance of the source pool, and added to the staking balance of the destination pool.

## How does Elevating work with Passthrough?

Passthrough Strategies are on a per token / LP basis, so just like for the Cartographer, the funds remain in the passthrough strategy, ignorant that they are being moved at all.

