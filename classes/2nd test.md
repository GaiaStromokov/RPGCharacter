---
aScore:
  str: 12
  con: 12
  dex: 12
  int: 12
  wis: 12
  cha: 12
aMod:
  str: 1
  con: 1
  dex: 1
  int: 1
  wis: 1
  cha: 1
level: 12
hdice: 8
ability:
  secondWind: 0
  indomitable: 0
---
str: `VIEW[{str}]`
level: `INPUT[number:level]`

```meta-bind-js-view

---
const mb = engine.getPlugin('obsidian-meta-bind-plugin').api;
const lvlT = mb.parseBindTarget('level', context.file.path);
const hitdiceT = mb.parseBindTarget('hdice', context.file.path);
const mconT = mb.parseBindTarget('aMod.con', context.file.path);


	


return mb.reactiveMetadata([lvlT], component, (from) => {
    const outstring = generateCharacterInfo(from);
    // Render the markdown
    return engine.markdown.create(outstring);
});

// Function to generate the character information string
function generateCharacterInfo(level) {
    const messages = [];
    
    // Hit Points
    messages.push(generateHitPoints(level));

    // Skills Section
    if (level >= 1) {
        messages.push(generateSkillsSection());
        messages.push(secondwind(level))
    }

	if (level >= 2) {
		messages.push(generateFightingStylesSection(level));
		messages.push(actionsurge(level))
	
	
	}

	if (level >= 9)
		messages.push(Indomitable(level))
    

    return messages.join('\n');
}

// Function to calculate and display hit points
function generateHitPoints(level) {
	
    let hitDice = mb.getMetadata(hitdiceT); // Example hit dice (replace with your actual variable)
    let conMod = mb.getMetadata(mconT); // Example constitution modifier (replace with your actual variable)
    let baseHP = hitDice + conMod; 
    let healthIncrease = (level > 1) ? conMod : 0; 
    let currentHP = baseHP + (level - 1) * healthIncrease; 
    return `**Hit Points:** ${currentHP}\n`;
}

// Function to generate Skills section
function generateSkillsSection() {
    return `\n**Skills (Choose 2 from list)**\n` +
           `Choice 1: \`INPUT[inlineSelect(option(Acrobatics), option(Animal Handling), option(Athletics), option(History), option(Insight), option(Intimidation), option(Perception), option(Survival)):skillChoice.skill1]\`\n` +
           `Choice 2: \`INPUT[inlineSelect(option(Acrobatics), option(Animal Handling), option(Athletics), option(History), option(Insight), option(Intimidation), option(Perception), option(Survival)):skillChoice.skill2]\`\n`;
}

// Function to generate Fighting Styles section
function generateFightingStylesSection(level) {
    const numFightingStyles = level >= 5 ? 2 : 1;
    let section = `\n**Fighting Style${numFightingStyles > 1 ? 's' : ''} (Choose ${numFightingStyles}):**\n`;
    for (let i = 1; i <= numFightingStyles; i++) {
        section += `\`INPUT[inlineSelect(option(Archery), option(Blind Fighting), option(Defense), option(Dueling), option(Great Weapon Fighting), option(Interception), option(Protection), option(Superior Technique), option(Thrown Weapon Fighting), option(Two-Weapon Fighting), option(Unarmed Fighting), option(Close Quarters Shooter), option(Mariner), option(Tunnel Fighter)):ability.fightingStyle${i}]\`\n`;
    }
    return section;
}

function secondwind(level) {
	let swstring = '';
    swstring += `Second Wind: \`VIEW[{ability.secondWind}]\` / 1 use\n`;  
    swstring += `\`INPUT[slider(minValue(0), maxValue(1), addLabels):ability.secondWind]\`\n`;
  return swstring;
}

function actionsurge(level) {
	let acsstring = '';
	let maxActionSurge = (level >= 17) ? 2 : 1; 
    acsstring += `\nAction Surge: \`VIEW[{ability.actionSurge}]\` / ${maxActionSurge} Uses\n`;
      acsstring += `You can take one additional action on your turn.\n`;
      acsstring += `\`INPUT[slider(minValue(0), maxValue(${maxActionSurge}), addLabels):ability.actionSurge]\`\n`;
  return acsstring;
}

function Indomitable(level) {
	let instring = '';
    let maxIndomitableUses = (level >= 17) ? 3 : (level >= 13) ? 2 : 1; 
	instring += `\nIndomitable: \`VIEW[{ability.indomitable}]\` / ${maxIndomitableUses} Uses\n`;
	instring += `You can reroll a failed saving throw.\n`;
	instring += `\`INPUT[slider(minValue(0), maxValue(${maxIndomitableUses}), addLabels):ability.indomitable]\`\n`;
  return instring;
}




```

