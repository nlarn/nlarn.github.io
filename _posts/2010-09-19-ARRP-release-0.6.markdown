---
layout: post
title:  ARRP Release 0.6
date:   2010-09-19 11:08:00 +0200
categories: release ARRP
---

It's our pleasure to announce a brand new version of NLarn for this years ARRP.  This is a major release which adds tons of new features.

[Download your copy from Sourceforge](http://sourceforge.net/projects/nlarn/files/nlarn/0.6/) and we hope you enjoy playing NLarn. We are looking forward to hear from you!

## Changes in this version:

### General
* Changed the flow of game time management and made actions
  interruptable. The result of an action that takes multiple turns
  is revealed after elapsing the required number of turns.
* Stats are now chosen from one of four fixed stat packages with high
  points in strength, constitution, dexterity and intelligence,
  respectively. At game start, the player is prompted to choose one or a
  random character stat set. This choice can be defined on the command
  line or in the ini file.
* Nuked the charisma stat.
* Added an auto-travel feature which allows to select a target with 'T'
  (features can be selected by their glyph) and to continue travel
  interrupted by e.g. a monster with 'C'.
* Automated saving points allow continuing games after crashes.
* Integrated Lua interpreter into the game. Moved monster data to external
  lua file.
* Movement speed is reduced when burdened. When going down a level while
  burdened, damage may be caused.
* Give a warning if the effects levitation, wall-walk or protection are
  about to time out.

{% include image.html url="/images/nlarn-fading-levitation_2010-07-23.png" caption="Fading levitation" max_width="300px" %}

* Use inverted colours to highlight stationary objects or traps with
  items on them.
* The statistics which are collected during the game play have been
  enhanced. A new statistics counter, "acts of vandalism", has been added,
  which counts destruction of walls, statues etc. via vaporisation, and
  also all those looted thrones.
* Added some new fortune/speech phrases.

### Spells

* Make spell casting success depend on Int, spell level and knowledge.
* Magic missile is now a single-target spell, and sonic spear has been
  upped to level 2.
* Lightning deals double damage against flying monsters. Player also
  takes double damage from lightning while levitating.
* Make finger of death less likely to succeed against undead or demons.
* Make polymorph less likely to succeed the higher the monster level.
  A polymorphed monster that can't survive in its current place gets
  killed.
* Tweaked the spell "alter reality".
* Redesigned the spells "phantasmal forces" and "scare monsters".
  Phantasmal forces affects a single monster, scare monsters affects all
  monsters that surround the player.
* Flood effect areas shrink as they time out.

### Monsters

* Overhauled to-hit calculations, now takes into account monster/player
  speed ratio. Saner AC values.
* Modified the monster generation to have a more interesting mix of
  monsters on a level, including out-of-depth monsters.
* Made some monsters significantly more rare.
* Tweaked monsters' gold property to make gold drops less reliable.
* Added ranged attacks: hell hounds and red dragons breathe bursts of
  fire, the green dragon spits poison and the platinum dragon can use its
  psionic attack at a distance. Gaze attacks are now possible at a
  distance with one third of their base chance.
* Xorns can pass through walls, water lords can swim.
* The ziller now has a random stat loss attack. The assassin beetle now has
  the poison attack. The green urchin and the lama nobe can now cause
  blindness.
* Hell hounds, red dragons and demon princes are resistant to fire, some
  monsters have sleep or poison resistance.
* Make monsters regenerate more often.
* Adjust some monsters' colours, get rid of dark grey monsters.
* A nymph will only steal a random amount of an item when the player
  has a larger number of that item.
* Populate the town with town people. Eradicate fortune cookies in favour
  of the talkative town people.

### Items

* New amulet type: reflection. Reflects breath and gaze attacks.
* Add new potion "recovery" healing stat drains, including dizziness.
* Added a "potion of levitation", which allows to float over water or lava.
* Implemented a "potion of power", which restores MP.
* Always show wielded weapon in the main view.
* Give blessed items a 50% chance to resist erosion/disenchantment.
* Blessed weapons do 50% bonus damage against undead and demons.
* Blessed potions' effects last longer.
* Blessed potions of object and treasure detection detect items carried
  by monsters.
* Improved blessed scrolls of magic mapping and potions of instant healing:
  a blessed scroll of magic mapping now also reveals all traps on the
  level, and a blessed potion of instant healing also heals poison,
  confusion, and blindness.
* For blessed genocide scrolls, allow to choose out of same-glyph monsters.
* Blessed scrolls of enchant armour/weapon now repair damage and may give
  a bonus enchantment.
* Uncursed identify scrolls allow identifying up to three items, averaging
  at two. Blessed scrolls affect all carried items, as before.
* Improve the scroll of "create artifact": now only generates amulets,
  rings, books, potions or scrolls.
* Life protection is only permanent with blessed scrolls.
* Blessed time warp scrolls are more likely to go farther back.
* Change potions of plain water to holy water, which enables the player
  to bless items.
* Refuse to use books, scrolls and potions which are known to be cursed.
* When wearing cursed armour, its curse status is identified immediately.
* If a carried container is destroyed, its contents spill on the floor.
* Added a more detailed item description for some item types.

### Levels

* Added rivers and lakes. Spells can now be cast across water and lava,
  and flying monsters can cross it. If a monster is killed over water/lava,
  all carried items get destroyed, except for the unique items which get
  teleported elsewhere on the level.

{% include image.html url="/images/nlarn-underground-lake_2010-07-23.png" caption="An underground lake" max_width="300px" %}

* Overhaul altar prayer. Make altar donations also cure poisoning
  and other afflictions, including stat loss other than strength or
  dexterity.
* Added some special effects when vaporising fountains or altars.

* Display remembered traps in their colour, now different by type.
* Pits actually trap player and monsters and restrict vision while
  trapped.
* Cause damage by falling through trap doors.
* Make trap poisoning less likely on the early levels.
* Make dexterity influence the likelihood of evading a trap.
* While burdened, increase the chance of triggering a trap.

## Fixed bugs:

* Store auto pickup settings in the saved game.
* Expire effects correctly when doing a time warp.
* Disallow using stairs while paralysed.
* Fix area effect spells not working under certain circumstances.
* Fix poisoning not scaling correctly with difficulty.
* Fix various information leaks about unknown mimics.
* Fixed remove curse scrolls leaking cursedness information for items
  of unknown curse status.
* Fix walk-through-walls not working when blind.
* Fix genocided monsters sometimes still being generated.
* Fix flickering inventory.
* Don't let books too difficult to understand increase Intelligence.
* Display correct count of items a nymph steals.
* Disable showing an item bonus in the identified items list.
* Changed many messages to present tense.
* Fixed lots of typos.
