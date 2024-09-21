---
HPL1: 12
hDice: 8
nHDice: 20
skillChoice:
  skill1: history
  skill2: history
ability:
  fightingStyle: dueling
  secondWind: 1
asci1stat:
asci1bonus:
asci2stat:
asci2bonus:
---
# Fighter Progression (Level 1-20)
## Skills (Choose 2 from list)
Choice 1: `INPUT[inlineSelect(option(Acrobatics), option(Animal Handling), option(Athletics), option(History), option(Insight), option(Intimidation), option(Perception), option(Survival)):skillChoice.skill1]`  
Choice 2: `INPUT[inlineSelect(option(Acrobatics), option(Animal Handling), option(Athletics), option(History), option(Insight), option(Intimidation), option(Perception), option(Survival)):skillChoice.skill2]`

---

## Level 1

- **Hit Points**: `VIEW[{rsheet#abilityMods.con}+10][math:HPL1]`
- **Fighting Style**: `INPUT[inlineSelect(option(Archery), option(Defense), option(Dueling), option(Great Weapon Fighting), option(Protection), option(Two-Weapon Fighting)):ability.fightingStyle]`
- **Second Wind**: `VIEW[{ability.secondWind}]` / 1 use  
  `INPUT[slider(minValue(0), maxValue(1), addLabels):ability.secondWind]`

## Level 2

- **Action Surge**: `INPUT[slider(minValue(0), maxValue(1), addLabels):ability.actionSurge]` / 1 use

## Level 3

- **Martial Archetype**: (Add subclass choice later)

## Level 4
**Ability Score Improvement
Stat`INPUT[inlineSelect(option(Str), option(Dex), option(Con), option( Int), option(Wis), option(Cha)):asci1stat]` Bonus `INPUT[inlineSelect(option(0), option(1), option(2), option(+1 Intelligence), option(+1 Wisdom), option(+1 Charisma)):asci1score]`

## Level 5

- **Extra Attack**: Gain 1 additional attack.

## Level 6

- **Ability Score Improvement**: (same as level 4)

## Level 7

- **Remarkable Athlete**: Add half proficiency bonus to Strength, Dexterity, or Constitution checks.

## Level 8

- **Ability Score Improvement**: (same as level 4)

## Level 9

- **Indomitable**: `INPUT[slider(minValue(0), maxValue(1), addLabels):ability.indomitable]` / 1 use

## Level 10

- **Second Fighting Style**: `INPUT[inlineSelect(option(Archery), option(Defense), option(Dueling), option(Great Weapon Fighting), option(Protection), option(Two-Weapon Fighting)):ability.secondFightingStyle]`

## Level 11

- **Extra Attack (2)**: Gain 1 additional attack.

## Level 12

- **Ability Score Improvement**: (same as level 4)

## Level 13

- **Indomitable**: `INPUT[slider(minValue(0), maxValue(2), addLabels):ability.indomitable]` / 2 uses

## Level 14

- **Ability Score Improvement**: (same as level 4)

## Level 15

- **Remarkable Athlete**: Increase benefit from earlier Remarkable Athlete.

## Level 16

- **Ability Score Improvement**: (same as level 4)

## Level 17

- **Action Surge**: `INPUT[slider(minValue(0), maxValue(2), addLabels):ability.actionSurge]` / 2 uses  
- **Indomitable**: `INPUT[slider(minValue(0), maxValue(3), addLabels):ability.indomitable]` / 3 uses

## Level 18

- **Survivor**: At the start of each turn, regain hit points equal to 5 + Constitution modifier (if you are below half HP).

## Level 19

- **Ability Score Improvement**: (same as level 4)

## Level 20

- **Extra Attack (3)**: Gain 1 additional attack.





