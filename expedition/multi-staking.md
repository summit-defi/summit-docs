# Expedition Multi-Staking

{% hint style="success" %}
#### TL,DR:

#### Multi-Staking allows users to stake _either- , both- , or any combination of-_ **SUMMIT and SUMMIT-FTM LP in the same Expedition:**

**Total SUMMIT Staked** \(amount used to calculate winnings\) **=  
           staked SUMMIT +  
           SUMMIT** _**inside**_ **staked** _****_**SUMMIT-FTM LP**

_SUMMIT and SUMMIT-FTM LP can be deposited \(or withdrawn\) simultaneously in a single deposit \(or withdraw\) transaction._

_Both SUMMIT and SUMMIT-FTM LP can be elevated into and out of Expeditions from other farms._
{% endhint %}

#### \* This page is not required reading, and is somewhat technical on the Multi-Staking implementation, feel free to skip it if the Hint above was enough for you \*

### The Why

Our users shouldn't be punished for holding SUMMIT-FTM LP token. Forcing our users to break their LP would result in periodic low liquidity, and high price fluctuations, and more frequent impermanent loss; obviously not something we want to do.

Instead, with **Multi-Staking,** you don't have to break your LPs into SUMMIT token to enter and win in the weekly Expeditions.

## Equivalent SUMMIT in LP

If you were to break your SUMMIT-FTM LP, the amount of SUMMIT that you would get out of that transaction is your **equivalent SUMMIT**. Therefore, the total amount of SUMMIT that is used to calculate your winnings is as follows:

```text
Expedition Staked Amounts
  5 SUMMIT-FTM LP
  15 SUMMIT token

        
Example LP Break Transaction On Exchange
  5 SUMMIT-FTM LP ==> 20 SUMMIT token + 45 FTM
  ∴ exchange rate = 1 SUMMIT-FTM LP ==> 4 SUMMIT token


Total SUMMIT staked in Expedition
  20 SUMMIT token (from 5 SUMMIT-FTM LP)
+ 15 SUMMIT token
-----------------
  35 SUMMIT token
```

If the exchange rate were **1 SUMMIT-FTM LP ==&gt; 2 SUMMIT** + XX FTM, all of the following \(if they all win\) would have the exact same **total SUMMIT,** and yield the exact same winnings:

```text
User 1                    User 2                    User 3
10 SUMMIT-FTM LP          3 SUMMIT-FTM LP           0 SUMMIT-FTM LP
0 SUMMIT token            14 SUMMIT token           20 SUMMIT token
```

## SUMMIT-FTM LP Incentive Multiplier

> **At launch, the Incentive Multiplier is set to 1X, meaning no extra boost to equivalent SUMMIT, but can be increased to anywhere between 1X - 2X to incentivize users to not break their LP. We will monitor this and see if 1X is sufficient.**

So _technically ****_what we just told you is incomplete. We have added an additional parameter to incentivize users to **NOT** break their existing LP to enter the Expedition.

To maximize their Expedition winnings, zealous users could break their SUMMIT-FTM LP, then sell their FTM for more SUMMIT to stake. This would effectively utilize both halves of their LP and double their staked SUMMIT compared to the original LP's equivalent SUMMIT. 

This is not ideal for many reasons. Our solution: the **Incentive Multiplier**.

The Incentive Multiplier boosts the value of the **equivalent SUMMIT** coming from the LP, raising it above the SUMMIT token amount that _**would**_ have come out of the LP breaking transaction. This means that part of the native token \(FTM\) side of the LP is being used to calculate the user's winnings.

With an Incentive Multiplier of 1.4 , the previous example from above would now look like:

```text
Expedition Staked Amounts
  5 SUMMIT-FTM LP
  15 SUMMIT token

    
            
Example LP Break Transaction On Exchange
  5 SUMMIT-FTM LP ==> 20 SUMMIT token + 45 FTM
  ∴ exchange rate = 1 SUMMIT-FTM LP ==> 4 SUMMIT token
  
Incentive Multiplier
  20 SUMMIT token (from 5 SUMMIT-FTM LP) * 1.4X incentive multiplier
  = 28 SUMMIT token



Total SUMMIT staked in Expedition
  28 SUMMIT token (from 5 SUMMIT-FTM LP with 1.4x incentive multiplier)
+ 15 SUMMIT token
-----------------
  43 SUMMIT token
```

_**The Incentive Multiplier starts at 1X and has a 72 hour update timelock.**_

##  ****

