---
pArmor:
  prof: simple, medium, heavy
  nprof: 
pWeapon:
  prof: simple, martial
  nprof: 
HPL1: 10
nHDice: 20
skillChoice:
  skill1: Animal Handling
  skill2: Athletics
---

HP at level 1: `VIEW[{characterSheet#abilityMods.con}+10][math:HPL1]`
HP above level 1: 
Hit Dice: `VIEW[{characterSheet#Level}][math:nHDice]`
Second Wind Usage: `VIEW[{ability.secondWind}]`
Skill 1: `VIEW[{skillChoice.skill1}]`
Skill 2: `VIEW[{skillChoice.skill2}]`
Fighting Style: `VIEW[{ability.fightingStyle}]`

Armor:  `VIEW[{pArmor.prof}]`
Weapon:  `VIEW[{pWeapon.prof}]`


skills:
Choice 1:`INPUT[inlineSelect(option(Acrobatics), option(Animal Handling), option(Athletics), option(History), option(Insight), option(Intimidation), option(Perception), option(Survival)):skillChoice.skill1]`

Choice 2:`INPUT[inlineSelect(option(Acrobatics), option(Animal Handling), option(Athletics), option(History), option(Insight), option(Intimidation), option(Perception), option(Survival)):skillChoice.skill2]`

Fighting Style: `INPUT[inlineSelect(option(Archery), option(Defense), option(Dueling), option(Great Weapon Fighting), option(Protection), option(Two-Weapon Fighting)):ability.fightingStyle]`


>[!hint | bg-c-red]+ Second Wind (`VIEW[{ability.secondWind}]`/1) `INPUT[slider(minValue(0), maxValue(1), addLabels):ability.secondWind]`







