<%*
const file = tp.file.find_tfile(tp.file.title);
const level = tp.frontmatter.level;

// Define the features for the Fighter class up to level 20
const fighterFeatures = {
  3: {
    secondWind: true
  },
  7: {
    actionSurge: true
  },
  10: {
    indomitable: true
  },
  15: {
    superiorDefense: true
  },
  18: {
    additionalAction: true
  },
  20: {
    mastery: true
  }
};

// Process the frontmatter to update the ability property based on the level
await app.fileManager.processFrontMatter(file, (frontmatter) => {
  // Initialize the ability object if it doesn't exist
  frontmatter.ability = frontmatter.ability || {};

  // Add features for levels the character has reached
  for (const [featureLevel, features] of Object.entries(fighterFeatures)) {
    const levelNumber = parseInt(featureLevel, 10);

    if (level >= levelNumber) {
      // Add or update feature keys
      for (const key of Object.keys(features)) {
        frontmatter.ability[key] = true;
      }
    } else {
      // Set features to false if level is less than required
      for (const key of Object.keys(features)) {
        frontmatter.ability[key] = frontmatter.ability[key] || false;
      }
    }
  }

  // Set features to false for levels not yet reached
  for (const featureLevel of Object.keys(fighterFeatures)) {
    const levelNumber = parseInt(featureLevel, 10);

    if (level < levelNumber) {
      // Set feature keys to false if they are not applicable
      for (const key of Object.keys(fighterFeatures[featureLevel])) {
        frontmatter.ability[key] = false;
      }
    }
  }
});
-%>
