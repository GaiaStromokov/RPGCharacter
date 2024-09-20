---
equipment:
  - table
  - table
  - table
  - tablre
  - table
  - table
inventory:
  - total
Inventory:
  - inventory
---
---

---

## Level
Level: `INPUT[number(class(nb-mb-css)):CR1/rsheet#Level]`
ProficiencyBonus: `VIEW[**{CR1/rsheet#pBonus}**][text(renderMarkdown)]`
## Ability Scores
| <nobr>Stat</nobr> | <nobr>Score</nobr> | <nobr>#</nobr> | <nobr>Stat</nobr> | <nobr>Score</nobr> | <nobr>#</nobr> |
| :---: | :---: | :---: | :---: | :---: | :---: |
| STR | `INPUT[number(class(nb-mb-css)):CR1/rsheet#abilityScores.str]` | `VIEW[{CR1/rsheet#abilityMods.str}]` | INT | `INPUT[number(class(nb-mb-css)):CR1/rsheet#abilityScores.int]` | `VIEW[{CR1/rsheet#abilityMods.int}]` |
| DEX | `INPUT[number(class(nb-mb-css)):CR1/rsheet#abilityScores.dex]` | `VIEW[{CR1/rsheet#abilityMods.dex}]` | WIS | `INPUT[number(class(nb-mb-css)):CR1/rsheet#abilityScores.wis]` | `VIEW[{CR1/rsheet#abilityMods.wis}]` |
| CON | `INPUT[number(class(nb-mb-css)):CR1/rsheet#abilityScores.con]` | `VIEW[{CR1/rsheet#abilityMods.con}]` | CHA | `INPUT[number(class(nb-mb-css)):CR1/rsheet#abilityScores.cha]` | `VIEW[{CR1/rsheet#abilityMods.cha}]` |
## Saving Throw
| <nobr>Stat</nobr> | <nobr>Prof</nobr> | <nobr>Total</nobr> | <nobr>Stat</nobr> | <nobr>Prof</nobr> | <nobr>Total</nobr> |
|:-----------------:|:-----------------:|:------------------:|:-----------------:|:-----------------:|:------------------:|
| STR  | `INPUT[toggle:CR1/rsheet#savingThrows.str]` | `VIEW[{CR1/rsheet#abilityMods.str}+{CR1/rsheet#pBonus}*{CR1/rsheet#savingThrows.str}]` | DEX  | `INPUT[toggle:CR1/rsheet#savingThrows.dex]` | `VIEW[{CR1/rsheet#abilityMods.dex}+{CR1/rsheet#pBonus}*{CR1/rsheet#savingThrows.dex}]` |
| CON  | `INPUT[toggle:CR1/rsheet#savingThrows.con]` | `VIEW[{CR1/rsheet#abilityMods.con}+{CR1/rsheet#pBonus}*{CR1/rsheet#savingThrows.con}]` | INT  | `INPUT[toggle:CR1/rsheet#savingThrows.int]` | `VIEW[{CR1/rsheet#abilityMods.int}+{CR1/rsheet#pBonus}*{CR1/rsheet#savingThrows.int}]` |
| WIS  | `INPUT[toggle:CR1/rsheet#savingThrows.wis]` | `VIEW[{CR1/rsheet#abilityMods.wis}+{CR1/rsheet#pBonus}*{CR1/rsheet#savingThrows.wis}]` | CHA  | `INPUT[toggle:CR1/rsheet#savingThrows.cha]` | `VIEW[{CR1/rsheet#abilityMods.cha}+{CR1/rsheet#pBonus}*{CR1/rsheet#savingThrows.cha}]` |

## Passive Skills
| Perception | Investigation | Stealth |
|:----------:|:-------------:|:-------:|
|`VIEW[{CR1/rsheet#passive.perception}]`|`VIEW[{CR1/rsheet#passive.investigation}]`           |`VIEW[{CR1/rsheet#passive.stealth}]`|

## HP/AC
| Hit Points  | `INPUT[number:CR1/rsheet#hp]`                           |
| ----------- | ------------------------------------------------------- |
| Temp HP     | `INPUT[number:CR1/rsheet#temphp]`                       |
| Hit dice    | `VIEW[{CR1/rsheet#Level}]`d`VIEW[{CR1/rsheet#hitDice}]` :  HD Left == `INPUT[number:CR1/rsheet#hDUse]`   |
| Initiative  | `VIEW[{CR1/rsheet#abilityMods.dex}]`                    |
| AC          | `INPUT[number:CR1/rsheet#AC]`                           |
| Resistances | `INPUT[text:CR1/rsheet#Resistances]`                    |
| Inspiration |  `INPUT[toggle:CR1/rsheet#Inpiration]`                                                       |
|             |                                                         |







## Skills
| Skill           |                          Expertise                           |                 Proficiency                  |                                                               Total                                                               |
| :-------------- | :----------------------------------------------------------: | :------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------: |
| Acrobatics      |   `INPUT[toggle(class(star)):CR1/rsheet#expertise.acrobatics]`   |   `INPUT[toggle:CR1/rsheet#skills.acrobatics]`   |     `VIEW[{CR1/rsheet#abilityMods.dex}+{CR1/rsheet#skills.acrobatics}*{CR1/rsheet#pBonus}+{CR1/rsheet#expertise.acrobatics}*{CR1/rsheet#pBonus}]`     |
| Animal Handling | `INPUT[toggle(class(star)):CR1/rsheet#expertise.animalHandling]` | `INPUT[toggle:CR1/rsheet#skills.animalHandling]` | `VIEW[{CR1/rsheet#abilityMods.wis}+{CR1/rsheet#skills.animalHandling}*{CR1/rsheet#pBonus}+{CR1/rsheet#expertise.animalHandling}*{CR1/rsheet#pBonus}]` |
| Arcana          |     `INPUT[toggle(class(star)):CR1/rsheet#expertise.arcana]`     |     `INPUT[toggle:CR1/rsheet#skills.arcana]`     |         `VIEW[{CR1/rsheet#abilityMods.int}+{CR1/rsheet#skills.arcana}*{CR1/rsheet#pBonus}+{CR1/rsheet#expertise.arcana}*{CR1/rsheet#pBonus}]`         |
| Athletics       |   `INPUT[toggle(class(star)):CR1/rsheet#expertise.athletics]`    |   `INPUT[toggle:CR1/rsheet#skills.athletics]`    |      `VIEW[{CR1/rsheet#abilityMods.str}+{CR1/rsheet#skills.athletics}*{CR1/rsheet#pBonus}+{CR1/rsheet#expertise.athletics}*{CR1/rsheet#pBonus}]`      |
| Deception       |   `INPUT[toggle(class(star)):CR1/rsheet#expertise.deception]`    |   `INPUT[toggle:CR1/rsheet#skills.deception]`    |      `VIEW[{CR1/rsheet#abilityMods.cha}+{CR1/rsheet#skills.deception}*{CR1/rsheet#pBonus}+{CR1/rsheet#expertise.deception}*{CR1/rsheet#pBonus}]`      |
| History         |    `INPUT[toggle(class(star)):CR1/rsheet#expertise.history]`     |    `INPUT[toggle:CR1/rsheet#skills.history]`     |        `VIEW[{CR1/rsheet#abilityMods.int}+{CR1/rsheet#skills.history}*{CR1/rsheet#pBonus}+{CR1/rsheet#expertise.history}*{CR1/rsheet#pBonus}]`        |
| Insight         |    `INPUT[toggle(class(star)):CR1/rsheet#expertise.insight]`     |    `INPUT[toggle:CR1/rsheet#skills.insight]`     |        `VIEW[{CR1/rsheet#abilityMods.wis}+{CR1/rsheet#skills.insight}*{CR1/rsheet#pBonus}+{CR1/rsheet#expertise.insight}*{CR1/rsheet#pBonus}]`        |
| Intimidation    |  `INPUT[toggle(class(star)):CR1/rsheet#expertise.intimidation]`  |  `INPUT[toggle:CR1/rsheet#skills.intimidation]`  |   `VIEW[{CR1/rsheet#abilityMods.cha}+{CR1/rsheet#skills.intimidation}*{CR1/rsheet#pBonus}+{CR1/rsheet#expertise.intimidation}*{CR1/rsheet#pBonus}]`   |
| Investigation   | `INPUT[toggle(class(star)):CR1/rsheet#expertise.investigation]`  | `INPUT[toggle:CR1/rsheet#skills.investigation]`  |  `VIEW[{CR1/rsheet#abilityMods.int}+{CR1/rsheet#skills.investigation}*{CR1/rsheet#pBonus}+{CR1/rsheet#expertise.investigation}*{CR1/rsheet#pBonus}]`  |
| Medicine        |    `INPUT[toggle(class(star)):CR1/rsheet#expertise.medicine]`    |    `INPUT[toggle:CR1/rsheet#skills.medicine]`    |       `VIEW[{CR1/rsheet#abilityMods.wis}+{CR1/rsheet#skills.medicine}*{CR1/rsheet#pBonus}+{CR1/rsheet#expertise.medicine}*{CR1/rsheet#pBonus}]`       |
| Nature          |     `INPUT[toggle(class(star)):CR1/rsheet#expertise.nature]`     |     `INPUT[toggle:CR1/rsheet#skills.nature]`     |         `VIEW[{CR1/rsheet#abilityMods.int}+{CR1/rsheet#skills.nature}*{CR1/rsheet#pBonus}+{CR1/rsheet#expertise.nature}*{CR1/rsheet#pBonus}]`         |
| Perception      |   `INPUT[toggle(class(star)):CR1/rsheet#expertise.perception]`   |   `INPUT[toggle:CR1/rsheet#skills.perception]`   |     `VIEW[{CR1/rsheet#abilityMods.wis}+{CR1/rsheet#skills.perception}*{CR1/rsheet#pBonus}+{CR1/rsheet#expertise.perception}*{CR1/rsheet#pBonus}]`     |
| Performance     |  `INPUT[toggle(class(star)):CR1/rsheet#expertise.performance]`   |  `INPUT[toggle:CR1/rsheet#skills.performance]`   |    `VIEW[{CR1/rsheet#abilityMods.cha}+{CR1/rsheet#skills.performance}*{CR1/rsheet#pBonus}+{CR1/rsheet#expertise.performance}*{CR1/rsheet#pBonus}]`    |
| Persuasion      |   `INPUT[toggle(class(star)):CR1/rsheet#expertise.persuasion]`   |   `INPUT[toggle:CR1/rsheet#skills.persuasion]`   |     `VIEW[{CR1/rsheet#abilityMods.cha}+{CR1/rsheet#skills.persuasion}*{CR1/rsheet#pBonus}+{CR1/rsheet#expertise.persuasion}*{CR1/rsheet#pBonus}]`     |
| Religion        |    `INPUT[toggle(class(star)):CR1/rsheet#expertise.religion]`    |    `INPUT[toggle:CR1/rsheet#skills.religion]`    |       `VIEW[{CR1/rsheet#abilityMods.int}+{CR1/rsheet#skills.religion}*{CR1/rsheet#pBonus}+{CR1/rsheet#expertise.religion}*{CR1/rsheet#pBonus}]`       |
| Sleight of Hand | `INPUT[toggle(class(star)):CR1/rsheet#expertise.sleightOfHand]`  | `INPUT[toggle:CR1/rsheet#skills.sleightOfHand]`  |  `VIEW[{CR1/rsheet#abilityMods.dex}+{CR1/rsheet#skills.sleightOfHand}*{CR1/rsheet#pBonus}+{CR1/rsheet#expertise.sleightOfHand}*{CR1/rsheet#pBonus}]`  |
| Stealth         |    `INPUT[toggle(class(star)):CR1/rsheet#expertise.stealth]`     |    `INPUT[toggle:CR1/rsheet#skills.stealth]`     |        `VIEW[{CR1/rsheet#abilityMods.dex}+{CR1/rsheet#skills.stealth}*{CR1/rsheet#pBonus}+{CR1/rsheet#expertise.stealth}*{CR1/rsheet#pBonus}]`        |
| Survival        |    `INPUT[toggle(class(star)):CR1/rsheet#expertise.survival]`    |    `INPUT[toggle:CR1/rsheet#skills.survival]`    |       `VIEW[{CR1/rsheet#abilityMods.wis}+{CR1/rsheet#skills.survival}*{CR1/rsheet#pBonus}+{CR1/rsheet#expertise.survival}*{CR1/rsheet#pBonus}]`       |


# Other proficiencies 
 |
 ---|---|
[[Languages]] |`INPUT[text:CR1/rsheet#Languages]`|
[[Weapons]]| `INPUT[text:CR1/rsheet#Weapons]` |
[[Armor]] | `INPUT[text:CR1/rsheet#Armor]`|
[[Tools]] | `INPUT[text:CR1/rsheet#Tools]` |


# Character Traits
 |
 ---|---|
[[Personality Traits]] |`INPUT[text:CR1/rsheet#personalityTraits]`|
[[Ideals]]| `INPUT[text:CR1/rsheet#Ideals]` |
[[Bonds]] | `INPUT[text:CR1/rsheet#Bonds]`|
[[Flaws]] | `INPUT[text:CR1/rsheet#Flaws]` |

## Inventory
Inventory Size: `INPUT[number:CR1/rsheet#invenSize]`
~~~meta-bind-js-view
{CR1/rsheet#invenSize} as number
save to {CR1/equiptagdump#list}
hidden
---

let values = [];
const outputs = context.metadata.frontmatter.outputs = [];

// Add table header
values.push('| # | Item | Count |');
values.push('| --- | --- | --- |');

// Loop to create rows equal to the value of 'number'
for (let i = 1; i <= context.bound.number; i++) { values.push(`| ${i} | \`INPUT[text:CR1/Inventory#item.name${i}]\` | \`INPUT[number:CR1/Inventory#item.count${i}]\` |`); }

return values.join("\n");

~~~

`VIEW[{CR1/equiptagdump#list}][text(renderMarkdown)]`


`VIEW[floor(({CR1/rsheet#abilityScores.str}-10)/2)][math(hidden):CR1/rsheet#abilityMods.str]`
`VIEW[floor(({CR1/rsheet#abilityScores.dex}-10)/2)][math(hidden):CR1/rsheet#abilityMods.dex]`
`VIEW[floor(({CR1/rsheet#abilityScores.con}-10)/2)][math(hidden):CR1/rsheet#abilityMods.con]`
`VIEW[floor(({CR1/rsheet#abilityScores.int}-10)/2)][math(hidden):CR1/rsheet#abilityMods.int]`
`VIEW[floor(({CR1/rsheet#abilityScores.wis}-10)/2)][math(hidden):CR1/rsheet#abilityMods.wis]`
`VIEW[floor(({CR1/rsheet#abilityScores.cha}-10)/2)][math(hidden):CR1/rsheet#abilityMods.cha]`

`VIEW[ceil({CR1/rsheet#Level}/4)+1][math(hidden):CR1/rsheet#pBonus]`

`VIEW[{CR1/rsheet#abilityMods.wis}+10][math(hidden):CR1/rsheet#passive.perception]`
`VIEW[{CR1/rsheet#abilityMods.int}+10][math(hidden):CR1/rsheet#passive.investigation]`
`VIEW[{CR1/rsheet#abilityMods.dex}+10][math(hidden):CR1/rsheet#passive.stealth]`











