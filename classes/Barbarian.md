---
HPL1: 12
hDice: 8
nHDice: 20
skillChoice:
  skill1: Animal Handling
  skill2: Insight
ability:
  secondWind: 0
  actionSurge: 0
  indomitable: 0
  fightingStyle1: Dueling
  fightingStyle2: Great Weapon Fighting
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
    else if (level < 3) maxRages = 2; // Same as level 1
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
    str += `\nUnarmored Defense: You can calculate your AC using 10 + your Dexterity modifier + your Constitution modifier.\n`;
  }

  // Add Martial Features
  if (level >= 2) {
    str += `\nLevel 2 features: Add later.\n`;
  }

  // Add Brutal Critical feature
  if (level >= 9) {
    str += `\nBrutal Critical: At level 9, you can roll an additional die for your critical hits.\n`;
  }

  // Add Indomitable Might feature
  if (level >= 18) {
    str += `\nIndomitable Might: At level 18, your Strength score cannot be less than your barbarian level.\n`;
  }

  // Add Primal Champion feature
  if (level >= 20) {
    str += `\nPrimal Champion: At level 20, your Strength and Constitution scores increase by 4.\n`;
  }

  // Add Ability Score Improvements
  let asiLevels = [4, 8, 12, 16, 19]; 
  let attributes = ['str', 'dex', 'con', 'int', 'wis', 'cha']; 

  asiLevels.forEach((asiLevel) => {
    if (level >= asiLevel) {
      str += `Ability Score Improvement - Level ${asiLevel}:\n`;
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

