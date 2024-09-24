---
HPL1: 12
hDice: 8
nHDice: 20
skillChoice:
  skill1: Animal Handling
  skill2: Insight
ability:
  rage: 0
Level: 20
l4c: 
l4v1: 
l4v11: 
l4v12: 
l6c: 
l6v1: 
l6v11: 
l6v12: 
l8c: 
l8v1: 
l8v11: 
l8v12: 
l12c: 
l12v1: 
l12v11: 
l12v12: 
l14c: 
l14v1: 
l14v11: 
l14v12: 
l16c: 
l16v1: 
l16v11: 
l16v12: 
l19c: 
l19v1: 
l19v11: 
l19v12: 
pclass: barbarian
uaAC: 12
---


Level: `INPUT[number(class(nb-mb-css)):Level]`
Level: `INPUT[text(class(nb-mb-css)):pclass]`

~~~meta-bind-js-view
{Level} as level
{skillChoice.skill1} as skill1
{skillChoice.skill2} as skill2 
{rsheet#abilityMods.con} as conMod
{rsheet#hitDice} as hitDice
{l4c} as l4c
{l8c} as l8c
{l12c} as l12c
{l16c} as l16c
{l19c} as l19c
{pclass} as pclass
---
const level = context.bound.level;
const skill1 = context.bound.skill1;
const skill2 = context.bound.skill2; 
const conMod = context.bound.conMod;
const hitDice = context.bound.hitDice;
const l4c = context.bound.l4c;
const l8c = context.bound.l8c;
const l12c = context.bound.l12c;
const l16c = context.bound.l16c;
const l19c = context.bound.l19c;
const pclass = context.bound.pclass;
// Generate markdown string for the new level
let str = ``;

// Only execute if pclass is "barbarian"
if (pclass === "barbarian") {
  // Calculate base HP and current HP
  let baseHP = hitDice + conMod; 
  let healthIncrease = (level > 1) ? conMod : 0; 
  let currentHP = baseHP + (level - 1) * healthIncrease; 

  // Display Hit Points
  if (level >= 1) {
    str += `Hit Points: ${currentHP}\n`;
  }

  // Add Skills
  if (level >= 1) {
    str += `\nSkills (Choose 2 from list)\n`;
    str += `Choice 1: \`INPUT[inlineSelect(option(Acrobatics), option(Animal Handling), option(Athletics), option(History), option(Insight), option(Intimidation), option(Perception), option(Survival)):skillChoice.skill1]\`\n`;
    str += `Choice 2: \`INPUT[inlineSelect(option(Acrobatics), option(Animal Handling), option(Athletics), option(History), option(Insight), option(Intimidation), option(Perception), option(Survival)):skillChoice.skill2]\`\n`;
  }

  // Add Rage
  if (level >= 1) {
    let maxRages;
    if (level === 1) maxRages = 2;
    else if (level < 3) maxRages = 2;
    else if (level < 6) maxRages = 3;
    else if (level < 12) maxRages = 4;
    else if (level < 17) maxRages = 5;
    else if (level < 20) maxRages = 6;
    else maxRages = 999; // Level 20

    str += `\nRages: \`VIEW[{ability.rage}]\` / ${maxRages} uses\n`;
    str += `You can enter a rage as a bonus action.\n`;
    str += `\`INPUT[slider(minValue(0), maxValue(${maxRages}), addLabels):ability.rage]\`\n`;
  }

  // Add Unarmored Defense
  if (level >= 1) {
    str += `\`VIEW[10+{rsheet#abilityMods.dex}+{rsheet#abilityMods.con}][math(hidden):uaAC]\`` + 
           `\n**Unarmored Defense:** You can calculate your AC using 10 + your Dexterity modifier + your Constitution modifier.\n` +
           `AC= \`VIEW[{uaAC}][text]\`\n`;
  }

  // Add Extra Attack and Fast Movement (Level 5)
  if (level >= 5) {
    str += `\n**Extra Attack:** Beginning at 5th level, you can attack twice, instead of once, whenever you take the Attack action on your turn.\n`;
    str += `**Fast Movement:** Starting at 5th level, your speed increases by 10 feet while you aren't wearing heavy armor.\n`;
  }

  // Add Feral Instinct and Instinctive Pounce (Level 7)
  if (level >= 7) {
    str += `\n**Feral Instinct:** You have advantage on initiative rolls.\n`;
    str += `If you are surprised at the beginning of combat and aren't incapacitated, you can act normally on your first turn, but only if you enter your rage before doing anything else on that turn.\n`;
    str += `**Instinctive Pounce:** (Optional) As part of the bonus action you take to enter your rage, you can move up to half your speed.\n`;
  }

  // Add Brutal Critical (Level 9)
// Add Brutal Critical feature
  if (level >= 9) {
    let additionalDice = (level >= 17) ? 3 : (level >= 13) ? 2 : 1;

    str += `\n**Brutal Critical:** On a critical hit, roll ${additionalDice} additional weapon damage dice.\n`;
}

  // Add Relentless Rage (Level 11)
  if (level >= 11) {
    str += `\n**Relentless Rage:** Starting at 11th level, if you drop to 0 hit points while raging, you can make a DC 10 Constitution saving throw to drop to 1 hit point instead.\n`;
    str += `Each time you use this feature after the first, the DC increases by 5. The DC resets to 10 after a short or long rest.\n`;
  }

  // Add Persistent Rage (Level 15)
  if (level >= 15) {
    str += `\n**Persistent Rage:** Your rage ends early only if you fall unconscious or if you choose to end it.\n`;
  }

  // Add Indomitable Might (Level 18)
  if (level >= 18) {
    str += `\n**Indomitable Might:** If your total for a Strength check is less than your Strength score, you can use that score in place of the total.\n`;
  }

  // Add Primal Champion (Level 20)
  if (level >= 20) {
    str += `\n**Primal Champion:** At level 20, your Strength and Constitution scores increase by 4, and their maximum is now 24.\n`;
  }

  // Add Ability Score Improvements
  let asiLevels = [4, 8, 12, 16, 19]; 
  let attributes = ['str', 'dex', 'con', 'int', 'wis', 'cha']; 

  asiLevels.forEach((asiLevel) => {
    if (level >= asiLevel) {
      str += `\n**Ability Score Improvement - Level ${asiLevel}:**\n`;
      str += `\`INPUT[inlineSelect(option(1), option(2)):l${asiLevel}c]\`\n`;

      let choice = eval(`l${asiLevel}c`);  
      if (choice == 1) {
        str += `\`INPUT[inlineSelect(${attributes.map(attr => `option(${attr})`).join(', ')}):l${asiLevel}v1]\`\n`;
      } else if (choice == 2) {
        str += `\`INPUT[inlineSelect(${attributes.map(attr => `option(${attr})`).join(', ')}):l${asiLevel}v11]\`\n`;
        str += `\`INPUT[inlineSelect(${attributes.map(attr => `option(${attr})`).join(', ')}):l${asiLevel}v12]\`\n`;
      }
    }
  });
}

// Render the markdown
return engine.markdown.create(str);
~~~
