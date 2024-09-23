

---

> [!info] Character name
> Contents

## Level
Level: `INPUT[number(class(boxnumberber)):rsheet#abilityScores.Level]`
ProficiencyBonus: `VIEW[**{rsheet#pBonus}**][text(renderMarkdown)]`
## Ability Scores
| <nobr>Stat</nobr> | <nobr>Score</nobr> | <nobr>#</nobr> | <nobr>Stat</nobr> | <nobr>Score</nobr> | <nobr>#</nobr> |
| :---: | :---: | :---: | :---: | :---: | :---: |
| STR | `INPUT[number(class(boxnumberber)):rsheet#abilityScores.str]` | `VIEW[{rsheet#abilityMods.str}]` | INT | `INPUT[number(class(boxnumberber)):rsheet#abilityScores.int]` | `VIEW[{rsheet#abilityMods.int}]` |
| DEX | `INPUT[number(class(boxnumberber)):rsheet#abilityScores.dex]` | `VIEW[{rsheet#abilityMods.dex}]` | WIS | `INPUT[number(class(boxnumberber)):rsheet#abilityScores.wis]` | `VIEW[{rsheet#abilityMods.wis}]` |
| CON | `INPUT[number(class(boxnumberber)):rsheet#abilityScores.con]` | `VIEW[{rsheet#abilityMods.con}]` | CHA | `INPUT[number(class(boxnumberber)):rsheet#abilityScores.cha]` | `VIEW[{rsheet#abilityMods.cha}]` |
## Saving Throws
| <nobr>Stat</nobr> | <nobr>Prof</nobr> | <nobr>Total</nobr> | <nobr>Stat</nobr> | <nobr>Prof</nobr> | <nobr>Total</nobr> |
|:-----------------:|:-----------------:|:------------------:|:-----------------:|:-----------------:|:------------------:|
| STR  | `INPUT[toggle:rsheet#savingThrows.str]` | `VIEW[{rsheet#abilityMods.str}+{rsheet#pBonus}*{rsheet#savingThrows.str}]` | DEX  | `INPUT[toggle:rsheet#savingThrows.dex]` | `VIEW[{rsheet#abilityMods.dex}+{rsheet#pBonus}*{rsheet#savingThrows.dex}]` |
| CON  | `INPUT[toggle:rsheet#savingThrows.con]` | `VIEW[{rsheet#abilityMods.con}+{rsheet#pBonus}*{rsheet#savingThrows.con}]` | INT  | `INPUT[toggle:rsheet#savingThrows.int]` | `VIEW[{rsheet#abilityMods.int}+{rsheet#pBonus}*{rsheet#savingThrows.int}]` |
| WIS  | `INPUT[toggle:rsheet#savingThrows.wis]` | `VIEW[{rsheet#abilityMods.wis}+{rsheet#pBonus}*{rsheet#savingThrows.wis}]` | CHA  | `INPUT[toggle:rsheet#savingThrows.cha]` | `VIEW[{rsheet#abilityMods.cha}+{rsheet#pBonus}*{rsheet#savingThrows.cha}]` |
## Passive Skills
| Perception | Investigation | Stealth |
|:----------:|:-------------:|:-------:|
|`VIEW[{rsheet#passive.perception}]`|`VIEW[{rsheet#passive.investigation}]`           |`VIEW[{rsheet#passive.stealth}]`|
## General
| Hit Points  | `INPUT[number(class(boxnumberber)):rsheet#chp]` / `VIEW[{rsheet#mhp}]` (max)                             |
| ----------- | ----------------------------------------------------------------------------------- |
| Temp HP     | `INPUT[number(class(boxnumberber)):rsheet#temphp]`                                                       |
| Hit dice    | `INPUT[number(class(boxnumberber)):rsheet#hDUse]` /`VIEW[{rsheet#Level}]`d`VIEW[{rsheet#hitDice}]` (max) |
| Initiative  | +`VIEW[{rsheet#abilityMods.dex}]`                                                   |
| AC          | `INPUT[number(class(boxnumberber)):rsheet#AC]`                                                                                                                           
| Inspiration | `INPUT[toggle:rsheet#Inpiration]`                                                   |

| Death Saves        |                                   |                                   |                                   |
| ------- | --------------------------------- | --------------------------------- | --------------------------------- |
| Success | `INPUT[toggle:rsheet#ds.s1]` | `INPUT[toggle:rsheet#ds.s2]` | `INPUT[toggle:rsheet#ds.s3]` |
| Faliure | `INPUT[toggle:rsheet#ds.f1]` | `INPUT[toggle:rsheet#ds.f2]` | `INPUT[toggle:rsheet#ds.f3]` |                              |
## Skills
| Skill           |                          Expertise                           |                 Proficiency                  |                                                               Total                                                               |
| :-------------- | :----------------------------------------------------------: | :------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------: |
| Acrobatics      |   `INPUT[toggle(class(star)):rsheet#expertise.acrobatics]`   |   `INPUT[toggle:rsheet#skills.acrobatics]`   |     `VIEW[{rsheet#abilityMods.dex}+{rsheet#skills.acrobatics}*{rsheet#pBonus}+{rsheet#expertise.acrobatics}*{rsheet#pBonus}]`     |
| Animal Handling | `INPUT[toggle(class(star)):rsheet#expertise.animalHandling]` | `INPUT[toggle:rsheet#skills.animalHandling]` | `VIEW[{rsheet#abilityMods.wis}+{rsheet#skills.animalHandling}*{rsheet#pBonus}+{rsheet#expertise.animalHandling}*{rsheet#pBonus}]` |
| Arcana          |     `INPUT[toggle(class(star)):rsheet#expertise.arcana]`     |     `INPUT[toggle:rsheet#skills.arcana]`     |         `VIEW[{rsheet#abilityMods.int}+{rsheet#skills.arcana}*{rsheet#pBonus}+{rsheet#expertise.arcana}*{rsheet#pBonus}]`         |
| Athletics       |   `INPUT[toggle(class(star)):rsheet#expertise.athletics]`    |   `INPUT[toggle:rsheet#skills.athletics]`    |      `VIEW[{rsheet#abilityMods.str}+{rsheet#skills.athletics}*{rsheet#pBonus}+{rsheet#expertise.athletics}*{rsheet#pBonus}]`      |
| Deception       |   `INPUT[toggle(class(star)):rsheet#expertise.deception]`    |   `INPUT[toggle:rsheet#skills.deception]`    |      `VIEW[{rsheet#abilityMods.cha}+{rsheet#skills.deception}*{rsheet#pBonus}+{rsheet#expertise.deception}*{rsheet#pBonus}]`      |
| History         |    `INPUT[toggle(class(star)):rsheet#expertise.history]`     |    `INPUT[toggle:rsheet#skills.history]`     |        `VIEW[{rsheet#abilityMods.int}+{rsheet#skills.history}*{rsheet#pBonus}+{rsheet#expertise.history}*{rsheet#pBonus}]`        |
| Insight         |    `INPUT[toggle(class(star)):rsheet#expertise.insight]`     |    `INPUT[toggle:rsheet#skills.insight]`     |        `VIEW[{rsheet#abilityMods.wis}+{rsheet#skills.insight}*{rsheet#pBonus}+{rsheet#expertise.insight}*{rsheet#pBonus}]`        |
| Intimidation    |  `INPUT[toggle(class(star)):rsheet#expertise.intimidation]`  |  `INPUT[toggle:rsheet#skills.intimidation]`  |   `VIEW[{rsheet#abilityMods.cha}+{rsheet#skills.intimidation}*{rsheet#pBonus}+{rsheet#expertise.intimidation}*{rsheet#pBonus}]`   |
| Investigation   | `INPUT[toggle(class(star)):rsheet#expertise.investigation]`  | `INPUT[toggle:rsheet#skills.investigation]`  |  `VIEW[{rsheet#abilityMods.int}+{rsheet#skills.investigation}*{rsheet#pBonus}+{rsheet#expertise.investigation}*{rsheet#pBonus}]`  |
| Medicine        |    `INPUT[toggle(class(star)):rsheet#expertise.medicine]`    |    `INPUT[toggle:rsheet#skills.medicine]`    |       `VIEW[{rsheet#abilityMods.wis}+{rsheet#skills.medicine}*{rsheet#pBonus}+{rsheet#expertise.medicine}*{rsheet#pBonus}]`       |
| Nature          |     `INPUT[toggle(class(star)):rsheet#expertise.nature]`     |     `INPUT[toggle:rsheet#skills.nature]`     |         `VIEW[{rsheet#abilityMods.int}+{rsheet#skills.nature}*{rsheet#pBonus}+{rsheet#expertise.nature}*{rsheet#pBonus}]`         |
| Perception      |   `INPUT[toggle(class(star)):rsheet#expertise.perception]`   |   `INPUT[toggle:rsheet#skills.perception]`   |     `VIEW[{rsheet#abilityMods.wis}+{rsheet#skills.perception}*{rsheet#pBonus}+{rsheet#expertise.perception}*{rsheet#pBonus}]`     |
| Performance     |  `INPUT[toggle(class(star)):rsheet#expertise.performance]`   |  `INPUT[toggle:rsheet#skills.performance]`   |    `VIEW[{rsheet#abilityMods.cha}+{rsheet#skills.performance}*{rsheet#pBonus}+{rsheet#expertise.performance}*{rsheet#pBonus}]`    |
| Persuasion      |   `INPUT[toggle(class(star)):rsheet#expertise.persuasion]`   |   `INPUT[toggle:rsheet#skills.persuasion]`   |     `VIEW[{rsheet#abilityMods.cha}+{rsheet#skills.persuasion}*{rsheet#pBonus}+{rsheet#expertise.persuasion}*{rsheet#pBonus}]`     |
| Religion        |    `INPUT[toggle(class(star)):rsheet#expertise.religion]`    |    `INPUT[toggle:rsheet#skills.religion]`    |       `VIEW[{rsheet#abilityMods.int}+{rsheet#skills.religion}*{rsheet#pBonus}+{rsheet#expertise.religion}*{rsheet#pBonus}]`       |
| Sleight of Hand | `INPUT[toggle(class(star)):rsheet#expertise.sleightOfHand]`  | `INPUT[toggle:rsheet#skills.sleightOfHand]`  |  `VIEW[{rsheet#abilityMods.dex}+{rsheet#skills.sleightOfHand}*{rsheet#pBonus}+{rsheet#expertise.sleightOfHand}*{rsheet#pBonus}]`  |
| Stealth         |    `INPUT[toggle(class(star)):rsheet#expertise.stealth]`     |    `INPUT[toggle:rsheet#skills.stealth]`     |        `VIEW[{rsheet#abilityMods.dex}+{rsheet#skills.stealth}*{rsheet#pBonus}+{rsheet#expertise.stealth}*{rsheet#pBonus}]`        |
| Survival        |    `INPUT[toggle(class(star)):rsheet#expertise.survival]`    |    `INPUT[toggle:rsheet#skills.survival]`    |       `VIEW[{rsheet#abilityMods.wis}+{rsheet#skills.survival}*{rsheet#pBonus}+{rsheet#expertise.survival}*{rsheet#pBonus}]`       |
___
## Proficiencies<span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span> Character

|                          |                                |                             |                                                      |
| ------------------------------------ | ------------------------------ | ------------------------------ | ---------------------------------------------------- |
| [[Proficiencies#Language\|Language]]  | `INPUT[text:rsheet#Languages]` | [[Ch_traits#Personality Traits\|Personality Traits]] | `INPUT[text:rsheet#personalityTraits]` |
| [[Proficiencies#Weapons\|Weapons]]    | `INPUT[text:rsheet#Weapons]`   | [[Ch_traits#Bonds\|Bonds]]           | `INPUT[text:rsheet#Bonds]`    |
| [[Proficiencies#Armor\|Armor]]        | `INPUT[text:rsheet#Armor]`     | [[Ch_traits#Ideals\|Ideals]]           | `INPUT[text:rsheet#Ideals]`    |
| [[Proficiencies#Tools\|Tools]]        | `INPUT[text:rsheet#Tools]`     | [[Ch_traits#Flaws\|Flaws]]           | `INPUT[text:rsheet#Flaws]`    |

## Combat
|             Name              |                       Hit                       |                                     Dmg                                      |           Type            |          Properties           |           Range            |
| :---------------------------: | :---------------------------------------------: | :--------------------------------------------------------------------------: | :-----------------------: | :---------------------------: | :------------------------: |
| `INPUT[text:rsheet#WP1.name]` | +`VIEW[{rsheet#WP1.Hit}][text(renderMarkdown)]` | `VIEW[{rsheet#WP1.Damage}]`+`VIEW[{rsheet#WP1.Bonus}][text(renderMarkdown)]` | `VIEW[{rsheet#WP1.Type}]` | `VIEW[{rsheet#WP1.Property}]` | `VIEW[{rsheet#WP1.Range}]` |
| `INPUT[text:rsheet#WP2.name]` | +`VIEW[{rsheet#WP2.Hit}][text(renderMarkdown)]` | `VIEW[{rsheet#WP2.Damage}]`+`VIEW[{rsheet#WP2.Bonus}][text(renderMarkdown)]` | `VIEW[{rsheet#WP2.Type}]` | `VIEW[{rsheet#WP2.Property}]` | `VIEW[{rsheet#WP2.Range}]` |
| `INPUT[text:rsheet#WP3.name]` | +`VIEW[{rsheet#WP3.Hit}][text(renderMarkdown)]` | `VIEW[{rsheet#WP3.Damage}]`+`VIEW[{rsheet#WP3.Bonus}][text(renderMarkdown)]` | `VIEW[{rsheet#WP3.Type}]` | `VIEW[{rsheet#WP3.Property}]` | `VIEW[{rsheet#WP3.Range}]` |
| `INPUT[text:rsheet#WP4.name]` | +`VIEW[{rsheet#WP4.Hit}][text(renderMarkdown)]` | `VIEW[{rsheet#WP4.Damage}]`+`VIEW[{rsheet#WP4.Bonus}][text(renderMarkdown)]` | `VIEW[{rsheet#WP4.Type}]` | `VIEW[{rsheet#WP4.Property}]` | `VIEW[{rsheet#WP4.Range}]` |
| `INPUT[text:rsheet#WP5.name]` | +`VIEW[{rsheet#WP5.Hit}][text(renderMarkdown)]` | `VIEW[{rsheet#WP5.Damage}]`+`VIEW[{rsheet#WP5.Bonus}][text(renderMarkdown)]` | `VIEW[{rsheet#WP5.Type}]` | `VIEW[{rsheet#WP5.Property}]` | `VIEW[{rsheet#WP5.Range}]` |
___
## Inventory
|<nobr>Item<nobr>|<nobr>Count<nobr>|<nobr>Item<nobr>|<nobr>Count<nobr>                         |
|:--------:|:----:|:----:|:-----------:|
| `INPUT[text(class(boxtext)):Inventory#item.name1]`  | `INPUT[number(class(boxnumber)):Inventory#item.count1]`  | `INPUT[text(class(boxtext)):Inventory#item.name11]` | `INPUT[number(class(boxnumber)):Inventory#item.count11]` |
|`INPUT[text(class(boxtext)):Inventory#item.name2]`  | `INPUT[number(class(boxnumber)):Inventory#item.count2]`  | `INPUT[text(class(boxtext)):Inventory#item.name12]` | `INPUT[number(class(boxnumber)):Inventory#item.count12]` |
|`INPUT[text(class(boxtext)):Inventory#item.name3]`  | `INPUT[number(class(boxnumber)):Inventory#item.count3]`  | `INPUT[text(class(boxtext)):Inventory#item.name13]` | `INPUT[number(class(boxnumber)):Inventory#item.count13]` |
| `INPUT[text(class(boxtext)):Inventory#item.name4]`  | `INPUT[number(class(boxnumber)):Inventory#item.count4]`  |`INPUT[text(class(boxtext)):Inventory#item.name14]` | `INPUT[number(class(boxnumber)):Inventory#item.count14]` |
|`INPUT[text(class(boxtext)):Inventory#item.name5]`  | `INPUT[number(class(boxnumber)):Inventory#item.count5]`  | `INPUT[text(class(boxtext)):Inventory#item.name15]` | `INPUT[number(class(boxnumber)):Inventory#item.count15]` |
|`INPUT[text(class(boxtext)):Inventory#item.name6]`  | `INPUT[number(class(boxnumber)):Inventory#item.count6]`  |`INPUT[text(class(boxtext)):Inventory#item.name16]` | `INPUT[number(class(boxnumber)):Inventory#item.count16]` |
|`INPUT[text(class(boxtext)):Inventory#item.name7]`  | `INPUT[number(class(boxnumber)):Inventory#item.count7]`  |`INPUT[text(class(boxtext)):Inventory#item.name17]` | `INPUT[number(class(boxnumber)):Inventory#item.count17]` |
|`INPUT[text(class(boxtext)):Inventory#item.name8]`  | `INPUT[number(class(boxnumber)):Inventory#item.count8]`  | `INPUT[text(class(boxtext)):Inventory#item.name18]` | `INPUT[number(class(boxnumber)):Inventory#item.count18]` |
|`INPUT[text(class(boxtext)):Inventory#item.name9]`  | `INPUT[number(class(boxnumber)):Inventory#item.count9]`  |`INPUT[text(class(boxtext)):Inventory#item.name19]` | `INPUT[number(class(boxnumber)):Inventory#item.count19]` |
|`INPUT[text(class(boxtext)):Inventory#item.name10]` | `INPUT[number(class(boxnumber)):Inventory#item.count10]` |`INPUT[text(class(boxtext)):Inventory#item.name20]` | `INPUT[number(class(boxnumber)):Inventory#item.count20]`|
___
##### Rest:
```meta-bind-button
style: primary
label: Long Rest
id: longRest
action:
  type: inlineJS
  code: |
    const mb = engine.getPlugin('obsidian-meta-bind-plugin').api;
    const levels = Array.from({length: 9}, (_, i) => mb.parseBindTarget(`rsheet#spellcast.lvl${i+1}`, context.file.path));

    // Set all spellcast levels to 0
    levels.forEach(level => mb.updateMetadata(level, () => 0));

    // Set rsheet#mhp to 0
    const mhp = mb.parseBindTarget('rsheet#mhp', context.file.path);
    mb.updateMetadata(mhp, () => 0);
```
___
~~~meta-bind-js-view
{rsheet#l0c1} as l0c1
{rsheet#l0c2} as l0c2
{rsheet#l0c3} as l0c3
{rsheet#l0c4} as l0c4
{rsheet#l0c5} as l0c5
{rsheet#l1c1} as l1c1
{rsheet#l1c2} as l1c2
{rsheet#l1c3} as l1c3
{rsheet#l1c4} as l1c4
{rsheet#l1c5} as l1c5
{rsheet#l1c6} as l1c6
{rsheet#l1c7} as l1c7
{rsheet#l1c8} as l1c8
{rsheet#l1c9} as l1c9
{rsheet#l1c10} as l1c10
{rsheet#l2c1} as l2c1
{rsheet#l2c2} as l2c2
{rsheet#l2c3} as l2c3
{rsheet#l2c4} as l2c4
{rsheet#l2c5} as l2c5
{rsheet#l2c6} as l2c6
{rsheet#l2c7} as l2c7
{rsheet#l2c8} as l2c8
{rsheet#l2c9} as l2c9
{rsheet#l2c10} as l2c10
{rsheet#l3c1} as l3c1
{rsheet#l3c2} as l3c2
{rsheet#l3c3} as l3c3
{rsheet#l3c4} as l3c4
{rsheet#l3c5} as l3c5
{rsheet#l3c6} as l3c6
{rsheet#l3c7} as l3c7
{rsheet#l3c8} as l3c8
{rsheet#l3c9} as l3c9
{rsheet#l3c10} as l3c10
{rsheet#l4c1} as l4c1
{rsheet#l4c2} as l4c2
{rsheet#l4c3} as l4c3
{rsheet#l4c4} as l4c4
{rsheet#l4c5} as l4c5
{rsheet#l4c6} as l4c6
{rsheet#l4c7} as l4c7
{rsheet#l5c1} as l5c1
{rsheet#l5c2} as l5c2
{rsheet#l5c3} as l5c3
{rsheet#l5c4} as l5c4
{rsheet#l5c5} as l5c5
{rsheet#l5c6} as l5c6
{rsheet#l5c7} as l5c7
{rsheet#l6c1} as l6c1
{rsheet#l6c2} as l6c2
{rsheet#l6c3} as l6c3
{rsheet#l6c4} as l6c4
{rsheet#l6c5} as l6c5
{rsheet#l6c6} as l6c6
{rsheet#l7c1} as l7c1
{rsheet#l7c2} as l7c2
{rsheet#l7c3} as l7c3
{rsheet#l7c4} as l7c4
{rsheet#l7c5} as l7c5
{rsheet#l8c1} as l8c1
{rsheet#l8c2} as l8c2
{rsheet#l8c3} as l8c3
{rsheet#l8c4} as l8c4
{rsheet#l9c1} as l9c1
{rsheet#l9c2} as l9c2
{rsheet#l9c3} as l9c3
{rsheet#l9c4} as l9c4
---
l0c1 = context.bound.l0c1
l0c2 = context.bound.l0c2
l0c3 = context.bound.l0c3
l0c4 = context.bound.l0c4
l0c5 = context.bound.l0c5
l1c1 = context.bound.l1c1
l1c2 = context.bound.l1c2
l1c3 = context.bound.l1c3
l1c4 = context.bound.l1c4
l1c5 = context.bound.l1c5
l1c6 = context.bound.l1c6
l1c7 = context.bound.l1c7
l1c8 = context.bound.l1c8
l1c9 = context.bound.l1c9
l1c10 = context.bound.l1c10
l2c1 = context.bound.l2c1
l2c2 = context.bound.l2c2
l2c3 = context.bound.l2c3
l2c4 = context.bound.l2c4
l2c5 = context.bound.l2c5
l2c6 = context.bound.l2c6
l2c7 = context.bound.l2c7
l2c8 = context.bound.l2c8
l2c9 = context.bound.l2c9
l2c10 = context.bound.l2c10
l3c1 = context.bound.l3c1
l3c2 = context.bound.l3c2
l3c3 = context.bound.l3c3
l3c4 = context.bound.l3c4
l3c5 = context.bound.l3c5
l3c6 = context.bound.l3c6
l3c7 = context.bound.l3c7
l3c8 = context.bound.l3c8
l3c9 = context.bound.l3c9
l3c10 = context.bound.l3c10
l4c1 = context.bound.l4c1
l4c2 = context.bound.l4c2
l4c3 = context.bound.l4c3
l4c4 = context.bound.l4c4
l4c5 = context.bound.l4c5
l4c6 = context.bound.l4c6
l4c7 = context.bound.l4c7
l5c1 = context.bound.l5c1
l5c2 = context.bound.l5c2
l5c3 = context.bound.l5c3
l5c4 = context.bound.l5c4
l5c5 = context.bound.l5c5
l5c6 = context.bound.l5c6
l5c7 = context.bound.l5c7
l6c1 = context.bound.l6c1
l6c2 = context.bound.l6c2
l6c3 = context.bound.l6c3
l6c4 = context.bound.l6c4
l6c5 = context.bound.l6c5
l6c6 = context.bound.l6c6
l7c1 = context.bound.l7c1
l7c2 = context.bound.l7c2
l7c3 = context.bound.l7c3
l7c4 = context.bound.l7c4
l7c5 = context.bound.l7c5
l8c1 = context.bound.l8c1
l8c2 = context.bound.l8c2
l8c3 = context.bound.l8c3
l8c4 = context.bound.l8c4
l9c1 = context.bound.l9c1
l9c2 = context.bound.l9c2
l9c3 = context.bound.l9c3
l9c4 = context.bound.l9c4
const generateTable = () => {
    let table = "> [!hint | clean no-i]+ ## Spells\n";
    table += ">> [!column| 3 clean no-t]\n";

    // Cantrips section
    table += ">>\n";
    table += ">>| Cantrips |\n";
    table += ">>|--------|\n";
    for (let i = 1; i <= 5; i++) {
        const value = context.bound[`l0c${i}`].trim(); // Ensure no extra spaces
        if (value) {
            const cantrip = `[[SpellRender#${value}\\|${value}]]`;
            table += `>>| ${cantrip} |\n`;
        }
    }
    table += ">>\n";

    // Level 1 spells section
    table += ">>\n";
    table += ">>| 1<sup>st</sup> Level Spells [`VIEW[{rsheet#spellcast.lvl1}]`/`VIEW[{rsheet#spellslot.lvl1}]`]:`BUTTON[lvl1-cast]` |\n";
    table += ">>|------------------------|\n";
    for (let i = 1; i <= 10; i++) {
        const value = context.bound[`l1c${i}`].trim();
        if (value) {
            const level1 = `[[SpellRender#${value}\\|${value}]]`;
            table += `>>| ${level1} |\n`;
        }
    }
    table += ">>\n";

    // Level 2 spells section
    table += ">>\n";
    table += ">>| 2<sup>nd</sup> Level Spells [`VIEW[{rsheet#spellcast.lvl2}]`/`VIEW[{rsheet#spellslot.lvl2}]`]:`BUTTON[lvl2-cast]` |\n";
    table += ">>|------------------------|\n";
    for (let i = 1; i <= 10; i++) {
        const value = context.bound[`l2c${i}`].trim();
        if (value) {
            const level2 = `[[SpellRender#${value}\\|${value}]]`;
            table += `>>| ${level2} |\n`;
        }
    }
    table += ">>\n";

    // Level 3 spells section
    table += ">>\n";
    table += ">>| 3<sup>rd</sup> Level Spells[`VIEW[{rsheet#spellcast.lvl3}]`/`VIEW[{rsheet#spellslot.lvl3}]`]:`BUTTON[lvl3-cast]` |\n";
    table += ">>|------------------------|\n";
    for (let i = 1; i <= 10; i++) {
        const value = context.bound[`l3c${i}`].trim();
        if (value) {
            const level3 = `[[SpellRender#${value}\\|${value}]]`;
            table += `>>| ${level3} |\n`;
        }
    }
    table += ">>\n";

    // Level 4 spells section
    table += ">>\n";
    table += ">>| 4<sup>th</sup> Level Spells[`VIEW[{rsheet#spellcast.lvl4}]`/`VIEW[{rsheet#spellslot.lvl4}]`]:`BUTTON[lvl4-cast]` |\n";
    table += ">>|------------------------|\n";
    for (let i = 1; i <= 7; i++) {
        const value = context.bound[`l4c${i}`].trim();
        if (value) {
            const level4 = `[[SpellRender#${value}\\|${value}]]`;
            table += `>>| ${level4} |\n`;
        }
    }
    table += ">>\n";

    // Level 5 spells section
    table += ">>\n";
    table += ">>| 5<sup>th</sup> Level Spells[`VIEW[{rsheet#spellcast.lvl5}]`/`VIEW[{rsheet#spellslot.lvl5}]`]:`BUTTON[lvl5-cast]` |\n";
    table += ">>|------------------------|\n";
    for (let i = 1; i <= 7; i++) {
        const value = context.bound[`l5c${i}`].trim();
        if (value) {
            const level5 = `[[SpellRender#${value}\\|${value}]]`;
            table += `>>| ${level5} |\n`;
        }
    }
    table += ">>\n";

    // Level 6 spells section
    table += ">>\n";
    table += ">>| 6<sup>th</sup> Level Spells[`VIEW[{rsheet#spellcast.lvl6}]`/`VIEW[{rsheet#spellslot.lvl6}]`]:`BUTTON[lvl6-cast]` |\n";
    table += ">>|------------------------|\n";
    for (let i = 1; i <= 6; i++) {
        const value = context.bound[`l6c${i}`].trim();
        if (value) {
            const level6 = `[[SpellRender#${value}\\|${value}]]`;
            table += `>>| ${level6} |\n`;
        }
    }
    table += ">>\n";

    // Level 7 spells section
    table += ">>\n";
    table += ">>| 7<sup>th</sup> Level Spells[`VIEW[{rsheet#spellcast.lvl7}]`/`VIEW[{rsheet#spellslot.lvl7}]`]:`BUTTON[lvl7-cast]` |\n";
    table += ">>|------------------------|\n";
    for (let i = 1; i <= 5; i++) {
        const value = context.bound[`l7c${i}`].trim();
        if (value) {
            const level7 = `[[SpellRender#${value}\\|${value}]]`;
            table += `>>| ${level7} |\n`;
        }
    }
    table += ">>\n";

    // Level 8 spells section
    table += ">>\n";
    table += ">>| 8<sup>th</sup> Level Spells[`VIEW[{rsheet#spellcast.lvl8}]`/`VIEW[{rsheet#spellslot.lvl8}]`]:`BUTTON[lvl8-cast]` |\n";
    table += ">>|------------------------|\n";
    for (let i = 1; i <= 4; i++) {
        const value = context.bound[`l8c${i}`].trim();
        if (value) {
            const level8 = `[[SpellRender#${value}\\|${value}]]`;
            table += `>>| ${level8} |\n`;
        }
    }
    table += ">>\n";

    // Level 9 spells section
    table += ">>\n";
    table += ">>| 9<sup>th</sup> Level Spells[`VIEW[{rsheet#spellcast.lvl9}]`/`VIEW[{rsheet#spellslot.lvl9}]`]:`BUTTON[lvl9-cast]` |\n";
    table += ">>|------------------------|\n";
    for (let i = 1; i <= 4; i++) {
        const value = context.bound[`l9c${i}`].trim();
        if (value) {
            const level9 = `[[SpellRender#${value}\\|${value}]]`;
            table += `>>| ${level9} |\n`;
        }
    }
    table += ">>\n";

    return table;
};

const str = generateTable();

// Render the markdown
return engine.markdown.create(str);

~~~
___

> [!hint | clean no-i]+ ## SpellBook
>> [!hint | clean no-i]+ Cantrips
>> |        <nobr><nobr>        |
>> |:--------------------------:|
>> | `INPUT[text:rsheet#l0c1]`  |
>> | `INPUT[text:rsheet#l0c2]`  |
>> | `INPUT[text:rsheet#l0c3]`  |
>> | `INPUT[text:rsheet#l0c4]`  |
>> | `INPUT[text:rsheet#l0c5]`  |
>>
>> > [!hint | clean no-i]+ Level 1
>> |        <nobr><nobr>        |
>> |:--------------------------:|
>> | `INPUT[text:rsheet#l1c1]`  |
>> | `INPUT[text:rsheet#l1c2]`  |
>> | `INPUT[text:rsheet#l1c3]`  |
>> | `INPUT[text:rsheet#l1c4]`  |
>> | `INPUT[text:rsheet#l1c5]`  |
>> | `INPUT[text:rsheet#l1c6]`  |
>> | `INPUT[text:rsheet#l1c7]`  |
>> | `INPUT[text:rsheet#l1c8]`  |
>> | `INPUT[text:rsheet#l1c9]`  |
>> | `INPUT[text:rsheet#l1c10]` |
>>
>> > [!hint | clean no-i]+ Level 2
>> |        <nobr><nobr>        |
>> |:--------------------------:|
>> | `INPUT[text:rsheet#l2c1]`  |
>> | `INPUT[text:rsheet#l2c2]`  |
>> | `INPUT[text:rsheet#l2c3]`  |
>> | `INPUT[text:rsheet#l2c4]`  |
>> | `INPUT[text:rsheet#l2c5]`  |
>> | `INPUT[text:rsheet#l2c6]`  |
>> | `INPUT[text:rsheet#l2c7]`  |
>> | `INPUT[text:rsheet#l2c8]`  |
>> | `INPUT[text:rsheet#l2c9]`  |
>> | `INPUT[text:rsheet#l2c10]` |
>>
>> > [!hint | clean no-i]+ Level 3
>> |        <nobr><nobr>        |
>> |:--------------------------:|
>> | `INPUT[text:rsheet#l3c1]`  |
>> | `INPUT[text:rsheet#l3c2]`  |
>> | `INPUT[text:rsheet#l3c3]`  |
>> | `INPUT[text:rsheet#l3c4]`  |
>> | `INPUT[text:rsheet#l3c5]`  |
>> | `INPUT[text:rsheet#l3c6]`  |
>> | `INPUT[text:rsheet#l3c7]`  |
>> | `INPUT[text:rsheet#l3c8]`  |
>> | `INPUT[text:rsheet#l3c9]`  |
>> | `INPUT[text:rsheet#l3c10]` |
>>
>> > [!hint | clean no-i]+ Level 4
>> |        <nobr><nobr>        |
>> |:--------------------------:|
>> | `INPUT[text:rsheet#l4c1]`  |
>> | `INPUT[text:rsheet#l4c2]`  |
>> | `INPUT[text:rsheet#l4c3]`  |
>> | `INPUT[text:rsheet#l4c4]`  |
>> | `INPUT[text:rsheet#l4c5]`  |
>> | `INPUT[text:rsheet#l4c6]`  |
>> | `INPUT[text:rsheet#l4c7]`  |
>>
>> > [!hint | clean no-i]+ Level 5
>> |        <nobr><nobr>        |
>> |:--------------------------:|
>> | `INPUT[text:rsheet#l5c1]`  |
>> | `INPUT[text:rsheet#l5c2]`  |
>> | `INPUT[text:rsheet#l5c3]`  |
>> | `INPUT[text:rsheet#l5c4]`  |
>> | `INPUT[text:rsheet#l5c5]`  |
>> | `INPUT[text:rsheet#l5c6]`  |
>>
>> > [!hint | clean no-i]+ Level 6
>> |        <nobr><nobr>        |
>> |:--------------------------:|
>> | `INPUT[text:rsheet#l6c1]`  |
>> | `INPUT[text:rsheet#l6c2]`  |
>> | `INPUT[text:rsheet#l6c3]`  |
>> | `INPUT[text:rsheet#l6c4]`  |
>> | `INPUT[text:rsheet#l6c5]`  |
>>
>> > [!hint | clean no-i]+ Level 7
>> |        <nobr><nobr>        |
>> |:--------------------------:|
>> | `INPUT[text:rsheet#l7c1]`  |
>> | `INPUT[text:rsheet#l7c2]`  |
>> | `INPUT[text:rsheet#l7c3]`  |
>> | `INPUT[text:rsheet#l7c4]`  |
>> | `INPUT[text:rsheet#l7c5]`  |
>>
>> > [!hint | clean no-i]+ Level 8
>> |        <nobr><nobr>        |
>> |:--------------------------:|
>> | `INPUT[text:rsheet#l8c1]`  |
>> | `INPUT[text:rsheet#l8c2]`  |
>> | `INPUT[text:rsheet#l8c3]`  |
>>
>> > [!hint | clean no-i]+ Level 9
>> |        <nobr><nobr>        |
>> |:--------------------------:|
>> | `INPUT[text:rsheet#l9c1]`  |
>> | `INPUT[text:rsheet#l9c2]`  |
>> | `INPUT[text:rsheet#l9c3]`  |
>> | `INPUT[text:rsheet#l9c4]`  |


> [!Admin| clean no-i]+
>Set Max HP`INPUT[number:rsheet#mhp]`






































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




~~~meta-bind-js-view
{rsheet#WP1.name} as input1
{rsheet#WP2.name} as input2
{rsheet#WP3.name} as input3
{rsheet#WP4.name} as input4
{rsheet#WP5.name} as input5
---
const inputs = [context.bound.input1, context.bound.input2, context.bound.input3,context.bound.input4,context.bound.input5];

// Create a function to generate the markdown string for each input
const generateMarkdown = (input, index) => `
  \`VIEW[{Armory#${input}.Hit}][text(hidden):rsheet#WP${index+1}.Hit]\`
  \`VIEW[{Armory#${input}.Damage}][text(hidden):rsheet#WP${index+1}.Damage]\`
  \`VIEW[{Armory#${input}.Bonus}][text(hidden):rsheet#WP${index+1}.Bonus]\`
  \`VIEW[{Armory#${input}.Property}][text(hidden):rsheet#WP${index+1}.Property]\` \`VIEW[{Armory#${input}.Type}][text(hidden):rsheet#WP${index+1}.Type]\`
  \`VIEW[{Armory#${input}.Range}][text(hidden):rsheet#WP${index+1}.Range]\`
`;

// Map through the inputs and join the results into one large string
const str = inputs
  .filter(input => input)  // Filter out any undefined or empty inputs
  .map(generateMarkdown)
  .join('\n');

// Render the markdown
return engine.markdown.create(str);


~~~




```meta-bind-js-view
{rsheet#spellslot.lvl1} as slot1
{rsheet#spellslot.lvl2} as slot2
{rsheet#spellslot.lvl3} as slot3
{rsheet#spellslot.lvl4} as slot4
{rsheet#spellslot.lvl5} as slot5
{rsheet#spellslot.lvl6} as slot6
{rsheet#spellslot.lvl7} as slot7
{rsheet#spellslot.lvl8} as slot8
{rsheet#spellslot.lvl9} as slot9

---
const levels = [1, 2, 3, 4, 5, 6, 7, 8, 9];
const slots = [
  context.bound.slot1,
  context.bound.slot2,
  context.bound.slot3,
  context.bound.slot4,
  context.bound.slot5,
  context.bound.slot6,
  context.bound.slot7,
  context.bound.slot8,
  context.bound.slot9
];

const input = [];

// Generate the Markdown for each level and slot
levels.forEach((level, index) => {
  const slot = slots[index]; // Match the slot with the level
  input.push("```meta-bind-button");
  input.push(`  label: "+1"`);
  input.push("  hidden: true");
  input.push(`  id: "lvl${level}-cast"`);
  input.push("  style: primary");
  input.push("  class: navigation-buttons");
  input.push("  actions:");
  input.push("    - type: updateMetadata");
  input.push(`      bindTarget: rsheet#spellcast.lvl${level}`);
  input.push("      evaluate: true");
  input.push(`      value: "Math.min(x + 1, ${slot})"`);
  input.push("```");
});

// Join all parts into a single Markdown string
const str = input.join('\n');

// Render the Markdown
return engine.markdown.create(str);

```


















