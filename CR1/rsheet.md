---
plClass: Barbarian
abilityScores:
  str: 10
  dex: 12
  con: 12
  int: 12
  wis: 12
  cha: 12
  Level: 1
abilityMods:
  str: 0
  dex: 1
  con: 1
  int: 1
  wis: 1
  cha: 1
savingThrows:
  str: false
  dex: false
  con: false
  int: false
  wis: false
  cha: false
skills:
  acrobatics: false
  athletics: false
  animalHandling: false
  arcana: false
  atheltics: false
  deception: false
  history: false
  insight: false
  intimidation: false
  investigation: false
  medicine: false
  nature: false
  perception: false
  performance: false
  persuasion: false
  religion: false
  sleightOfHand: false
  stealth: false
  survival: false
expertise:
  acrobatics: false
  athletics: false
  animalHandling: false
  arcana: false
  atheltics: false
  deception: false
  history: false
  insight: false
  intimidation: false
  investigation: false
  medicine: false
  nature: false
  perception: false
  performance: false
  persuasion: false
  religion: false
  sleightOfHand: false
  stealth: false
  survival: false
passive:
  perception: 11
  investigation: 11
  stealth: 11
pBonus: 3
Level: 5
mhp: 0
chp: 20
temphp: 
hitDice: 8
hDUse: 0
AC: 11
Resistances: Poison, Acid, Fire
Immunities: soup
Languages: common, dwarvish, elvish, giant
Weapons: simple, simple
Armor: medium, heavy
Tools: glassblowers, flowers
Inpiration: false
personalityTraits: Communism
Ideals: communism
Bonds: karl marx
Flaws: money
invenSize: 5
spellslot:
  lvl1: 9
  lvl2: 8
  lvl3: 7
  lvl4: 6
  lvl5: 5
  lvl6: 4
  lvl7: 3
  lvl8: 2
  lvl9: 1
spellcast:
  lvl1: 0
  lvl2: 0
  lvl3: 0
  lvl4: 0
  lvl5: 0
  lvl6: 0
  lvl7: 0
  lvl8: 0
  lvl9: 0
WP1:
  name: rapier
  Hit: "`VIEW[{rsheet#abilityMods.dex}+{rsheet#pBonus}]`"
  Damage: 1d8
  Bonus: "`VIEW[{rsheet#abilityMods.dex}]`"
  Property: finesse
  Type: piercing
  Range: melee
  Dmg: ""
WP2:
  name: net
  Hit: "`VIEW[{rsheet#abilityMods.dex}+{rsheet#pBonus}]`"
  Damage: "0"
  Bonus: "`VIEW[{rsheet#abilityMods.dex}]`"
  Property: special, thrown
  Type: entangling
  Range: 5/15
WP3:
  name: greatsword
  Hit: "`VIEW[{rsheet#abilityMods.str}+{rsheet#pBonus}]`"
  Damage: 2d6
  Bonus: "`VIEW[{rsheet#abilityMods.str}]`"
  Property: heavy, two-handed
  Type: slashing
  Range: melee
WP4:
  name: rapier
  Hit: "`VIEW[{rsheet#abilityMods.dex}+{rsheet#pBonus}]`"
  Damage: 1d8
  Bonus: "`VIEW[{rsheet#abilityMods.dex}]`"
  Property: finesse
  Type: piercing
  Range: melee
WP5:
  name: whip
  Hit: "`VIEW[{rsheet#abilityMods.dex}+{rsheet#pBonus}]`"
  Damage: 1d4
  Bonus: "`VIEW[{rsheet#abilityMods.dex}]`"
  Property: finesse, reach
  Type: slashing
  Range: melee
ds:
  s1: false
  s2: false
  s3: false
  f1: false
  f2: false
  f3: false
l0c1: Mending
l0c2: Prestidigitation
l3c1: Fireball
l9c1: Wish
l1c1: Aid
l0c3: Druidcraft
l4c1: ""
l6c1: Prismatic_Spray
---

