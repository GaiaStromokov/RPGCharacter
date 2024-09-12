---
HPL1: 10
hDice: 8
nHDice: 2
parmor:
   simple: true
   medium: true
   heavy: true
pweapon:
   simple: true
   martial: true
ptools
   tools:
savingThrows
   strength: true
   dexterity: false
   constitution: true
   intelligence: false
   wisdom: false
   charisma: false
skillChoice:
   skill1: history
   skill2: history
ability:
   fightingStyle: dueling
   secondWind: 1
---

HP at level 1: `VIEW[{rsheet#abilityMods.con}+10][math:HPL1]`
HP above level 1: 
Hit Dice: `VIEW[{rsheet#Level}][math:nHDice]`
Second Wind Usage: `VIEW[{ability.secondWind}]`
Skill 1: `VIEW[{skillChoice.skill1}]`
Skill 2: `VIEW[{skillChoice.skill2}]`
Fighting Style: `VIEW[{ability.fightingStyle}]`

skills:
Choice 1:`INPUT[inlineSelect(option(Acrobatics), option(Animal Handling), option(Athletics), option(History), option(Insight), option(Intimidation), option(Perception), option(Survival)):skillChoice.skill1]`

Choice 2:`INPUT[inlineSelect(option(Acrobatics), option(Animal Handling), option(Athletics), option(History), option(Insight), option(Intimidation), option(Perception), option(Survival)):skillChoice.skill2]`

Fighting Style: `INPUT[inlineSelect(option(Archery), option(Defense), option(Dueling), option(Great Weapon Fighting), option(Protection), option(Two-Weapon Fighting)):ability.fightingStyle]`


>[!hint | bg-c-red]+ Second Wind (`VIEW[{ability.secondWind}]`/1) `INPUT[slider(minValue(0), maxValue(1), addLabels):ability.secondWind]`







