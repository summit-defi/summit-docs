# Cosmic Deities

![](<../.gitbook/assets/DEITIES Masthead (1).jpg>)

{% hint style="success" %}
#### The fate of each round of an Expedition is decided by two _warring Deities_, each fighting to earn or steal the pot.
{% endhint %}

## The Cosmic Deities

Titans fight above to guide the Sherpa's expedition. Untold riches are the reward for a successful search.

The Cosmic Bull guides the way, leading the Sherpa to glory.

The Cosmic Bear deceives, distracts, and creates false treasure.

**If the Sherpa is successful in his search, the treasure is distributed to the Cosmic Bull. If not, it is stolen by the Cosmic Bear.**

While Totems have a consistent chance of winning, Deities are different.

Each round of an Expedition the Deities change in strength _(relative deity strength below)_, meaning each round of the Expedition has a different chance of the Cosmic Bull successfully guiding the Sherpa to riches.

## Relative Deity Strength

Each round of an Expedition, the Deities either grow stronger or weaker comparatively. The stronger a Deity the higher the chance it wins the round of the expedition, as follows:

```
                COSMIC BULL                        COSMIC BEAR
0|------------------------------------------|----------------------|99
               strength:  67                      strength:  32             
```

### Choosing a Winning Deity

1. When a round ends, a random number is chosen between 0 - 99 inclusive.
2. If this number falls between 0 and the Cosmic Bull's strength (exclusive) then the Cosmic Bull wins the round.
3. Alternatively, if the number falls between the Cosmic Bear's strength (inclusive) and 99 (inclusive) then the Cosmic Bear will win the round.

```
Relative Deity Strength:
                 COSMIC BULL                        COSMIC BEAR
 0|------------------------------------------|----------------------|99
                strength:  67                      strength:  32    

               
Winner Visualization:               
  [------------------------------------------)
              cosmic bull win
                                             [----------------------]
                                                  cosmic bear win
               
With Values:               
 N            : Random Number 0-99 Inclusive
 [0, 67)      : COSMIC BULL WIN
 [67, 99]     : COSMIC BEAR WIN
```

## Deity Strength

The **deity strengths** for a round are tied to the result of the previous round:

1. The same round end random number 0 - 99 inclusive as described above is used.
2. The random number is multiplied by 0.4 and added to 50.
3. The result is always 50 - 90, and is used as the chance of success of the next round.

> Round A results in a random number of 90 (Bear win)
>
> &#x20;90\*.4 = 36 + 50 => Next round change of Cosmic Bull winning is 86%

> Round X results in a random number of 0 (Bull win)
>
> \*0.4 = 0 + 50 => Next round chance of Cosmic Bull winning is 50%

In short, there is a self balance of Deity Strength, but the random number is always **completely random.**

Tying the chance of success to the previous rounds random number increases the perceived fairness of the Expedition.  Although given the random chance to win in any case it's always fair. &#x20;
