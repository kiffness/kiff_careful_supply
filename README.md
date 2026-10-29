# Careful Supply Runs

An add-on for Mysterial's **Faction Enhancer – War Module** for X4: Foundations.

When a faction invades a sector, it builds a defence station there and sends freighters to supply it. If the
area is still a war zone, those freighters arrive one after another and die, and with the War Module the
invasion keeps going as long as the odd one gets through. Xenon are hit hardest: losing their freighters and
miners is what stalls their economy.

With this add-on, factions are more careful:

- **They notice the losses.** Every supply ship killed while the station is being built is counted for that invasion.
- **They hold back.** After 2 losses within 20 minutes, the remaining freighters pull back to the gate they'd
  enter by, on their own side, and wait.
- **They wait for it to be safe.** At least 5 minutes later, they set off again once there are no armed
  enemies within 25 km of the build site or the entry gate (or their own warships there are twice as strong)
  and no enemy station within 20 km.
- **They know when to quit.** After 6 supply ships lost, or 45 minutes on hold, the invasion retreats, the
  way the game already does when an invasion runs out of time. If you park a defence station by the gate,
  they will give up rather than feed it freighters.

## Requirements

- X4: Foundations 8.00 or later (made and checked against 9.00)
- [Faction Enhancer – War Module](https://steamcommunity.com/sharedfiles/filedetails/?id=1668457361) by Mysterial

Without the War Module this add-on does nothing.

## Install

- **Steam Workshop:** subscribe.
- **Manually:** put the `kiff_careful_supply` folder in `X4 Foundations\extensions\`.

It can be added to or removed from an existing save at any time.

## Compatibility

It doesn't replace any files. It patches two War Module scripts in place:

- `md/FactionSubgoal_SupplyFreighters.xml`: counting losses, holding and releasing the freighters
- `md/FactionGoal_Invade_Space.xml`: giving up the invasion

Other mods that patch the same parts should still work. Mods that replace those files completely won't work with it.

## Checking it works

Start X4 with `-debug all -logfile debug.log` (Steam: right-click X4 → Properties → Launch options). The log
in `Documents\Egosoft\X4\<your id>\debug.log` then shows lines starting with `[Careful Supply]`: one when the
game loads, and one for each supply ship lost, each hold, each resume and each invasion given up.

## Tuning

The numbers are near the top of `md/FactionSubgoal_SupplyFreighters.xml` (`KCS_Settings`). The give-up
limits (6 ships, 45 minutes) are in `md/FactionGoal_Invade_Space.xml`.

## Credits

Made by Kiffness.

All the invasion and supply logic this builds on is [Mysterial](https://forum.egosoft.com/viewtopic.php?p=4836247)'s
Faction Enhancer – War Module. This add-on only patches it at load time and contains none of its files. It's an
unofficial add-on, not made or supported by Mysterial, so please report problems with it here, not to them.
