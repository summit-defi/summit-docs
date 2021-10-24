# Expedition Multi-Pledging

{% hint style="success" %}
**TL,DR:**

**Multi-Staking allows users to pledge \_either- , both- , or any combination of- \_SUMMIT and SUMMIT-FTM LP in the same Expedition:**

**Total SUMMIT pledged (amount used to calculate winnings) =**\
\*\* pledged SUMMIT +\
**\*\* SUMMIT \_inside \_pledged**_\*\*_**SUMMIT-FTM LP**

_Both SUMMIT and SUMMIT-FTM LP can be elevated into and out of Expeditions from other farms._
{% endhint %}

Say a user pledges 10 SUMMIT-FTM LP, how much does that add to your pledged amount?

_Lets take an example, if the user took that 10 SUMMIT-FTM LP to SpookySwap and broke the LP, and it broke into 20 SUMMIT and 5 FTM, they would then be able to pledge that 20 SUMMIT in the Expedition. **Instead, that user can pledge the 10 SUMMIT-FTM LP in the Expedition directly, and our contracts calculate that it would be worth 20 SUMMIT if it was broken, so we add that 20 SUMMIT to the user's pledged amount. No LP break necessary!**_

\_\_

#### \* The below specifics of Multi-Pledging are not strictly required reading, and are somewhat technical on the mechanics and implementation, feel free to skip it if the explanation above was enough for you \*

### The Why

Our users shouldn't be punished for holding SUMMIT-FTM LP token. Forcing our users to break their LP would result in periodic low liquidity, and high price fluctuations, and more frequent impermanent loss; obviously not something we want to do.

Instead, with **Multi-Pledging,** you don't have to break your LPs into SUMMIT token to enter and win in the weekly Expeditions.

## Equivalent SUMMIT in LP

If you were to break your SUMMIT-FTM LP, the amount of SUMMIT that you would get out of that transaction is your **equivalent SUMMIT**. Therefore, the total amount of SUMMIT that is used to calculate your winnings is as follows:

```
Expedition Staked Amounts
  5 SUMMIT-FTM LP
  15 SUMMIT token

        
Example LP Break Transaction On Exchange
  5 SUMMIT-FTM LP ==> 20 SUMMIT token + 45 FTM
  ∴ exchange rate = 1 SUMMIT-FTM LP ==> 4 SUMMIT token


Total SUMMIT pledged in Expedition
  20 SUMMIT token (from 5 SUMMIT-FTM LP)
+ 15 SUMMIT token
-----------------
  35 SUMMIT token
```

If the exchange rate were **1 SUMMIT-FTM LP ==> 2 SUMMIT** + XX FTM, all of the following (if they all win) would have the exact same \*\*total SUMMIT, \*\*and yield the exact same winnings:

```
User 1                    User 2                    User 3
10 SUMMIT-FTM LP          3 SUMMIT-FTM LP           0 SUMMIT-FTM LP
0 SUMMIT token            14 SUMMIT token           20 SUMMIT token
```

## SUMMIT-FTM LP Incentive Multiplier

> **At launch, the Incentive Multiplier is set to 1X, meaning no extra boost to equivalent SUMMIT, but can be increased to anywhere between 1X - 2X to incentivize users to not break their LP. We will monitor this and see if 1X is sufficient.**

So \_technically\*\* \*\*\_what we just told you is incomplete. We have added an additional parameter to incentivize users to **NOT** break their existing LP to enter the Expedition.

To maximize their Expedition winnings, zealous users could break their SUMMIT-FTM LP, then sell their FTM for more SUMMIT to pledge. This would effectively utilize both halves of their LP and double their pledged SUMMIT compared to the original LP's equivalent SUMMIT.

This is not ideal for many reasons. Our solution: the **Incentive Multiplier**.

The Incentive Multiplier boosts the value of the **equivalent SUMMIT** coming from the LP, raising it above the SUMMIT token amount that _**would**_ have come out of the LP breaking transaction. This means that part of the native token (FTM) side of the LP is being used to calculate the user's winnings.

With an Incentive Multiplier of 1.4 , the previous example from above would now look like:

```
Expedition Pledged Amounts
  5 SUMMIT-FTM LP
  15 SUMMIT token

    
            
Example LP Break Transaction On Exchange
  5 SUMMIT-FTM LP ==> 20 SUMMIT token + 45 FTM
  ∴ exchange rate = 1 SUMMIT-FTM LP ==> 4 SUMMIT token
  
Incentive Multiplier
  20 SUMMIT token (from 5 SUMMIT-FTM LP) * 1.4X incentive multiplier
  = 28 SUMMIT token



Total SUMMIT pledged in Expedition
  28 SUMMIT token (from 5 SUMMIT-FTM LP with 1.4x incentive multiplier)
+ 15 SUMMIT token
-----------------
  43 SUMMIT token
```

_**The Incentive Multiplier starts at 1X and has a 72 hour update timelock.**_

## \*\* \*\*
