---
level:
---
Level Input: `INPUT[text:level]`

```meta-bind-js-view

---
const mb = engine.getPlugin('obsidian-meta-bind-plugin').api;
const lvlT = mb.parseBindTarget('level', context.file.path);

return mb.reactiveMetadata([lvlT], component, (from) => {

    return engine.markdown.create(from);
});

```