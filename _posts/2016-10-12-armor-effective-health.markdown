---
layout: post
title:  "Armor and Effective Health"
date:   2016-10-12 16:30:00
categories: wow
---

Armor is a very important stat to tanks, but there's a common misconception that it suffers from "diminishing returns." In a certain sense that's true, but really the right way to look at it is in terms of "effective health." It turns out that *each additional point of armor increases your effective health by the same amount*. What does this mean?

# Armor

First, we should establish what armor does, mechanically. At level 110, armor determines your physical damage reduction using this formula:

$$dr(armor) = \frac{armor}{armor + 7390}$$

This formula comes from [wowwiki](http://wowwiki.wikia.com/wiki/Armor#Armor_damage_reduction_formula), and is specifically designed to have the property we're talking about - that is, so that each point of armor gives the same amount of effective health.

# Effective Health

Effective health is how much unmodified damage you can take before dying. So, if you have a health pool of 1mil, and 50% damage reduction from armor, your effective health for physical damage is 2mil. This formula gives your effective health for a given amount of damage reduction; conceptually, it's asking how many 1 damage hits you can take before dying.

$$eh(health, dr) = \frac{health}{1 - dr}$$

# Diminishing Returns?

The misconception about diminishing returns comes from looking at the amount of damage reduction you get from different amounts of armor. Let's look at a few datapoints.

$$dr(28000) = 0.791$$

$$dr(30000) = 0.802$$

$$dr(32000) = 0.812$$

$$dr(34000) = 0.821$$

Okay, so the jump from 28k to 30k armor gave us 1.1% more DR, while the jump from 32k to 34k gave us only 0.9% more DR.  Doesn't this mean the last 2k is the least valuable? Sort of! Let's look at this again from an effective health perspective though.

Let's say we have a tank with 3mil health and 28k armor, and an enemy that hits for 500k unmodified. How many hits can he take? The answer is his effective health divided by the size of the hit.

$$\frac{eh(3000000, dr(28000))}{500000} = 28.73$$

So this tank can take 28.73 hits before dying. What if they have 30k armor instead?

$$\frac{eh(3000000, dr(30000))}{500000} = 30.36$$

That's 1.6 additional hits before death. Now we can do the same for 32k and 34k armor.

$$\frac{eh(3000000, dr(32000))}{500000} = 31.98$$

$$\frac{eh(3000000, dr(34000))}{500000} = 33.60$$

The difference is still 1.6 hits! So the 2k armor difference from 28k to 30k gives the same increase in survivability, measured by effective health, as the difference from 32k to 34k. This property holds for all possible armor values up to the armor cap, and all possible health values.
