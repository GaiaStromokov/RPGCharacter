---
plClass: Barbarian
abilityScores:
  str: 10
  dex: 10
  int: 10
  cha: 10
  wis: 10
  con: 10
abilityMods:
  str: 0
  dex: 0
  con: 0
  int: 0
  wis: 0
  cha: 0
savingThrows:
  str: false
skills:
  acrobatics: false
expertise:
  deception: false
passive:
  perception: 10
  investigation: 10
  insight: 5
  stealth: 10
pBonus: 6
Level: 20
race:
  name: 
  subRace: 
  traits: 
pLevel: 1
class: 
feats: 
background: 
languages: 
resistances: 
hp: 1
tempHP: 0
ac: 10
prof: 2
---


## Ability Scores
| <nobr>Stat</nobr> | <nobr>Score</nobr> | <nobr>#</nobr> | <nobr>Stat</nobr> | <nobr>Score</nobr> | <nobr>#</nobr> |
| :---: | :---: | :---: | :---: | :---: | :---: |
| STR | `INPUT[number(class(nb-mb-css)):abilityScores.str]` | `VIEW[{abilityMods.str}]` | INT | `INPUT[number(class(nb-mb-css)):abilityScores.int]` | `VIEW[{abilityMods.int}]` |
| DEX | `INPUT[number(class(nb-mb-css)):abilityScores.dex]` | `VIEW[{abilityMods.dex}]` | WIS | `INPUT[number(class(nb-mb-css)):abilityScores.wis]` | `VIEW[{abilityMods.wis}]` |
| CON | `INPUT[number(class(nb-mb-css)):abilityScores.con]` | `VIEW[{abilityMods.con}]` | CHA | `INPUT[number(class(nb-mb-css)):abilityScores.cha]` | `VIEW[{abilityMods.cha}]` |
## Saving Throw
| <nobr>Stat</nobr> | <nobr>Prof</nobr> | <nobr>Total</nobr> | <nobr>Stat</nobr> | <nobr>Prof</nobr> | <nobr>Total</nobr> |
|:-----------------:|:-----------------:|:------------------:|:-----------------:|:-----------------:|:------------------:|
| STR  | `INPUT[toggle:savingThrows.str]` | `VIEW[{abilityMods.str}+{pBonus}*{savingThrows.str}]` | DEX  | `INPUT[toggle:savingThrows.dex]` | `VIEW[{abilityMods.dex}+{pBonus}*{savingThrows.dex}]` |
| CON  | `INPUT[toggle:savingThrows.con]` | `VIEW[{abilityMods.con}+{pBonus}*{savingThrows.con}]` | INT  | `INPUT[toggle:savingThrows.int]` | `VIEW[{abilityMods.int}+{pBonus}*{savingThrows.int}]` |
| WIS  | `INPUT[toggle:savingThrows.wis]` | `VIEW[{abilityMods.wis}+{pBonus}*{savingThrows.wis}]` | CHA  | `INPUT[toggle:savingThrows.cha]` | `VIEW[{abilityMods.cha}+{pBonus}*{savingThrows.cha}]` |

## Level
Level: `INPUT[number(class(nb-mb-css)):Level]`

## Passive Skills
| Perception | Investigation | Stealth |
|:----------:|:-------------:|:-------:|
|`VIEW[{passive.perception}]`|`VIEW[{passive.investigation}]`           |`VIEW[{passive.stealth}]`|
## Skills
| Skill           |                          Expertise                           |                 Proficiency                  |                                                               Total                                                               |
| :-------------- | :----------------------------------------------------------: | :------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------: |
| Acrobatics      |   `INPUT[toggle(class(star)):expertise.acrobatics]`   |   `INPUT[toggle:skills.acrobatics]`   |     `VIEW[{abilityMods.dex}+{skills.acrobatics}*{pBonus}+{expertise.acrobatics}*{pBonus}]`     |
| Animal Handling | `INPUT[toggle(class(star)):expertise.animalHandling]` | `INPUT[toggle:skills.animalHandling]` | `VIEW[{abilityMods.wis}+{skills.animalHandling}*{pBonus}+{expertise.animalHandling}*{pBonus}]` |
| Arcana          |     `INPUT[toggle(class(star)):expertise.arcana]`     |     `INPUT[toggle:skills.arcana]`     |         `VIEW[{abilityMods.int}+{skills.arcana}*{pBonus}+{expertise.arcana}*{pBonus}]`         |
| Athletics       |   `INPUT[toggle(class(star)):expertise.athletics]`    |   `INPUT[toggle:skills.athletics]`    |      `VIEW[{abilityMods.str}+{skills.athletics}*{pBonus}+{expertise.athletics}*{pBonus}]`      |
| Deception       |   `INPUT[toggle(class(star)):expertise.deception]`    |   `INPUT[toggle:skills.deception]`    |      `VIEW[{abilityMods.cha}+{skills.deception}*{pBonus}+{expertise.deception}*{pBonus}]`      |
| History         |    `INPUT[toggle(class(star)):expertise.history]`     |    `INPUT[toggle:skills.history]`     |        `VIEW[{abilityMods.int}+{skills.history}*{pBonus}+{expertise.history}*{pBonus}]`        |
| Insight         |    `INPUT[toggle(class(star)):expertise.insight]`     |    `INPUT[toggle:skills.insight]`     |        `VIEW[{abilityMods.wis}+{skills.insight}*{pBonus}+{expertise.insight}*{pBonus}]`        |
| Intimidation    |  `INPUT[toggle(class(star)):expertise.intimidation]`  |  `INPUT[toggle:skills.intimidation]`  |   `VIEW[{abilityMods.cha}+{skills.intimidation}*{pBonus}+{expertise.intimidation}*{pBonus}]`   |
| Investigation   | `INPUT[toggle(class(star)):expertise.investigation]`  | `INPUT[toggle:skills.investigation]`  |  `VIEW[{abilityMods.int}+{skills.investigation}*{pBonus}+{expertise.investigation}*{pBonus}]`  |
| Medicine        |    `INPUT[toggle(class(star)):expertise.medicine]`    |    `INPUT[toggle:skills.medicine]`    |       `VIEW[{abilityMods.wis}+{skills.medicine}*{pBonus}+{expertise.medicine}*{pBonus}]`       |
| Nature          |     `INPUT[toggle(class(star)):expertise.nature]`     |     `INPUT[toggle:skills.nature]`     |         `VIEW[{abilityMods.int}+{skills.nature}*{pBonus}+{expertise.nature}*{pBonus}]`         |
| Perception      |   `INPUT[toggle(class(star)):expertise.perception]`   |   `INPUT[toggle:skills.perception]`   |     `VIEW[{abilityMods.wis}+{skills.perception}*{pBonus}+{expertise.perception}*{pBonus}]`     |
| Performance     |  `INPUT[toggle(class(star)):expertise.performance]`   |  `INPUT[toggle:skills.performance]`   |    `VIEW[{abilityMods.cha}+{skills.performance}*{pBonus}+{expertise.performance}*{pBonus}]`    |
| Persuasion      |   `INPUT[toggle(class(star)):expertise.persuasion]`   |   `INPUT[toggle:skills.persuasion]`   |     `VIEW[{abilityMods.cha}+{skills.persuasion}*{pBonus}+{expertise.persuasion}*{pBonus}]`     |
| Religion        |    `INPUT[toggle(class(star)):expertise.religion]`    |    `INPUT[toggle:skills.religion]`    |       `VIEW[{abilityMods.int}+{skills.religion}*{pBonus}+{expertise.religion}*{pBonus}]`       |
| Sleight of Hand | `INPUT[toggle(class(star)):expertise.sleightOfHand]`  | `INPUT[toggle:skills.sleightOfHand]`  |  `VIEW[{abilityMods.dex}+{skills.sleightOfHand}*{pBonus}+{expertise.sleightOfHand}*{pBonus}]`  |
| Stealth         |    `INPUT[toggle(class(star)):expertise.stealth]`     |    `INPUT[toggle:skills.stealth]`     |        `VIEW[{abilityMods.dex}+{skills.stealth}*{pBonus}+{expertise.stealth}*{pBonus}]`        |
| Survival        |    `INPUT[toggle(class(star)):expertise.survival]`    |    `INPUT[toggle:skills.survival]`    |       `VIEW[{abilityMods.wis}+{skills.survival}*{pBonus}+{expertise.survival}*{pBonus}]`       |


# Other proficiencies 
 |
 ---|---|
[[Languages]] | `=replace(join(this.languages, ","),",","<BR>")` |
[[Weapons]]| `=replace(join(this.weapons, ","),",","<BR>")` |
[[Armor]] | `=replace(join(this.armor, ","),",","<BR>")` |
[[Tools]] | `=replace(join(link(this.tools), ","),",","<BR>")` |







`VIEW[floor(({abilityScores.str}-10)/2)][math(hidden):abilityMods.str]`
`VIEW[floor(({abilityScores.dex}-10)/2)][math(hidden):abilityMods.dex]`
`VIEW[floor(({abilityScores.con}-10)/2)][math(hidden):abilityMods.con]`
`VIEW[floor(({abilityScores.int}-10)/2)][math(hidden):abilityMods.int]`
`VIEW[floor(({abilityScores.wis}-10)/2)][math(hidden):abilityMods.wis]`
`VIEW[floor(({abilityScores.cha}-10)/2)][math(hidden):abilityMods.cha]`

`VIEW[ceil({Level}/4)+1][math(hidden):pBonus]`

`VIEW[{abilityMods.wis}+10][math(hidden):passive.perception]`
`VIEW[{abilityMods.int}+10][math(hidden):passive.investigation]`
`VIEW[{abilityMods.dex}+10][math(hidden):passive.stealth]`






