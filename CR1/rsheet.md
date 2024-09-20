---
plClass: Barbarian
abilityScores:
  str: 20
  dex: 15
  con: 15
  int: 15
  wis: 15
  cha: 15
abilityMods:
  str: 5
  dex: 2
  con: 2
  int: 2
  wis: 2
  cha: 2
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
  perception: 12
  investigation: 12
  stealth: 12
pBonus: 6
Level: 20
mhp: 20
chp: 20
temphp: 
hitDice: 8
hDUse: 0
AC: 11
Resistances: Poison, Acid, Fire
Immunities: soup
Languages: common, dwarvish
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
  lvl1: 9
  lvl2: 0
  lvl3: 0
  lvl4: 0
  lvl5: 0
  lvl6: 0
  lvl7: 0
  lvl8: 0
  lvl9: 0
WP1:
  name: shortsword
  Hit: "`VIEW[{rsheet#abilityMods.dex}+{rsheet#pBonus}]`"
  Damage: 1d6
  Bonus: "`VIEW[{rsheet#abilityMods.dex}]`"
  Property: finesse, light
  Type: slashing
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
  name: ""
  Hit: ""
  Damage: ""
  Bonus: ""
  Property: ""
  Type: ""
  Range: ""
ds:
  s1: false
  s2: false
  s3: false
l0c1: Mending
l0c2: Prestidigitation
l3c1: Fireball
l9c1: Wish
l1c1: Aid
l0c3: ""
l4c1: ""
l6c1: Prismatic_Spray
---

