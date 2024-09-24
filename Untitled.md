---
level: 1
---

Level `INPUT[number:level]`
```meta-bind-js-view

---
const mb = engine.getPlugin('obsidian-meta-bind-plugin').api;

const lvlT = mb.parseBindTarget('level', context.file.path);
return mb.reactiveMetadata([lvlT], component, (from) => {
    return generateCharacterInfo(from);
});

// Function to generate the character information string
function generateCharacterInfo(level) {
    const messages = [];
    
    // Hit Points
    messages.push(generateHitPoints(level));

    // Skills Section
    if (level >= 1) {
        messages.push(generateSkillsSection());
    }

    // Fighting Styles Section
    messages.push(generateFightingStylesSection(level));

    return messages.join('\n');
}

// Function to calculate and display hit points
function generateHitPoints(level) {
    let hitDice = 10; // Example hit dice (replace with your actual variable)
    let conMod = 2; // Example constitution modifier (replace with your actual variable)

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
        section += `\`INPUT[inlineSelect(option(Archery), option(Blind Fighting), option(Defense), option(Dueling), option(Great Weapon Fighting), option(Interception), option(Protection), option(Superior Technique), option(Thrown Weapon Fighting), option(Two-Weapon Fighting), option(Unarmed Fighting), option(Close Quarters Shooter), option(Mariner), option(Tunnel Fighter):ability.fightingStyle${i}]\`\n`;
    }
    return section;
}

```

