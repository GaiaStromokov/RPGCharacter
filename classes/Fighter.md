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
Level: 20
l4c: 1
l4v1: 
l4v11: 
l4v12: 
l6c: feat
l6v1: dex
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
l4feat: Athlete
l4f: Lucky
l6f: Athlete
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
{l4f} as l4f
{l6f} as l6f
{l8f} as l8f
{l12f} as l12f
{l16f} as l16f
{l19f} as l19f
{pclass} as pclass
{ability.fightingStyle1} as fightingStyle1
{ability.fightingStyle2} as fightingStyle2
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
const l4f = context.bound.l4f;
const l6f = context.bound.l6f;
const l8f = context.bound.l8f; 
const l12f = context.bound.l12f; 
const l16f = context.bound.l16f; 
const l19f = context.bound.l19f; 
const pclass = context.bound.pclass;
const fightingStyle1 = context.bound.fightingStyle1
const fightingStyle2 = context.bound.fightingStyle2

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

if (level >= 1) {
    let numFightingStyles = level >= 5 ? 2 : 1; 
    str += `\n**Fighting Style${numFightingStyles > 1 ? 's' : ''} (Choose ${numFightingStyles}):**\n`;
    for (let i = 1; i <= numFightingStyles; i++) {
      str += `\`INPUT[inlineSelect(option(Archery), option(Blind Fighting), option(Defense), option(Dueling), option(Great Weapon Fighting), option(Interception), option(Protection), option(Superior Technique), option(Thrown Weapon Fighting), option(Two-Weapon Fighting), option(Unarmed Fighting), option(Close Quarters Shooter), option(Mariner), option(Tunnel Fighter)
      ):ability.fightingStyle${i}]\`\n`;
    }
    str += `[[FightingStyle#${fightingStyle1}\|${fightingStyle1}]]\n`;
    if (numFightingStyles > 1) {
      str += `[[FightingStyle#${fightingStyle2}\|${fightingStyle2}]]\n`;
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
let feats = ['Actor', 'Alert', 'Athlete', 'Charger', 'Crossbow Expert', 'Defensive Duelist', 'Dual Wielder', 'Durable', 'Elemental Adept', 'Grappler', 'Great Weapon Master', 'Healer', 'Heavily Armored', 'Heavy Armor Master', 'Inspiring Leader', 'Keen Mind', 'Lucky', 'Mage Slayer', 'Magic Initiate', 'Martial Adept', 'Medium Armor Master', 'Mobile', 'Moderately Armored', 'Observant', 'Polearm Master', 'Resilient', 'Ritual Caster', 'Savage Attacker', 'Sentinel', 'Shield Master', 'Skilled', 'Skulker', 'Spell Sniper', 'Tavern Brawler', 'Tough', 'War Caster', 'Weapon Master'];

asiLevels.forEach((asiLevel) => {

  if (level >= asiLevel) {
    str += `**ASI-L${asiLevel}:**\n`;
    str += `\`INPUT[inlineSelect(option(1), option(2), option(feat)):l${asiLevel}c]\`\n`;

    let choice = eval(`l${asiLevel}c`);  
    if (choice == 1) {
      str += `\`INPUT[inlineSelect(${attributes.map(attr => `option(${attr})`).join(', ')}):l${asiLevel}v1]\`\n`;
      str += `\`VIEEW
    } else if (choice == 2) {
      str += `\`INPUT[inlineSelect(${attributes.map(attr => `option(${attr})`).join(', ')}):l${asiLevel}v11]\`\n`;
      str += `\`INPUT[inlineSelect(${attributes.map(attr => `option(${attr})`).join(', ')}):l${asiLevel}v12]\`\n`;
    } else if (choice === 'feat') {
      str += `\`INPUT[inlineSelect(${feats.map(feat => `option(${feat})`).join(', ')}):l${asiLevel}f]\`\n`;
    }
  }
});







}

// Render the markdown
return engine.markdown.create(str);
~~~