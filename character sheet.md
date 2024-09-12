---
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

passive:
  perception: 5
  investigation: 5
  insight: 5
---


## Ability Scores
| <nobr>Stat</nobr> | <nobr>Score</nobr> | <nobr>#</nobr> | <nobr>Stat</nobr> | <nobr>Score</nobr> | <nobr>#</nobr> |
| :---: | :---: | :---: | :---: | :---: | :---: |
| STR | `INPUT[number(class(nb-mb-css)):rsheet#abilityScores.str]` | `VIEW[{rsheet#abilityMods.str}]` | INT | `INPUT[number(class(nb-mb-css)):rsheet#abilityScores.int]` | `VIEW[{rsheet#abilityMods.int}]` |
| DEX | `INPUT[number(class(nb-mb-css)):rsheet#abilityScores.dex]` | `VIEW[{rsheet#abilityMods.dex}]` | WIS | `INPUT[number(class(nb-mb-css)):rsheet#abilityScores.wis]` | `VIEW[{rsheet#abilityMods.wis}]` |
| CON | `INPUT[number(class(nb-mb-css)):rsheet#abilityScores.con]` | `VIEW[{rsheet#abilityMods.con}]` | CHA | `INPUT[number(class(nb-mb-css)):rsheet#abilityScores.cha]` | `VIEW[{rsheet#abilityMods.cha}]` |
## Saving Throw
| <nobr>Stat</nobr> | <nobr>Prof</nobr> | <nobr>Total</nobr> | <nobr>Stat</nobr> | <nobr>Prof</nobr> | <nobr>Total</nobr> |
|:-----------------:|:-----------------:|:------------------:|:-----------------:|:-----------------:|:------------------:|
| STR  | `INPUT[toggle:rsheet#savingThrows.str]` | `VIEW[{rsheet#abilityMods.str}+{rsheet#pBonus}*{rsheet#savingThrows.str}]` | DEX  | `INPUT[toggle:rsheet#savingThrows.dex]` | `VIEW[{rsheet#abilityMods.dex}+{rsheet#pBonus}*{rsheet#savingThrows.dex}]` |
| CON  | `INPUT[toggle:rsheet#savingThrows.con]` | `VIEW[{rsheet#abilityMods.con}+{rsheet#pBonus}*{rsheet#savingThrows.con}]` | INT  | `INPUT[toggle:rsheet#savingThrows.int]` | `VIEW[{rsheet#abilityMods.int}+{rsheet#pBonus}*{rsheet#savingThrows.int}]` |
| WIS  | `INPUT[toggle:rsheet#savingThrows.wis]` | `VIEW[{rsheet#abilityMods.wis}+{rsheet#pBonus}*{rsheet#savingThrows.wis}]` | CHA  | `INPUT[toggle:rsheet#savingThrows.cha]` | `VIEW[{rsheet#abilityMods.cha}+{rsheet#pBonus}*{rsheet#savingThrows.cha}]` |

## Level
Level: `INPUT[number(class(nb-mb-css)):rsheet#Level]`

## Passive Skills
| Perception | Investigation | Stealth |
|:----------:|:-------------:|:-------:|
|`VIEW[{rsheet#passive.perception}]`|`VIEW[{rsheet#passive.investigation}]`           |`VIEW[{rsheet#passive.stealth}]`|
## Skills
| Skill             | Expertise                                                 | Proficiency                               | Total                                                             |
| :---------------- | :-------------------------------------------------------: | :---------------------------------------: | :----------------------------------------------------------------: |
| Acrobatics        | `INPUT[toggle(class(star)):rsheet#expertise.acrobatics]`   | `INPUT[toggle:rsheet#skills.acrobatics]`  | `VIEW[{rsheet#abilityMods.dex}+{rsheet#skills.acrobatics}*{rsheet#pBonus}+{rsheet#expertise.acrobatics}*{rsheet#pBonus}]`  |
| Animal Handling   | `INPUT[toggle(class(star)):rsheet#expertise.animalHandling]`| `INPUT[toggle:rsheet#skills.animalHandling]`| `VIEW[{rsheet#abilityMods.wis}+{rsheet#skills.animalHandling}*{rsheet#pBonus}+{rsheet#expertise.animalHandling}*{rsheet#pBonus}]`|
| Arcana            | `INPUT[toggle(class(star)):rsheet#expertise.arcana]`       | `INPUT[toggle:rsheet#skills.arcana]`     | `VIEW[{rsheet#abilityMods.int}+{rsheet#skills.arcana}*{rsheet#pBonus}+{rsheet#expertise.arcana}*{rsheet#pBonus}]`       |
| Athletics         | `INPUT[toggle(class(star)):rsheet#expertise.athletics]`    | `INPUT[toggle:rsheet#skills.athletics]`  | `VIEW[{rsheet#abilityMods.str}+{rsheet#skills.athletics}*{rsheet#pBonus}+{rsheet#expertise.athletics}*{rsheet#pBonus}]`    |
| Deception         | `INPUT[toggle(class(star)):rsheet#expertise.deception]`    | `INPUT[toggle:rsheet#skills.deception]`  | `VIEW[{rsheet#abilityMods.cha}+{rsheet#skills.deception}*{rsheet#pBonus}+{rsheet#expertise.deception}*{rsheet#pBonus}]`    |
| History           | `INPUT[toggle(class(star)):rsheet#expertise.history]`      | `INPUT[toggle:rsheet#skills.history]`    | `VIEW[{rsheet#abilityMods.int}+{rsheet#skills.history}*{rsheet#pBonus}+{rsheet#expertise.history}*{rsheet#pBonus}]`      |
| Insight           | `INPUT[toggle(class(star)):rsheet#expertise.insight]`      | `INPUT[toggle:rsheet#skills.insight]`    | `VIEW[{rsheet#abilityMods.wis}+{rsheet#skills.insight}*{rsheet#pBonus}+{rsheet#expertise.insight}*{rsheet#pBonus}]`      |
| Intimidation      | `INPUT[toggle(class(star)):rsheet#expertise.intimidation]` | `INPUT[toggle:rsheet#skills.intimidation]`| `VIEW[{rsheet#abilityMods.cha}+{rsheet#skills.intimidation}*{rsheet#pBonus}+{rsheet#expertise.intimidation}*{rsheet#pBonus}]` |
| Investigation     | `INPUT[toggle(class(star)):rsheet#expertise.investigation]`| `INPUT[toggle:rsheet#skills.investigation]`| `VIEW[{rsheet#abilityMods.int}+{rsheet#skills.investigation}*{rsheet#pBonus}+{rsheet#expertise.investigation}*{rsheet#pBonus}]`|
| Medicine          | `INPUT[toggle(class(star)):rsheet#expertise.medicine]`     | `INPUT[toggle:rsheet#skills.medicine]`   | `VIEW[{rsheet#abilityMods.wis}+{rsheet#skills.medicine}*{rsheet#pBonus}+{rsheet#expertise.medicine}*{rsheet#pBonus}]`     |
| Nature            | `INPUT[toggle(class(star)):rsheet#expertise.nature]`       | `INPUT[toggle:rsheet#skills.nature]`     | `VIEW[{rsheet#abilityMods.int}+{rsheet#skills.nature}*{rsheet#pBonus}+{rsheet#expertise.nature}*{rsheet#pBonus}]`       |
| Perception        | `INPUT[toggle(class(star)):rsheet#expertise.perception]`   | `INPUT[toggle:rsheet#skills.perception]` | `VIEW[{rsheet#abilityMods.wis}+{rsheet#skills.perception}*{rsheet#pBonus}+{rsheet#expertise.perception}*{rsheet#pBonus}]`   |
| Performance       | `INPUT[toggle(class(star)):rsheet#expertise.performance]`  | `INPUT[toggle:rsheet#skills.performance]`| `VIEW[{rsheet#abilityMods.cha}+{rsheet#skills.performance}*{rsheet#pBonus}+{rsheet#expertise.performance}*{rsheet#pBonus}]`  |
| Persuasion        | `INPUT[toggle(class(star)):rsheet#expertise.persuasion]`   | `INPUT[toggle:rsheet#skills.persuasion]` | `VIEW[{rsheet#abilityMods.cha}+{rsheet#skills.persuasion}*{rsheet#pBonus}+{rsheet#expertise.persuasion}*{rsheet#pBonus}]`   |
| Religion          | `INPUT[toggle(class(star)):rsheet#expertise.religion]`     | `INPUT[toggle:rsheet#skills.religion]`   | `VIEW[{rsheet#abilityMods.int}+{rsheet#skills.religion}*{rsheet#pBonus}+{rsheet#expertise.religion}*{rsheet#pBonus}]`     |
| Sleight of Hand   | `INPUT[toggle(class(star)):rsheet#expertise.sleightOfHand]`| `INPUT[toggle:rsheet#skills.sleightOfHand]`| `VIEW[{rsheet#abilityMods.dex}+{rsheet#skills.sleightOfHand}*{rsheet#pBonus}+{rsheet#expertise.sleightOfHand}*{rsheet#pBonus}]`|
| Stealth           | `INPUT[toggle(class(star)):rsheet#expertise.stealth]`      | `INPUT[toggle:rsheet#skills.stealth]`    | `VIEW[{rsheet#abilityMods.dex}+{rsheet#skills.stealth}*{rsheet#pBonus}+{rsheet#expertise.stealth}*{rsheet#pBonus}]`      |
| Survival          | `INPUT[toggle(class(star)):rsheet#expertise.survival]`     | `INPUT[toggle:rsheet#skills.survival]`   | `VIEW[{rsheet#abilityMods.wis}+{rsheet#skills.survival}*{rsheet#pBonus}+{rsheet#expertise.survival}*{rsheet#pBonus}]`     |


# Other proficiencies 
 |
 ---|---|
[[Languages]] | `=replace(join(this.languages, ","),",","<BR>")` |
[[Weapons]]| `=replace(join(this.weapons, ","),",","<BR>")` |
[[Armor]] | `=replace(join(this.armor, ","),",","<BR>")` |
[[Tools]] | `=replace(join(link(this.tools), ","),",","<BR>")` |







`VIEW[floor(({rsheet#abilityScores.str}-10)/2)][math(hidden):rsheet#abilityMods.str]`
`VIEW[floor(({rsheet#abilityScores.dex}-10)/2)][math(hidden):rsheet#abilityMods.dex]`
`VIEW[floor(({rsheet#abilityScores.con}-10)/2)][math(hidden):rsheet#abilityMods.con]`
`VIEW[floor(({rsheet#abilityScores.int}-10)/2)][math(hidden):rsheet#abilityMods.int]`
`VIEW[floor(({rsheet#abilityScores.wis}-10)/2)][math(hidden):rsheet#abilityMods.wis]`
`VIEW[floor(({rsheet#abilityScores.cha}-10)/2)][math(hidden):rsheet#abilityMods.cha]`

`VIEW[ceil({rsheet#Level}/4)+1][math(hidden):rsheet#pBonus]`

`VIEW[{rsheet#abilityMods.wis}+10][math(hidden):rsheet#passive.perception]`
`VIEW[{rsheet#abilityMods.int}+10][math(hidden):rsheet#passive.investigation]`
`VIEW[{rsheet#abilityMods.dex}+10][math(hidden):rsheet#passive.stealth]`






