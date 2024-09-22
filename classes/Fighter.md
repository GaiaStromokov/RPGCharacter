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
Level: 4
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
pclass: fighter
---

## Input for Level (for testing)
Level: `INPUT[number(class(nb-mb-css)):Level]`
Level: `INPUT[text(class(nb-mb-css)):pclass]`
___
~~~meta-bind-js-view
{Level} as level
{skillChoice.skill1} as skill1
{skillChoice.skill2} as skill2 
{rsheet#abilityMods.con} as conMod
{rsheet#hitDice} as hitDice
{l4c} as l4c
{l6c} as l6c
{l8c} as l8c
{l12c} as l12c
{l14c} as l14c
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
const l6c = context.bound.l6c;
const l8c = context.bound.l8c;
const l12c = context.bound.l12c;
const l14c = context.bound.l14c;
const l16c = context.bound.l16c;
const l19c = context.bound.l19c;
const pclass = context.bound.pclass;

// Generate markdown string for the new level
let str = ``;

// Only execute if pclass is "fighter"
if (pclass === "fighter") {
  // Calculate base HP and current HP
  let baseHP = hitDice + conMod; 
  let healthIncrease = (level > 1) ? conMod : 0; 
  let currentHP = baseHP + (level - 1) * healthIncrease; 

  // Display Hit Points
  if (level >= 1) {
    str += `**Hit Points:** ${currentHP}\n`;
  }

  // Add Skills
  if (level >= 1) {
    str += `\n**Skills (Choose 2 from list)**\n`;
    str += `Choice 1: \`INPUT[inlineSelect(option(Acrobatics), option(Animal Handling), option(Athletics), option(History), option(Insight), option(Intimidation), option(Perception), option(Survival)):skillChoice.skill1]\`\n`;
    str += `Choice 2: \`INPUT[inlineSelect(option(Acrobatics), option(Animal Handling), option(Athletics), option(History), option(Insight), option(Intimidation), option(Perception), option(Survival)):skillChoice.skill2]\`\n`;
  }

  // Add Fighting Styles
  if (level >= 1) {
    let numFightingStyles = level >= 5 ? 2 : 1; 
    str += `\n**Fighting Style${numFightingStyles > 1 ? 's' : ''} (Choose ${numFightingStyles}):**\n`;
    for (let i = 1; i <= numFightingStyles; i++) {
      str += `\`INPUT[inlineSelect(option(Archery), option(Defense), option(Dueling), option(Great Weapon Fighting), option(Protection), option(Two-Weapon Fighting)):ability.fightingStyle${i}]\`\n`;
    }
  }

  // Add Sliders
  if (level >= 1) {
    str += `**Second Wind:** \`VIEW[{ability.secondWind}]\` / 1 use\n`;  
    str += `\`INPUT[slider(minValue(0), maxValue(1), addLabels):ability.secondWind]\`\n`;

    if (level >= 2) {
      let maxActionSurge = (level >= 17) ? 2 : 1; 
      str += `\n**Action Surge:** \`VIEW[{ability.actionSurge}]\` / ${maxActionSurge} Uses\n`;
      str += `*You can take one additional action on your turn.*\n`;
      str += `\`INPUT[slider(minValue(0), maxValue(${maxActionSurge}), addLabels):ability.actionSurge]\`\n`;
    }

    if (level >= 9) {
      let maxIndomitableUses = (level >= 17) ? 3 : (level >= 13) ? 2 : 1; 
      str += `\n**Indomitable:** \`VIEW[{ability.indomitable}]\` / ${maxIndomitableUses} Uses\n`;
      str += `*You can reroll a failed saving throw.*\n`;
      str += `\`INPUT[slider(minValue(0), maxValue(${maxIndomitableUses}), addLabels):ability.indomitable]\`\n`;
    }
  }

  // Add Martial Features
  if (level >= 3) {
    str += `\n**Level 3 features:** Add later.\n`;
  }

  // Add Ability Score Improvements
  let asiLevels = [4, 6, 8, 12, 14, 16, 19]; 
  let attributes = ['str', 'dex', 'con', 'int', 'wis', 'cha']; 

  asiLevels.forEach((asiLevel) => {
    if (level >= asiLevel) {
      str += `**Ability Score Improvement - Level ${asiLevel}:**\n`;
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
~~~meta-bind-js-view
{Level} as level
{skillChoice.skill1} as skill1
{skillChoice.skill2} as skill2 
{rsheet#abilityMods.con} as conMod
{rsheet#hitDice} as hitDice
{l4c} as l4c
{l6c} as l6c
{l8c} as l8c
{l12c} as l12c
{l14c} as l14c
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
const l6c = context.bound.l6c;
const l8c = context.bound.l8c;
const l12c = context.bound.l12c;
const l14c = context.bound.l14c;
const l16c = context.bound.l16c;
const l19c = context.bound.l19c;
const pclass = context.bound.pclass;

// Generate markdown string for the new level
let str = ``;

// Only execute if pclass is "fighter"
if (pclass === "fighter") {
  // Calculate base HP and current HP
  let baseHP = hitDice + conMod; 
  let healthIncrease = (level > 1) ? conMod : 0; 
  let currentHP = baseHP + (level - 1) * healthIncrease; 

  // Display Hit Points
  if (level >= 1) {
    str += `**Hit Points:** ${currentHP}\n`;
  }

  // Add Skills
  if (level >= 1) {
    str += `\n**Skills (Choose 2 from list)**\n`;
    str += `Choice 1: \`INPUT[inlineSelect(option(Acrobatics), option(Animal Handling), option(Athletics), option(History), option(Insight), option(Intimidation), option(Perception), option(Survival)):skillChoice.skill1]\`\n`;
    str += `Choice 2: \`INPUT[inlineSelect(option(Acrobatics), option(Animal Handling), option(Athletics), option(History), option(Insight), option(Intimidation), option(Perception), option(Survival)):skillChoice.skill2]\`\n`;
  }

  // Add Fighting Styles
  if (level >= 1) {
    let numFightingStyles = level >= 5 ? 2 : 1; 
    str += `\n**Fighting Style${numFightingStyles > 1 ? 's' : ''} (Choose ${numFightingStyles}):**\n`;
    for (let i = 1; i <= numFightingStyles; i++) {
      str += `\`INPUT[inlineSelect(option(Archery), option(Defense), option(Dueling), option(Great Weapon Fighting), option(Protection), option(Two-Weapon Fighting)):ability.fightingStyle${i}]\`\n`;
    }
  }

  // Add Sliders
  if (level >= 1) {
    str += `**Second Wind:** \`VIEW[{ability.secondWind}]\` / 1 use\n`;  
    str += `\`INPUT[slider(minValue(0), maxValue(1), addLabels):ability.secondWind]\`\n`;

    if (level >= 2) {
      let maxActionSurge = (level >= 17) ? 2 : 1; 
      str += `\n**Action Surge:** \`VIEW[{ability.actionSurge}]\` / ${maxActionSurge} Uses\n`;
      str += `*You can take one additional action on your turn.*\n`;
      str += `\`INPUT[slider(minValue(0), maxValue(${maxActionSurge}), addLabels):ability.actionSurge]\`\n`;
    }

    if (level >= 9) {
      let maxIndomitableUses = (level >= 17) ? 3 : (level >= 13) ? 2 : 1; 
      str += `\n**Indomitable:** \`VIEW[{ability.indomitable}]\` / ${maxIndomitableUses} Uses\n`;
      str += `*You can reroll a failed saving throw.*\n`;
      str += `\`INPUT[slider(minValue(0), maxValue(${maxIndomitableUses}), addLabels):ability.indomitable]\`\n`;
    }
  }

  // Add Martial Features
  if (level >= 3) {
    str += `\n**Level 3 features:** Add later.\n`;
  }

// Add Ability Score Improvements
let asiLevels = [4, 6, 8, 12, 14, 16, 19]; 
let attributes = ['str', 'dex', 'con', 'int', 'wis', 'cha']; 

str += `\n**Ability Score Improvements:**\n`;
str += `| Level | Increase Type | Choices |\n`;
str += `|-------|---------------|---------|\n`;

asiLevels.forEach((asiLevel) => {
  if (level >= asiLevel) {
    let increaseType = `\`INPUT[inlineSelect(option(1), option(2)):l${asiLevel}c]\``;
    let choices = '';

    let choice = eval(`l${asiLevel}c`);  
    if (choice == 1) {
      choices = `\`INPUT[inlineSelect(${attributes.map(attr => `option(${attr})`).join(', ')}):l${asiLevel}v1]\``;
    } else if (choice == 2) {
      choices = `\`INPUT[inlineSelect(${attributes.map(attr => `option(${attr})`).join(', ')}):l${asiLevel}v11]\`, ` +
                `\`INPUT[inlineSelect(${attributes.map(attr => `option(${attr})`).join(', ')}):l${asiLevel}v12]\``;
    }

    str += `| Level ${asiLevel} | ${increaseType} | ${choices} |\n`;
  }
});



// Render the markdown
return engine.markdown.create(str);
~~~


