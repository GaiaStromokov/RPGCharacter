<%*
const file = tp.file.find_tfile(tp.file.title);
const level = tp.frontmatter.level;

// Define the feature from the fighter class
const fighterFeature = "Second Wind: You can use a bonus action to regain hit points equal to 1d10 + your fighter level.";

await app.fileManager.processFrontMatter(file, (frontmatter) => {
  if (level === 3) {
    frontmatter.ability = frontmatter.ability || {};
    frontmatter.ability.secondWind = 1;
  } else if (level < 3) {
    if (frontmatter.ability && frontmatter.ability.secondWind) {
      delete frontmatter.ability.secondWind;
    }
  }
});
-%>
